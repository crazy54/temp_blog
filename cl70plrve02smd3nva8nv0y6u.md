## Multi-Cloud: Why You Need to Push Back on Leadership

_**“Multiple Clouds - Two is better than one, amiright?!? That is what all you operational folks say when it comes to keeping services alive!”**_

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1660849559319/buyHaOlkw.png)


##### _**Is this what you say in your head when your leadership asks what clouds you are on today and why you are not on ${insert.cloud.var}?**_

* * *

> “.._you get **some** elasticity, you get **some** cost savings out of it, maybe **some** more reliability, **but you get none of the other benefits**. You can't use any of the security tools that Amazon is giving you. Plus, you need to have your workforce, your development force **able to be proficient in each and every one of these clouds that you're using, which seems like a waste.**”_
> 
> *   _**Dr. Warner Vogels, CTO, Amazon Web Services**_
>     

This is a topic that I am sure many of you reading have heard about and even struggled to win this argument before! Well, maybe not with the _exact phrasing_, but you get the point. Our leaders these days are facing some hard choices, such as:

Thanks for reading apt-get ops! Subscribe for free to receive new posts and support my work.

_“AWS had a rough 2021 when it came to operations in US-EAST-1 and other large US-based regions, and the board wants answers quickly on how we will be autonomous from AWS or any cloud platform.”_

If you are a Sr. Engineer in operations, this blog is going to give you hard facts on how you can help your senior leaders stand up to the board that has no idea about operations, but still believes they know the best path forward. This blog is dedicated to all y’all that are struggling with this sort of stuff at work right now.

    Myth: If We Operate on TWO Cloud Providers, It Won’t Take Long to Get Setup on Cloud 2 Because All Our Infrastructure is Stood Up Using (Insert Infrastructure as Code (IaC) Solution Here)

**WRONG. Just becuase you have [Infrastructure as Code](https://en.wikipedia.org/wiki/Infrastructure_as_code) [(IaC)](https://en.wikipedia.org/wiki/Infrastructure_as_code) does not mean standing up a second set of infrastructure is simple or easy.**

Terraform vs The World
----------------------

Let’s just get Terraform out of the way. TF requires you to code for a _provider_. Each provider has its own methods and functions depending on the cloud provider and service. Let’s take a look at an example of using TF to stand up a VM on Azure and AWS and see what can be used as a template. For each example, I build a VM, and the _**bare minimum**_ _**supporting features.**_ On AWS, I make a VPC (/16), a private subnet (/24) and network interface on the instance on that subnet.

On Azure, I did many of the same options - I first made my resource group, then to that group I add in a VM and tell Azure to use the latest Ubuntu 16.04 image. Then, I set disk params so the disk is removed on VM deletion for simple cleanup. Once that is done, a new /16 CIDR is carved up just like AWS, and I then make a private /24 range to use on the VM, and a network interface the VM will attach so it can speak on that subnet.

Also to those in the community who will say things such as: _“You can put the required provider into a env\_var on the machine executing the build code or in a variables.tf file to make changes and use the same basic code over again!”_

Yes, I get that. However, I want to show what is _**required**_ in the code; Even if you can/would make environment variables out of repeating variables in the build. I have built out many Terraform environments in my day so I know how to template/copy over and over. _**Smarter**_, **not harder**.

#### **AWS**

##### _Create one EC2 t3a.Large instance called_ aptget-ops_\-001 and supporting VPC/network._

    terraform {
      required_providers {
        aws = {
          source  = "hashicorp/aws"
          version = "~> 3.0"
        }
      }
    }
    
    # Start AWS Provider
    provider "aws" {
      region = "us-east-1"
    }
    
    variable "instance_count" {
      default = "000"
    }
    
    resource "aws_vpc" "ago_vpc" {
      cidr_block = "192.16.0.0/16"
    
      tags = {
        Name = "aptget-ops-vpc"
      }
    }
    
    resource "aws_subnet" "blog-prod_subnet" {
      vpc_id            = aws_vpc.ago_vpc.id
      cidr_block        = "192.168.10.0/24"
      availability_zone = "us-east-1a"
    
      tags = {
        Name = "aptget-ops-PROD"
      }
    }
    
    resource "aws_instance" "prod_web_server" {
      ami           = "ami-1a2b3c4d"
      instance_type = "t3a.Large"
    
      tags = {
        Name = "aptget-ops-${count.index + 1}"
      }
    
      network_interface {
          network_interface_id = aws_network_interface.prod_web_server.id
          device_index         = 0
      }
    }

#### **Azure**

##### _Create one VM called aptget-ops-001 and supporting networking._

    # Configure the Azure provider
    
    terraform {
      required_providers {
        azurerm = {
          source  = "hashicorp/azurerm"
          version = "~> 3.0.2"
        }
      }
    
      required_version = ">= 1.1.0"
    }
    
    variable "instance_count" {
      default = "000"
    }
    
    resource "azurerm_resource_group" "rg" {
      name     = aptget-ops-prod-rg"
      location = "westus2"
    }
    
    resource "azurerm_virtual_network" "prod" {
      name                = "aptget-ops-blog-vpc"
      address_space       = ["10.0.0.0/16"]
      location            = azurerm_resource_group.location
      resource_group_name = azurerm_resource_group.name
    }
    
    resource "azurerm_subnet" "default" {
      name                 = "default-eth"
      resource_group_name  = azurerm_resource_group.example.name
      virtual_network_name = azurerm_virtual_network.example.name
      address_prefixes     = ["10.10.2.0/24"]
    }
    
    resource "azurerm_network_interface" "pub" {
      name                = "azurerm_linux_virtual_machine.name-nic"
      location            = azurerm_resource_group.example.location
      resource_group_name = azurerm_resource_group.example.name
    
      ip_configuration {
        name                          = "default-eth-cfg"
        subnet_id                     = azurerm_subnet.internal.id
        private_ip_address_allocation = "Dynamic"
      }
    
    tags = {
      environment = "prod"
     }
    
    }
    
    resource "azurerm_linux_virtual_machine" "main" {
      count                 = var.instance.count
      name                  = "aptget-ops-${count.index + 1}"
      location              = azurerm_resource_group.location
      resource_group_name   = azurerm_resource_group.name
      network_interface_ids = [azurerm_network_interface.main.id]
      vm_size               = "Standard_DS1_v2"
     
      tags = {
        Name = "aptget-Ops-${count.index + 1}"
      }
    
      delete_os_disk_on_termination = true
      delete_data_disks_on_termination = true
     
     admin_ssh_key {
        username   = "taco"
        public_key = file("~/.ssh/id_rsa.pub")
      }
    
      storage_image_reference {
        publisher = "Canonical"
        offer     = "UbuntuServer"
        sku       = "16.04-LTS"
        version   = "latest"
      }
    
      storage_os_disk {
        name              = "aptgetblog-OS"
        caching           = "ReadWrite"
        create_option     = "FromImage"
        managed_disk_type = "Standard_LRS"
      }
    
      os_profile {
        computer_name  = "azurerm_linux_virtual_machine.name"
        admin_username = "aptget-ops"
        admin_password = "DerpyTaco!"
      }
    }

_**Note**_: _Terraform’s version at the time of writing is 1.2.4._

**You can see the differences on each of these - it does not take an engineer to understand that going from AWS to Azure or vice-versa is going to take code refactoring and a lot of it. In size alone, you are looking at:**

**AWS - 1Kb - 49 Lines of Code**

**Azure - 3Kb - 93 Lines of Code**

In my day to day work, I see my customers mainly use CloudFormation(CFN) and skip Terraform becuase CFN gives them the ability to code specifically for AWS and get features ahead of a new Terraform provider release or update. The other thing to realize is that Terraform is using the AWS API(s) in the background to execute your stacks. They also say that since they would have to re-do almost all their IaC work, they would much rather have the most current AWS services and features available to them. The other advantage for CFN is that it can be written using the AWS CDK in multiple languages if a developer would like to write their IaC up in TypeScript, Python, Java, C#, and Go instead of a YAML or JSON file.

On the other end of the spectrum, you have those who prefer Terraform and the options it brings to the table - and recently Hashicorp announced the [ability to use their TF CDK](https://www.terraform.io/cdktf) to also generate Terraform IaC files (TF uses .tf as the file ext.) from a long list of the most popular languages. Some companies also like the Hashicorp family of products and standardize on them across the board to simplify workflows for all teams and save on yearly fees. Terraform also has a great open source community and custom code can be written fairly quickly to support custom framework or build pipelines.

Is Multi-Cloud Even Feasible Today?
-----------------------------------

**Short Answer**: _Yes_.

**Long Answer**: _Not really, but money and time can resolve most problems._

* * *

**Let’s assume a few things in this test case:**

1.  Your company has obtained master level dominance across two cloud platforms. Everyone can resolve their own issues and no support cases get created anymore. _**(I will explain why this is not possible later on, so keep up.)**_
    
2.  Your environments are well written, battle tested, and easily deployed on either cloud. No work is required to deploy your apps and microservices and supporting infrastructure.
    

All of your engineers, developers, and dev/fin/ops people are also able to do their jobs on each platform and can solve issues that arise.

* * *

### So… What Now?

Let’s say that you have identical infrastructures in both cloud platforms and now you want to see some benefit for your hard work. The problem you now have is you have to resolve the following development and operational challenges:

1.  **Disaster Recovery** **\-** How can you hit your RPO/RTO timeframe set by management?
    
2.  **Automation -** You will need to make all of your automated scripts aware of each platform and all resources located within each. How do you know when to execute? Are you ingesting logs, metrics and application/api/microservice logs?
    
3.  **Each Application/Service/API/Microservice MUST be Cloud-Aware -** In order to properly have your code know what automation to run on each cloud, you now have to have your logs from all applications, services, APIs, etc. write in their log entries the location of the service.
    
4.  **Server, Cluster & Container Naming Schema -** You will need to modify every single name you have across the board on both platforms/clouds to reflect a naming schema which identifies the cloud provider, region and AZ they are in so your automation corrects the right devices and developers & engineers know what they are looking at.
    

I could continue here, but you get the idea. You now enter what I call phase two. This is where you realize quickly that you have a number of issues to resolve, and you need to get them solved _**quickly. You also need to create SOPs for the second cloud and make sure your DR/Failover/Failout plans all have been tested thoroughly and are executable with instructions provided.**_

Lets look at some of the things I have not mentioned above that would be needed for a successful multi-cloud deployment for your organization.

1.  **Full Stack Visibility and Logging/Monitoring Unification** (Single Pane of Glass)
    
2.  **Single Pane of Glass for SecOps Tooling & Automation/Alerting**
    
3.  **Webapp User Session DB Consideration** - make sure you have your active user session DB shared between each cloud or when you fail out of one cloud, all users will need to fully authenticate again! They will also lose whatever they were working on or what they had in their cart.
    
4.  **Predictive analytics that can identify common and uncommon issues on each platform**
    
5.  **Full-Text Search Platform for**:
    
    *   Logs
        
    *   Metrics
        
    *   Service/Application Specific Logs & Metrics
        
    *   End User Monitoring (EUM) AKA [Real User Monitoring (RUM)](https://en.wikipedia.org/wiki/Real_user_monitoring)
        
    *   Synthetic Site Testing or Canary Testing
        

You can see that real fast the items that you have to be on top of is _**daunting, especially for smaller startups or small-medium sized operations.**_ To get the most benefit out of using multiple cloud services & providers means you have to be an expert at each platform, service and can automate and fail fast to resolve issues as they come up, and believe you/me, they _**WILL**_ come up.

The overall complexity of a setup on multiple cloud platforms is soul crushing and needs multiple engineering teams to deploy, monitor, maintain, and most of all, _**reduce operating costs and human managed tasks as much as possible.**_

I hope this article has shown you some of the good and bad sides of using two clouds, and you have some great details, data and arguments to give to your leadership. I know I am biased towards AWS - I work there, so _**how can I not be?**_ However, my job makes me help our customers cut costs, resolve complexity issues, and fail fast. I get to see how customers overcome these issues and I help them with the AWS side of the problem.

### The Bottom Line A.K.A tldr

Don’t even THINK about moving into a second cloud until you have mastered the cloud you moved to first. Once the above issues have been resolved in production on the first cloud, by all means, feel free to do it. Personally, I just do not see customers getting close to that goal at all with how fast trends like Kubernetes and containerization have dominated the conversation lately.

Mastering a cloud means you master cost saving, the tech, your code, everything. _**Why?**_ Because when you get another cloud involved, you are in for a very steep learning curve and a large cut in deliverables. Do not try to launch new Epics or infrastructure changes until you can operate your Standard Operating Procedures flawlessly on both clouds, without causing disruption to users, developers, engineers, data scientists, BizDev/BizOps and especially project managers are going to have a busy next couple years.

I would love to hear from you if you are running on two cloud providers and have had to solve some of the problems I talked about here. I will check the comments to see if any great stories appear, and maybe we can make a focused article on the issues you personally ran into and how you solved them.

Cheers.

Thanks for reading apt-get ops! Subscribe for free to receive new posts about operations, the cloud(s), site reliability engineering, and tons more. Each person that joins means a lot.