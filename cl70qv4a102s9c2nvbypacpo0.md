## NVMe Controllers: The Next Big Performance Upgrade for the Enterprise & Consumer

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1559c7e6-48f7-45d4-9a5e-daeb7ff6588e_1125x750.jpeg align="center")


**Happy Fri-Yay** everyone. Sorry that I was a day late on this post - this week was my 9th wedding anniversary and I spent time _**away**_ from the internet and computer and I only am posting today, and maybe tech updates over the weekend. As I try to get my writing schedule worked out to provide everyone new, exciting and useful information while keeping my quality high, I have found myself getting more and more ideas for not just content, but ways I can connect with y’all that read my content. As any community on the internet can tell you, without any kind of communication to and from the leader(s) no one will get their ideas evaluated and implemented. I want to really encourage you to comment on and like my posts. This allows me to see what content resonates with you, and which ones do not. I would also suggest things for me to write about - you can leave a comment with your idea, or email me at: **ideas@aptgetops.tech**

New URL
-------

You can now use the url: [aptgetops.tech](http://aptgetops.tech) to come to the blog. As I begin building traffic and users, I will be moving towards using that domain for everything I do. Feel free to reach out and send ideas, collaborate with me, or maybe do a podcast sometime. I am always open to doing work with others to increase visibility. Creative folks never get much credit, but I do it for the love of tech, not views or subscribers. As I have always said, my content is 100% open source and free. No paywall here.

What’s in a SoC?
----------------

Let’s jump in - last week I posted a great article about hard drives and how to look at performance, IOPS, read/writes, etc. ([click here to see that post](https://aptgetops.substack.com/p/its-all-about-the-iops-baby)) and in one section I was talking about NVMe drive controllers. One reader told me that this made him very interested in the subject and I agree - **System on a Chip** (**SoC**) and **application-specific integrated circuits** (aka **ASIC**) are microprocessors created to do one thing, all day, and do it REALLY REALLY well. Let’s take the M1 Apple chip. That uses the ARM processor architecture, but that is one bit of the SoC. Technically, the Apple M1, Apple [iPhone SoC,](https://en.wikipedia.org/wiki/Apple_silicon#Apple_A15_Bionic) called the A15, and all Apple silicon are all Systems on a Chip. Why is that? Well, to put it simply, an SoC has a central processor like a CPU or central processing unit, but it also has a graphics chip to let you play games on bathroom breaks at while at the in-laws. It also has a chip to store your faceID and finger prints so they can be used to buy apps, pay for Starbucks, or whatever else you can pay for on your phone. These devices are made specifically for Apple, and they have a massive workforce that design, optimize, and work on production FABs to get these chips made and sold to you in your next product. If you want to learn more about Apple Silicon, [check this out](https://en.wikipedia.org/wiki/Apple_silicon).


![](https://cdn.hashnode.com/res/hashnode/image/upload/v1660849538560/5wBqkrrcL.png align="center")

Global smartphone application processor (AP) and system-on-ship (SoC) chipset shipments for 2020 and 2021.

Qualcomm is by far the most used SoC package to date in the United States and they continue to improve at rates [Intel’s Gordon Moore](https://www.intel.com/content/www/us/en/newsroom/opinion/moore-law-now-and-in-the-future.html#gs.88lzln) could not even imagine. The largest share of the SoC mobile market is held by a company you likely have never heard of - MediaTek. They are contracted by almost every single phone manufacturer in Asia, and due to the population and availability of phones in that region, they are everywhere. This same thing goes for Qualcomm in the USA and Europe. Samsung and Apple bring up the rear. Apple’s ARM based M1 and M2 chipsets are making huge waves in the creative userbase thanks to Apple designing their SoC specifically for the workloads their userbases actually perform every single day. This is why Apple controls the OS all the way down to the tools used to fix broken phones. They want their users to never have to learn what a Ghz is, what memory to buy, how much storage they need - they make it a seamless experience. In fact, I would likely buy an iPad or Chromebook if I needed a laptop today just for use at home.

More Power
----------

The power mobile SoCs have today greatly surpass technology that landed man on the moon. In fact, the SoC in your flagship phone likely can do more per clock cycle than a laptop from 2018. Qualcomm’s Snapdragon 8cx Gen 2 5G SoC actually has better performance than some laptop CPUs - if you want to see the list of all the CPU/SoC benchmarks, [check out this link](https://www.notebookcheck.net/Mobile-Processors-Benchmark-List.2436.0.html?type=&sort=&deskornote=2&or=1&showBars=1&showPercent=1&cinebench_r15_single=1&cinebench_r15_multi=1&cinebench_r20_single=1&cinebench_r20_multi=1&wprime_32=1&wprime_1024=1&x264_pass1=1&x265=1&blender=1&7-zip_single=1&7-zip_multiple=1&geekbench4_1_multi=1&geekbench5_single=1&geekbench5_multi=1&geekbench5_1_single=1&geekbench5_1_multi=1&webxprt3=1&cpu_fullname=1&codename=1&l2cache=1&l3cache=1&tdp=1&mhz=1&turbo_mhz=1&cores=1&threads=1) - I made a table which contains them all in order, and I think you will find it pretty enlightening. Most folks do not think about their phone much, but with the amount of power in your pocket can do things you’ve never dreamed of. Why do you think most malware on mobile devices runs bitcoin mining operations, and other floating point based jobs? Well if you are not using the processor, someone else will do it for you. In the list of benchmarked CPUs, around 350 is where it gets really interesting. You begin to see Apple/Qualcomm SoCs and ARM processors -and they have similar benchmarks to the following laptop processors:

1.  **Intel Core i7** (Haswell) 22nm process and runs up to 3.2 Ghz
    
2.  **Ryzen 5 2600H** (Mobile SoC released in late 2018) 3.2Ghz Base & 3.6Ghz Boosted 14nm process
    
3.  Apple’s own **A12z Bionic / A14** - these are 7nm chips! They run up to 2.9Ghz
    

The list goes on and on - but the fact we carry laptops around in our pocket should blow your mind each and every time you do something as simple as sending a text. Leave a comment with the most _**compute or graphical intensive workload you perform on your phone.**_ I want to see how engineers take advantage of these complex and performant SoCs.

FAB!
----

In case you have not read up on chip manufacturing and FAB technology lately, (sorry, a FAB or Fabrication plant is where processors are born) Samsung, Intel and Globalfoundries are the main places or FAB owners to get CPUs/SoCs/ASICs made. The way this works, is that you go shop your ideas around, in this case, let’s say we have an ARM based 14nm processor I want to build. You have to explain how many you want, how long you have until you go to market, and the number per week you need to hit that target. It takes on average, _**14-20 days for a single CPU to be fabricated**_. If you want to understand more about this process, check this awesome video out from LTT: [Linus Tours Intel's FAB in Israel](https://www.youtube.com/watch?v=2ehSCWoaOqQ&ab_channel=LinusTechTips) . Once you enter into an agreement with the FAB, you have to wait for finished units to come to you and then you can begin to manufacture devices. Some companies like AMD and Intel make the CPU and the supporting chipsets - but allow motherboard manufactures to make the layout and features on their products. The same goes for mobile phones and you can see how Apple, Samsung, and even Google Pixel devices come in multiple performance tiers that allow their customers to pick what they need most.

Future of Storage
-----------------

So what does all this have to do with storage controllers? Well, the direction we are heading with storage (and it has already happened) is putting an SoC or ASIC onto the device itself and _**use that compute to manipulate data on the drive’s on-board cache or DRAM.**_ Samsung now sells enterprise drives with this technology and it will only be a matter of time until they move to consumer storage devices. I talked in my last post ([All About the IOPS Baby](https://aptgetops.substack.com/p/its-all-about-the-iops-baby)) about how PCI Gen3/4 allow Microsoft’s Xbox X|S products and supported Windows 11 devices to use a new DirectX API that lets game devs drag data off the hard disk into processor cache and that speeds up processing times immensely.

Taking that concept, imaging the enterprise in a few years from now, I can see storage having removable and replaceable processors so you can keep the amount of storage you have, but you can upgrade the compute power that drives it. Think about how you can upgrade memory today in a NetApp SAN, and replace the headunit to get more performance and HA features from your arrays. This will be made much smaller and becuase Intel/Samsung/GlobalFoundries have 7nm/14nm processes available, they will be power efficient, and produce less heat during operation. This will improve reliability and total lifespan of the devices. Storage is going to get real interesting real quick.

So, What About the Home User?
-----------------------------

**Glad you asked.**

Today, the latest greatest drives are powered with what are called NVMe drives, also known as: NVMe™ (Non-Volatile Memory Express). This basically means Non-volatile memory (NVM) or non-volatile storage is **a type of computer memory that can retain stored information even after power is removed from the device.** Memory or RAM (Random Access Memory) is actually classified as volatile memory becuase when you power off a computer, everything stored in memory is lost. RAM needs power to be applied to the individual gates to form 0s and 1s. When you turn off your computer, all those gates close and no more data is stored but your hard drive made up of similar memory NAND modules, is able to retain the [transistor gate positioning.](https://en.wikipedia.org/wiki/NAND_gate) This is critical as all the data you have comes down to those transistor gates staying put.

You want to stay away from cheap SSDs. Trust me and [trust this blog](https://ramblingpolymath.com/2021/07/be-wary-of-cheap-hard-drives-and-ssds/) that talks about DRAM/HDDs/Issues with cheap hardware. Why should you spend extra money on high performance disks and flash storage? For one, they will be faster, but they also have backup systems on board to help fight data degradation, and the ability to finish writing to flash during a power outage/event. This goes for platter/magnetic drives and flash based M.2 NVMe and 2.5” SSDs. Look for storage that contains DRAM chip(s) on them, or read reviews to figure out if they do have DRAM on them. This DRAM allows drives to have space to put files it has not written to a block yet and if there was some power issue, it would likely be able to store that file anyway. Stay clear of devices with no cache, or DRAM. It is worth the money, so just pay the $10-30 bucks it will cost you and get the better product. Also, DRAM has one more feature I spoke about in the last blog - it keeps a drive map of where files are and how worn out each block or cell in the flash memory of the hard disk is, so it can help evenly wear out the flash evenly - otherwise you would lose big chunks of storage randomly and not be able to use 10% of your SSD. It’s important stuff, but it is a small detail.

Why NVMe? SSDs Are Fast…
------------------------

Yes. They are kind of fast.

NVMe was made when flash began to hit speeds that, at the time, saturated the SATA / SCSI bus, and something else was needed to solve the bandwidth problems. Enter NVMe (Non-Volatile Memory Express) - a special type of flash which is called NUMA, or [Non Uniform Memory Access](https://en.wikipedia.org/wiki/Non-uniform_memory_access) which basically means that it is flash memory which is made to be used with random access in mind - such as in consumer pcs and in huge SANs for the enterprise. CPUs first came out with NUMA enabled back in 2003 for AMD and by 2007 Intel joined the NUMA game. This made the building blocks to enable NVMe drives for the enterprise and consumer markets. NUMA allows enterprises to actually have CPU 1 read CPU 0’s memory and vice versa. Home computers do not really use NUMA like this - but they could if you had the workflow or VMs to do it with.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1660849539666/aXHB48NOR.png align="center")

###### `This figure shows NVMe hooked to the PCIe Bus vs the SSDs that are controlled by the HBA.`

If you want to read more about drive controllers at a much lower level than I talked about above, please [check out this blog](https://www.cactus-tech.com/resources/blog/details/solid-state-drive-primer-7-controller-architecture-basic-overview/). It dives headfirst into how these really cool chips work, and how they determine performance of the disk.

The Stuff You’ve Been Waiting For…
----------------------------------

AMD has an awesome bit of kit called [XiLinx platform](https://www.xilinx.com/applications/data-center/computational-storage/smartssd.html). This is the worlds first “compute on disk” platform. What is that you ask? This allows anyone that makes SSDs or NVMe drives to integrate this tech onto the drive as the controller. Then, using voodoo and magic that I won’t bore you with ([you can see it here](https://www.xilinx.com/applications/data-center/computational-storage/smartssd.html)) but I can explain an example workflow it can help out with. Say you are executing a SQL query on a MSSQL DB and you have a normal SSD. Typically, SQL will tell the CPU to recall the data from the SSD, the SSD controller tells the SSD what is needed, the SSD then locates, and sends that data through the HBA/Controller to the RAM of the machine, and then the CPU sucks it into L2/3 cache to use the data, and it spits data back out. That data goes back the opposite way, the whole process in reverse. Whew!

Well now, this compute on disk allows the drive to recall the data, process the query on disk, and send the result to the CPU directly - right into L2/3 cache and memory. The CPU then is able to move onto the next task. This has allowed Samsun to claim 70% performance gain using 50% less power! Can you imagine what this could do for computers down the road as our storage becomes faster and faster? If SQL can get sped up that much, what about game loading? Processing huge machine learning datasets and improving the models that they power. This could completely change the way cell phones are looked at - same with tablets. The world of storage is one to keep your eye on. It is speeding down the highway like a bat out of hell. CPUs have peaked with core/thread counts, and clock speeds. Now let’s see the storage catch up and make our systems far more speedy and enable these typically highly costly and power hungry tasks to shrink down into our pocket, and you can train and manipulate a neural network on your mobile device. The future is here, and it is FAST.

**PS: [Check Out TechRadar's Post on the Samsung SmartSSD here](https://www.techradar.com/news/samsungs-newest-ssd-is-unlike-any-youve-come-across-before)!**

Thank you for the read! Check out the next blog when I talk about how some of the biggest failures happened to me and what I learned from failure. Trust me, I am not looking forward to spilling my mistakes out on the internet, but hey, someone out there can learn from them, and I hope they will. Catch y’all next time! Have a super Saturday!