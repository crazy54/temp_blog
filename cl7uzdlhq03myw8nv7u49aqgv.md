## AWS Container Services: Which One is Right For You?

# Containers - The Basic Idea

So, you've determined you want to use AWS as your cloud, now you have to figure out how you can host containers. This is a problem many people face, especially when those who pay for said container operations on AWS are the ones doing the choosing for you based on a budget for a single year of operations, or starting off monthly and determining demand as you go. AWS is awesome. However, when you are not entirely sure about what the difference between EKS, EKS Fargate, ECS, ECS Fargate, & OpenShift are, you may be in for some training really quickly. In this article, I hope to share with you why you would use each one of these AWS container services, and their benefits, as well as their faults or limitations. Get a Redbull, latte, whatever you please - but get caffeinated, and get reading!


### The Open Container Initiative 

Before I delve into the services, I want to determine what a container really is at the lowest level we can get. Back in 2015 when containers (mainly Docker) was getting very large, the community wanted to define what a container is, how you deliver that container, and finally, define how you would create and leverage a filesystem that is portable and able to be used anywhere. This organization made up of some of the largest names in Tech, as well as development projects such as PodMan, and individuals who also get a say and help to push initiatives through the voting process. **This organization became known as The Open Container Initiative or OCI. **

To answer what ***is*** a container, we need to understand the difference between a virtual machine and a container. A VM is a software-based virtualized computer. What I mean, is that a bit of software (big names out there are: VMware, KVM, VirtualBox, and Hyper-V) takes physical hardware and creates an abstraction layer above that to create virtual or emulated computer hardware that the user defines. *(Some virtual machine software can pass the hardware itself into the VM, so for some kinds of virtual machines, they get full access to physical hardware to speed things up or allow hardware features to work with no software getting in the way.)*

Now we understand the hardware bit - when you make a VM, you have basically a blank hard drive and computer hardware that is emulated before you. Now you have to install Windows or Linux just like on a physical computer. The end result is a full computer running the OS you installed with its own hardware dedicated to running that VM. You then run applications on top of the OS you installed on top of the virtual hardware. 

**Now onto a container. This is where things get interesting.**


![ContainersvsVMs_Image.avif](https://cdn.hashnode.com/res/hashnode/image/upload/v1662732823193/ahlIS2kgF.avif
align="center")

The main difference of a container and a VM is that a container does not get hardware. A container uses the hardware of the host it runs on top of, meaning a single container has only the bare basic items needed to run the application or code it contains. Containers do not use the full operating system installation like a VM does. In fact, a container only has the binary and library files needed to run the code contained inside the application. Imagine instead of installing an OS 40 times, but rather, packaging up 30MB of the critical files that make up the needed basics of an Operating System and using that over and over. Any OS install of a modern OS typically is around 15GB, so the space savings in only 10 containers is ***huge*** when you compare VMs to containers. 

Also, you do not need to include all the fluff that a VM would have such as drivers, applications to support the apps you want to run, APIs, you name it. All of that disappears and you are left with only the files that need to make things run. (This is a simplified explanation, but I want to make sure everyone is with me.) Also with a container, you have to use a container engine to download, unzip, and execute said containers. Think of this like the OS running an .MSI or .EXE to start up your favorite game. Containers can run anywhere a container engine like Docker can be installed. Also, containers are usually sized between 100MB and 2-3GB, and yes they can be larger depending on the container and what it does, but most are small as that is one huge advantage they offer us. The last thing to talk about is that with any application that talks to the web, a port is used to pass traffic to and from the backend server to the client. With a container, you define this port in the configuration of the container so it can speak to your load balancer and the internet clients. 

If you want to get an in-depth look at the additional differences, take a peek at this blog post: [IBM - VM vs Containers](https://www.ibm.com/cloud/blog/containers-vs-vms) I want to get into the rest of the content, so I want to keep this part to a minimal amount, as we will speak about more down the line. **Stay with me. **

### The Open Container Initiative 
![oci](https://opencontainers.org/img/logos/OCI-logo.svg align="center")

Now that we understand the differences and what makes a container nice and simple to run at scale anywhere you need to, it is vital to look at the standards containers have to support as Docker is no longer the default or defacto container engine. In fact, Kubernetes dropped Docker support back in v1.23 and now only supports standardized containers built using the OCI accepted standards. 

This means it is best to know more about those specifications the OCI came up with - these are what truly define the container standard as it is known as today. The parts of a container and all container engines as specified by OCI are:

- **Container Image** - What is a Layer? How many can you have? What is in the image?

- **The Runtime** - Details the way all container engines run and the API calls they must support to allow any container to operate, no matter the runtime.

- **Distribution** - How Can You Standardize How to Move Them Around?

- **Artifacts** - What additional artifacts (like Helm charts) are used to manage containers at scale?


### Container Image

![image of a container](https://www.marineinsight.com/wp-content/uploads/2020/12/16-Types-of-Container-Units-and-Designs-for-Shipping-Cargo.png align="center")

See what I did there? That's an ***image of a container.***

1. [**Image Format Specification**](https://github.com/opencontainers/image-spec/blob/main/spec.md)

This specification defines an OCI Image, consisting of an image manifest, an image index (optional), a set of filesystem layers, and a configuration. You must have these parts included to be able to call it a container. All container engines will be looking for these items no matter who made the image or where it came from. Before this standard, Docker had a monopoly on containers, and almost all software was using it as the container engine. However, most people run other engines like Podman as it is more lightweight which allows you to run more containers on the host machine. 

The goal of this specification is to enable the creation of interoperable tools for building, transporting, and preparing a container image to run. In layman's terms, a container must include:

- **Image Manifest**: Unlike the image index, which contains information about a set of images that can span a variety of architectures and operating systems, an **image manifest** provides a configuration and ***set of layers for a single container image for a specific architecture and operating system.***

Here is a simple Python application I made into a container. This is the Dockerfile for that application.

```
FROM python:3.11.0a6-alpine3.15

RUN mkdir /app_code

WORKDIR /app_code

COPY /PYTHON_EXAMPLE_APP/ /app_code

RUN pip3 install -r requirements.txt

EXPOSE 5000/tcp

CMD ["python3", "/app_code/website-flask.py"]
``` 

![My project-1 (2).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662746211739/WzJK2ysxK.png align="center")

If I were to build that container right now, at the end we would get a hash like **32av34b409cb**. This would be the final filesystem ID. If we forgot to run the line where I **COPY ** code from the example_app directory, we would get a layer ID, just as we got layer IDs on the first version build. This new layer ID would be something like **37se2j49bv8f**.  In the image above, you can see how this looks.

In a layered file system like containers use, each layer is an operation. You can speed up builds a ton by making changes to single layers, like making sure all our code required for the build is in a single folder in the repository. If you have your container build file optimized so all your changes are in a single COPY command, and a single folder that is home to your code, only that layer is going to be updated each build of the container. This will save so much time, especially on long manifests. If you can picture a final layer filesystem for this container, Alpine, the Linux OS bits would be on a layer at the base, and then beginning with the first command of RUN mkdir, going down the list would be in order as their own layers. Keep in mind, only lines in the Dockerfile that modify the filesystem are made as a layer. Now, when Docker finishes, it can tar up all the layers and package them as the container image you and I know and love today. Pretty neat. 

There is a lot more in the world of layered file systems and optimizing how containers get built, but this is a crash course.  

There are more things in the manifest but layers are the most notable, and will help you to understand containers much more than some other items on the list. If you are interested to learning more, [check out the full list here!](https://github.com/opencontainers/image-spec/blob/main/manifest.md#image-manifest-property-descriptions)

**Next Up - Runtime.**

[Runtime Specification](https://github.com/opencontainers/runtime-spec)
The Open Container Initiative Runtime Specification aims to specify the configuration, execution environment, and life cycle of a container. This is really for those wanting to make software to *run containers* on hardware. There are different dependencies and specifications based on the OS the software is made to run on, and unless you are developing a podman or Docker competitor, this will be a bit of a bore, and this is not something you need to memorize for DevOps or TechOps.  However, if you are intersted, I would suggest taking a look [at the specifications if you like to get geeky.](https://github.com/opencontainers/runtime-spec/blob/main/spec.md#abstract)

A container's configuration is specified as the config.json for the supported platforms and details the fields that enable the creation of a container. The execution environment is specified to ensure that applications running inside a container have a consistent environment between runtimes along with common actions defined for the container's lifecycle.

[Distribution Specification](https://github.com/opencontainers/distribution-spec)
The Open Container Initiative Distribution Specification (a.k.a. "OCI Distribution Spec") defines an API protocol to facilitate and standardize the distribution of content. Again, this is some lower level programmer stuff, but since we are on the topic, it is pretty interesting if you are wanting to learn more. [This is a link to the spec](https://github.com/opencontainers/distribution-spec/blob/main/spec.md#open-container-initiative-distribution-specification) and take a look if you want to. I read it, and I think it was pretty cool. I love to know how things work, and that is exactly what this is. 

[Artifacts](https://github.com/opencontainers/artifacts)
Applications and services typically require additional artifacts to deploy and manage container images, including helm charts for deployment and Open Policy Agent (OPA) bundles for policy enforcement. This one too is a bit heavy and more on the developer side of the fence if you want to make the next new cool container repository and build/deployment service with custom artifacts. You also may need this if you want to make something like Helm, or any other plugin or artifact related to the deployment, building, or operation of containers. 

## Putting it All Together Now

Well, now you know a lot more than you did when you opened this up. We just learned about the parts that make up the life and operation of containers, and why Docker was pushed out of the monopoly it had. Now, let's get to the heart of the article - container services on AWS and when to use them. 

## Container Services at AWS

AWS has many services that fit the OCI models we learned about above. Let's learn more about each service, and the right time to deploy them inside our companies. 

### What is a "Fargate" and Why Do I Care?

![fargate-logo](https://cdn.hashnode.com/res/hashnode/image/upload/v1662748406832/qww8xqIMj.png align="center")

Ah, yes. Fargate. When ECS (Elastic Container Service) was new at AWS before EKS, Fargate was born. What Fargate does, is basically a complete container lifecycle manager. Fargate takes in your container, and it runs as many of them as you want without you needing to deploy EC2 instances or any compute to deploy those containers to. Fargate takes care of all the autoscaling, and orchestration for you. AWS sums it up best in the opening paragraph of the Fargate documentation for ECS:

***"...package your application in containers, specify the Operating System, CPU and memory requirements, define networking and IAM policies, and launch the application. Each Fargate task has its own isolation boundary and does not share the underlying kernel, CPU resources, memory resources, or elastic network interface with another task."***
-AWS [Fargate ECS Documentation](https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html)

So, Fargate takes care of everything for you. No instance selection, no provisioning, nothing. Just tell Fargate how much CPU and memory you need to run the container(s) you need and tell it about how you want it to scale up, and scale down. This is the best route for those without any DevOps or TechOps engineers to spare, or you want to demo something. 

Fargate can also take advantage of Spot on Linux containers. This is a big deal - you can save more than 50% depending on availability and demand on instances in the Region and AZ you use, but it can use Spot as the capacity provider! If you do use Fargate make sure you use Spot. It makes no sense to not use Spot unless you are doing large, long running tasks for BizOps or ETL jobs that cannot ever be interrupted.  However, you can code the Spot 2-minute warning into your container's code and pass the current job to another container while that instance is taken down and a new instance comes up in its place. I actually have had customers run Fargate ECS with their website, with no issues whatsoever. Don't pass Fargate up just becuase it seems silly to you. There may be a value proposition (and resiliency advantage!) in this service.   

### Elastic Kubernetes Service 

Next up, Kubernetes. 

So I want to clear this up. I see too many people who do not know why the abbreviation is K8s! ***This is the abbreviation of kubernetes because the word has 8 letters you leave out when using k8s.***

***The more you know...🌈✨***

![](https://media.giphy.com/media/l0IsIsuNJly1evlIY/giphy.gif align="center")

Anyway, sorry for the short teaching moment. EKS or Elastic Kubernetes Service, is a service that AWS installs, and manages a virtual control plane for you in their own VPC. This control plane is what does all the container orchestration as well as things like installation and configuration of addons like VPC networking, EBS, EFS, and FSx. Then the user has the option of a few methods of adding in compute nodes. 

- **Managed Node Group** - This is where you make a launch template in EC2 that you can make do whatever you want, then you assign that launch template to a node group. A node group is managed by AWS EKS and it takes rules you make during the setup (such as the minimum and maximum node count) and it manages that group of nodes for you. This is the simplest way to get EKS up and running if you want to customize the OS and instance types. You can use Spot - however you do not put Spot in your Launch Template or EKS cannot manage the node group. EKS & EC2 will take care of using Spot for capacity if you so choose that in the node group setup or API call.  

[Click Here for Docs on EKS Managed Node Groups!](https://docs.aws.amazon.com/eks/latest/userguide/managed-node-groups.html)

- **Self-Managed Nodes** - The next option is managing nodes in EC2, then adding them to a node group you create in the EKS console or API. You then manage all aspects of the nodes. EKS will not touch the nodes, but it will use those nodes to host pods  and applications. You have to make sure also that all security groups and networking is indeed correct and permissions are also setup to allow the nodes to be used by EKS. 

[Click Here for Docs on EKS Self-Managed Nodes!](https://docs.aws.amazon.com/eks/latest/userguide/worker.html)

- **EKS Fargate** - EKS can provision a controller on the control plane just like an addon essentially, and that controller is used to make Fargate API calls to spawn new compute or reduce compute capacity all on its own. You then only have to specify your applications in K8s configuration files, as well as making sure your container images are accessible to EKS so it can download them to run pods. This is a great solution if you want to get your feet wet but do not want to have the added complexity of VPC networking, EC2 launch templates and security groups. If you have devs that want to use EKS, make sure you use Fargate + Spot as the capacity provider. This not only will save money but you can set limits on the amount of compute your EKS dev clusters can provision, and most of the time, the smaller node types can be used for testing and development work, making the total cost per month super small. Just make sure you keep monitoring up and checking to ensure your limits do not get changed!

**Below is a diagram of how these options look:** *Managed Nodes & Self-Managed Nodes Vs. Fargate and how the control plane is setup in an AWS owned VPC*

![fargate-vs-managed](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/08/05/image-58.png align="center")


### Going Back to Basics: Elastic Container Service (ECS)
![ecs](https://miro.medium.com/max/626/1*RmiGt6GAWf4pkO9ohOnRaQ.png align="center")

AWS has one more option for you - Elastic Container Service. This time instead of using Fargate to manage the compute, you now manage it using the same types of options EKS has. You cannot just target EC2 hosts and use those to host containers in ECS, but you can use an Auto Scaling Group (ASG) that you can configure using a launch template and you tell ECS the minimum and maximum size of that ASG which then will mange the nodes for you. 

If you want, you can build your own cluster of hosts out to use with ECS, but honestly, if this is going into production, you should be using an ASG to host tasks becuase if you get hit with a Reddit storm or some other spike, you want to handle it automatically. Manual node creation and scaling takes too long, so let AWS take that on for you. Just make sure you spread out over 2-3 AZs in the Region you choose to operate in. 

I said the word "task". Not container. AWS terminology is task when you are referring to a single instance of a container. However, a task can have many more instances of that task. In fact, I would *hope* you have more than one instance of a task so you have HA in case of some AZ failure or regional AWS issue. If it is a developer task on a dev cluster, it does not make sense to do it, but make sure production is done up right. 

ECS can be a great choice for those tasks that are used a few times an hour, or maybe you only use an ECS cluster one time a day and have an ASG scale that out during that processing hour your devs use to process the days analytical data. There is a container runtime choice for you if you are on AWS today. Take some time and read up on them even more than I have told you about in this blog. You want to make sure you choose right! 


### ECR: Elastic Container Registry 

![ECR](https://d1.awsstatic.com/legal/AmazonElasticContainerRegistry/Product-Page-Diagram_Amazon-ECR%402x.67baf7f72501a65e39af166c83f8364082c7d1b5.png align="center")

So now that we have a way to run our containers, we need a way to *host* them so they are close to our EKS managed node groups. This can aid with spin-up time of new pods, and when you are playing in a game of milliseconds, it is vital that you take advantage of hosting your own containers somewhere is AWS, and the Elastic Container Registry is a great way to do that. **There is a free tier on ECR** - 500MB/Month for 1 year. This is actually a lot of room when talking container images. Oh, and unlike Docker's limits on the number of pulls from the same IP address, ECR resolves that problem. You can pull as much as you want to and you never will get slowed down. 

ECR also has more than just hosting a container in a private or public registry. You can use all the nice IAM access controls built in, you can encrypt container images to ensure they remain yours and not running somewhere else, and you can serve your images via HTTPS which is a great feature when you have a limit of traffic coming into your VPC or even in tightly controlled environments like GovCloud. 

If you have not checked out ECR yet, [click here to see the public image gallery!](https://gallery.ecr.aws/)

## Bottlerocket & EKS Anywhere

Finally, we have [BottleRocket](https://github.com/bottlerocket-os/bottlerocket) and [EKS Anywhere.](https://anywhere.eks.amazonaws.com/)

BottleRocket is the AWS-led open source security focused operating system. AWS and others have been working to build a Linux based, highly secure environment to run containers on. This has been a long term project but today, it has ARM & x86_64 support, as well as something most other platforms don't have: a CIS Level 1 Benchmark. This means PCI/HIPAA/FedRAMP shops can actually use Bottlerocket and pass auditing without a Linux guru making a custom Linux AMI for them to use, and be audited. Those of you that know how limiting these kinds of environments can be will know how good this is. I also want to mention you can see all the different changes the dev team makes to the underlying kernel and OS and this makes custom versions easy to create using the repo I linked above. 

If you're in the market for a CIS backed operating system to run k8s on, this is your stop. 

[Click Here to Get the CIS Benchmark for Bottlerocket]() 

EKS Anywhere is a cool idea but maybe not useful to everyone. If you want to manage all your k8s clusters in EKS and related tooling (eksctl/CDK/CFN) then look at EKS Anywhere. It basically allows you to install a version of EKS locally or on-prem, heck, even in Azure if you want. Then you can deploy and manage it in the AWS EKS console and related tools. If you want to understand EKS read that section above! 

# Conclusion & Final Thoughts


### Determine Complexity Then Choose a Service
You know the needs you have. Do you want or need features? Reasoning here is that you should not lock into a platform or service unless it meets your needs but don't use the next level up as you're going to increase complexity and that will end up biting you later on. Also, understand deployment on the service you pick. ECS does blue/green deployments out of the box with not much effort from you. If you don't have a big or really agile team use Fargate so your life is simpler. That's the thing about containers! You should easily be able to pick them up and move elsewhere any time you need to. 

Just don't lock in to a service because it has cool features. A feature is not ever going to work for you if you can't leverage it. Ask those around you. See what they think. Heck, challange your team to a hack day and see who can deploy an app you own into any AWS container service they pick. Get some real world experience! Fail fast. Move to the next one. 

You never need to be scared to fail and if you are, the culture you're in is bad, and I suggest working elsewhere. 


### The PaaS Advantage

The best part of these container services is the fact they are patched often, and operated by AWS. The agility you gain using services like Fargate on ECS means you can achieve rapid and low cost development with your teams. Want to host a development environment that you can easily change at a moments notice based on compute or other accelerated compute device like attaching and utilizing CUDA cores from a Nvidia GPU? This is your ticket. AWS has covered so many use cases and continue innovating quickly to support more workloads each year. I am looking forward to re:Invent 2022 this year to see what they come up with next. 

If you're interested in trying out any of the services above, there is a free tier you can leverage and get some containers up and going. 

## DevOps with AWS

If you're in management and you're wanting to get your team running on AWS but you're not sure if they support Infrastructure as Code, don't worry. Containers on AWS are first class citizens when it comes to Cloudformation. Most new features launch with CFN support or they add it very quickly. All the things I've wanted or have done were easy to do using my preferred method which is Cloudformation in YAML. Terraform is also available but let's be realistic - that just calls the AWS Golang SDK so it'll be a bit limited until they update the AWS provider. 

Also, make sure you take a look at the AWS Container Roadmap on Github. If you want a feature or want to track a feature so you won't need to develop it on your own, then bookmark the site. 

[Click Here to View the AWS Container Roadmap](https://github.com/aws/containers-roadmap) 

***All of the public roadmaps AWS has are linked on this Github. Bookmark the services you use to get involved and get informed!***

Finally, if you are new to the blog, I would appreciatea follow! I try to write articles I personally want to read, and love to hear how I did or get ideas from readers. If you want to suggest something email me at ideas@aptgetops.tech and I'll happily figure out what we can do.

**That's all this time. Have a great weekend and stay current and curious!**