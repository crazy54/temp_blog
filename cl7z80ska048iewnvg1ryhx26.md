## Computational Storage: What Is This?!

## What Happened?

The **Storage Networking Industry Association** (SNIA) has completed the very first official specification of a new breed of storage devices. If NAND chipmakers can innovate at the rate and level they have expressed, boy, we're in for some truly new bits of kit that will change compute as much, if not ***more so*** than when the first solid state drive was introduced back in 1995 by the Israeli firm **M-Systems**. They launched the modern flash-based SSD with its Fast Flash Disk (FFD-350) series that used the 3.5 inch form factor, which is why it was named FFD-350.

Enter **CSxes:** **Computational Storage Devices**

A computational storage device is pretty much what it sounds like - take the latest NAND storage and add an application-specific integrated circuit (ASIC) to it. Why? This allows the CSxe to obtain the file or files your CPU wants so it can perform whatever operation was made by the user. Once the file has been located by the SSD, it would then send it into the local cache of the drive, then the drive forwards a copy onto your memory. Once in RAM, the CPU can take the file or files into its internal low level cache and do what it needs to. Once finished, it performs the same thing but in reverse. The SSD then takes out the new version of the file from its cache, and writes it to the internal NAND flash, and it records what the file is and where the file is located so it can be called up next time. 

CSxes change this entire workflow up: no more will you always have to move files into cache then into RAM, then the L3 cache of the CPU. CSxes have an onboard computational chip made for data manipulation. This enables the drive to retrieve the file you need, and perform all of the operations needed right on the drive's ASIC. This speeds up the entire transaction from start to finish, and it is going to change storage yet again for the enterprise, then us consumers. For the gamers out there, these devices will allow you to stream texture bundles directly from the drive to your GPU, no more CPU bottlenecks to worry about for open world games. Well, at least on the texture rendering side of things. 

Before we go deeper let's look back quickly at what got us to this point.

## Storage N-AND You

![ssdgif](https://i.makeagif.com/media/7-09-2021/zSxIqH.gif align="center")

For those reading this, my bet is that a good majority of you remember the first time you installed and used a solid-state drive. The speed it offered at the time was far more than paying $3-500 for a new CPU. SSDs launched when the GHz war was on fire with large jumps in single core performance and the AMD launch of 86-64 (aka x64, AMD64) architecture. Other people may have other memories, such as putting an SSD in a passed down old laptop or desktop - and that SSD provided not only faster loading times, but a cheaper way to gain a lot of performance very quickly.

NAND gave us a new way to think about data and how data is stored as well as accessed. This upgrade came with numerous benefits like:

- Larger queue depths and deep queue increased performance
- NAND Flash caching devices
- Exponential Growth: Huge appliances with hundreds of thousands of IOPS were available to large (and small) businesses with higher performance with lower total cost of ownership. 
- Lower cost: Consumer SSDs brought innovation and competition to shrink the transistor gate size while growing all other performance metrics
- Smaller form-factor notebooks and desktop workstations as well as home PCs
- Lowered reliance on CPU and memory for overall performance - storage became a hot commodity
- Gaming Console Performance: NVMe Disk APIs Allow Direct GPU Access

## Next!

Computational storage devices are going to bring a similar revolution to the enterprise and consumer space. For the enterprise, imagine entire SANs with 360 CSxes grouped together. This will also mean that with CSxe's we will likely see smaller controllers or head units needed since the ASICs on the CSxe can perform data manipulation right on the drive without the need to pull it into a head unit and then write the new values out to storage.

One particular enterprise compute team is going to love these: DBAs. If you are a DBA today, my bet is that you've had to clean drool off your face about 5 times thus far while reading the article. DBAs will no longer have to worry about available compute for each 45-inner-join long query they want to run in the middle of the day. **Samsung has announced that they have seen MSSQL improve up to 40x on their CSxe** 🤯

## Standards

The SNIA made these standards for one simple reason: encourage interoperability between the various CSDs currently under development, but they also want to ensure workloads like work done by web developers and application developers (and DBAs) also can work on the ASIC onboard the device. One thing they also have to think about is how ***multiple devices can work together if data is spanned across them*** - which one does the compute? Do they both scrape and stream data? 

These are the types of things standards have to think about and challenge. They are also there to make sure that each hardware producer can play nice in the sandbox of your computer. If no one made these standards, nothing works right and the cool drives you install never work the way they should. That would be a bummer. 

## CSD or CXxes?

![fight](https://www.ipswitch.com/images/default-source/blogs/ssds-vs-hds_-pros-and-cons-of-each-1024x512-1.gif?sfvrsn=3b5fdd11_6 align="center")

You may have seen another name for these devices - Computational Storage Device (CSD).Essentially, CSDs and CSxes are the same thing, but there is one thing we have yet to talk about. Some of these CSDs or CSxes will utilize external or close by PCi-Express compute cards. These standards make sure both types of device follow the same rules, so even though large SANs may use controller ASICs and separate compute devices, they will still be far faster than what we use today. 

TechRadar.com did an interview with Western Digital and asked their project lead about use-cases and what is going to improve for specific workloads professionals and gamers will throw at these new compute storage devices. 

> “In the context of storage, we can think of applications like video transcoding, compression, database acceleration as falling into this category. A video transcoding device closely paired with a storage device can allow a video server to more efficiently stream content at many different quality levels while minimizing unnecessary I/O and data transfers throughout the system.”

##  Putting it All Together

The most complete sentence to put together what was announced and what devices *really* are, is David McIntyre, who chairs the computational storage special interest group at SNIA. He said:

> "The 1.0 Model has a nice baseline on definitions – before this there were none, but now we have** Computational Storage Devices (CSxes)**, **Computational Storage Processors (CSPs)**,** Computational Storage Drives (CSDs**), and **Computational Storage Arrays (CSAs)**, and ***more***,"

One thing I think is awesome is the ***more*** phrasing. This means the standards put forth in the 1.0 SNIA Compute Storage Device paper has room to grow and add even more. Think of this as when any new WiFi standard was announced. You have the brands that put out 1.0 devices that never get the full support becuase the hardware changed mid-lifecycle, and you have the quality brands who wait for the standard to no longer change hardware specs, and the rest of the changes are done in firmware. You will pay hundreds if not thousands of dollars for a mesh WiFi 6 setup ([Yeah, looking at you Linksys](https://www.linksys.com/tri-band-ax5300-mesh-wifi-6-system-2-pack/MX10600.html)) or you can wait for eero to put out Wifi 6 gear that maintains most of the standard and can update once the final specs are out. 

I personally cannot wait to see how computational storage changes our Web3.0 world that is ever-changing and growing. We need a boost in performance now that our processors are only moving into the smaller 4nm and 7nm processes and the TDPs are lowering but performance overall is not a generational change. I strongly believe that these devices will be just like the SSD you installed in your mom's laptop in 2009. Maybe by then the disk will have tensor cores and be able to use AI to support her questions... 

Thanks for the read. Make sure you check out https://aptgetops.tech for more news and more Ops based content. Email me at [ideas@aptgetops.tech](mailto:ideas@aptgetops.tech) if you have any article ideas or want to make a post together! 