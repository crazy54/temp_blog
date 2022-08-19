## Tech Stories: Best of the Week - July 17, 2022

I wanted to post something different this week. We will resume with the normal tech articles next post, but I want to share the news from our industry since a lot of it goes unnoticed unless you seek it out. Sit back, crack open a cold one, and enjoy these news articles!

* * *

![1900s paperboy memes | quickmeme](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2273b033-9fe2-4e93-8b7e-5deec19acd81_194x259.jpeg  align="center")

* * *

All-Aboard the Drone Highway!
=============================

[Click to Read Article on The Register](https://www.theregister.com/2022/07/21/265km_drone_superhighway_to_launch)

So this article is pretty interesting. Here in the United States, we have places where drones and autonomous cars can be tested and carry people around. ([Click here](https://www.carsthatdrivethemselves.com/self-driving-car-test-cities/) to learn all about those places where cars can legally drive for you)

A majority of the testing done in the United States is done in Nevada, and Silicon Valley. Now, in the USA, _**it is not strictly illegal**_ to have your Tesla drive you in fully autonomous mode but it is not really smart, and it could get the police interested in you if you are seen hands off the wheel watching tv on your morning commute. Around 29 states in the union have legislature in their respective houses trying to settle on the laws and regulations on these vehicles that will eventually replace human error and reduce or remove accidental deaths and injury.

The article via The Register, talks about how the UK has passed laws to set aside 265km or 165 miles of sky that drones can be tested on, and help form the guidelines for tomorrow. There is more to it, as drones or unmanned flights need to have a way to speak with other drones and air traffic control. This is where ARROW comes in - a company called _**Altitude Angel**_ is installing their fully automated beyond visual line-of-sight (BVLOS) drone hardware which takes care of a series of basic technical integrations which, crucially, don’t require specialist hardware on-board the drone. This means that with this system in place, no drone manufacturer has to pay a royalty to add in a SoC or other controller to use the system. Functionally, this corridor is going to be a small window into what automated and unmanned flight will look like in the years to come.

That makes me super excited, and I will be following this very closely to see how well they get these systems to work. Let me know if you want to see more drone/autonomous driving/flying content and I would be happy to oblige!

* * *

Oracle, Google - Can’t Take the Heat. Literally.
================================================

[Click Here to Read the Article on The Register](https://www.theregister.com/2022/07/19/google_oracle_cloud/)

So as someone who has worked in Operations for the majority of my professional career, this makes me _**very curious**_ about how Google and Oracle determine what types of cooling and datacenters are leased to add capacity for the UK and European markets.

As you may know, the world has seen a large and unrelenting heatwave this past week and for the first time in recorded history _**(that is over 360 years in fact)**_ temperatures hit 104 degrees in eastern England. For a country that right now typically averages ~72 degrees, they do not have the infrastructure to handle those temps for days on end. Even things you never would think about - like rails used for the tube and train routes around Europe had far more expansion than they have ever planned for and some trains could not operate safely.

Well, in some datacenters that have contacts with Oracle and Google, the temps made the ambient temps inside rise and keep rising until their cooling systems could no longer help, and fried. This meant that the NOC inside the datacenters had to power the most power hungry and temperature raising gear like SANs, and JBODs and some clusters of hypervisors offline. This meant that the unlucky customers on those machines have had complete service disruption until they can get their evap and chillers fixed, which, is currently not known as to when that can happen.

If interested, check out the Oracle [status page here.](https://ocistatus.oraclecloud.com/#/incidents/ocid1.oraclecloudincident.oc1.phx.amaaaaaavwew44aa7zoskanlspjh4ll6wxhwxrbkbed4d4cnupxexzqzvlyq) _Google has restored normal service in the region as of this being published._

![This is fine Meme | Meaning & History | Dictionary.com](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F14a12415-b2ce-4a97-a128-813fe0f4101b_300x300.jpeg align="center")


##### _**Real Photo from Inside the Google/Oracle Datacenter(s) that Lost Cooling.**_

* * *

Throwing Snowcones in Space?
============================

[Click to Read about AWS Throwing Snowcones Into Low Earth Orbit](https://aws.amazon.com/blogs/aws/how-we-sent-an-aws-snowcone-into-orbit/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1660849549294/8GLYLsx9g.jpeg align="center")


##### _**Photo of an AWS Snowcone 🍧 Captured Aboard the International Space Station**_

I am employed at AWS. There, now that it is out of the way…

This story would have made it regardless if I worked at AWS or not - this is a great story, and it signals things to come. It also shows you what can be done with an AWS Snowcone, which is far more than just sucking up your dataz and throwing it up inside an AWS region of your choosing. Oh no, much more is inside this small package.

The Snowcone from AWS is part of the AWS Snow family. The Snowcone itself is a dual core processor, 4GB of memory, and 14TB of storage you can fill up with AMIs, or personal or company data. It also has an e-Ink display window, which is the same as a Kindle. You can use the Snowcone’s display to get info from it like the IP address or even change it to have a shipping label on it when you are done with the device. Oh, and the Snowcone can be controlled just like an Outpost - you can launch and manage VMs from the AWS console or API.

So this Snowcone took a ride aboard a Falcon-9 SpaceX rocket for the Axiom-1 Mission (Ax-1). To get ready for this flight, the Snowcone went through thermal, vibration, and electromagnetic testing. It was then wrapped up like a baby in [Kapton](https://en.wikipedia.org/wiki/Kapton) tape and sent up to process metadata from images taken by the onboard Nikon cameras.

The interesting thing here is that the crew had issues getting the ML model see and download the files taken by the cameras which end up on the NASA NAS (hehe) and the code wanted all the filenames in capital letters. Turns out they were all lowercase and a new AMI had to be SSH’d up to the Snowcone and begin to process the data. It was able to process one photo every 3 seconds, and another update was made after a few weeks, and researchers SSH’d to the Snowcone once again and uploaded a new Machine Learning model. One thing I have yet to do in my career is SSH into something that is in low earth orbit. Need to make sure that is on my Linkedin as a goal for my next job…

* * *

Uh, Huawei… You’re Too Close! Back That Tech Up!
================================================

[Click Here to Read the Routers Exclusive Article](https://www.reuters.com/world/us/exclusive-us-probes-chinas-huawei-over-equipment-near-missile-silos-2022-07-21/)


![Smartphone with a Huawei logo is seen in front of U.S. flag in this illustration](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6b841ad3-6ac4-4471-952a-021ea60e2e43_4456x2762.jpeg align="center")


##### _**(Photo: Reuters USA)**_

Well here we go again. Huawei has been a big bad boy, and the United States wants to know what they did. There are some U.S. cell towers fitted with Huawei gear, and this gear could (in theory) capture sensitive information from military bases and missile silos that the company could then transmit to China. Electronic warfare at its best! The current Biden administration is so worried in fact that they are investigating the matter very closely.

In the article, someone who wanted to remain anonymous _(also known as not wanting to die in a Chinese interrogation)_ said that Huawei could obtain sensitive data on military drills and the readiness status of bases and personnel via the equipment. Well, now that is some quality gear there Huawei!

This leads me to a subject a little off topic, but related, and important. AWS has built all of its own infrastructure over the last decade and a half, even pushing fibre density higher than previously thought possible. AWS does this becuase our customers want an end-to-end solution, and being inside the AWS network gives that to you. Once you enter the AWS network from the edge, you literally never leave again unless you have to. In fact, you have seen how Private Link and private endpoints have taken off as they improve security in your VPC, do not require a NAT GW to get traffic into another service, but they all are on the AWS backbone which is unparalleled in speed and reliability. That is another post for another time though. Back on track.

When asked, the Commerce Department said it could not "confirm or deny ongoing investigations." When Huawei was asked about this, of course they would not spy on the United States using their networking gear. [Except for that one time](https://www.wired.com/story/huawei-backdoors-us-crypto-ag/) when they used 5G network infrastructure to spy on the USA [and Australia.](https://www.bloomberg.com/news/articles/2021-12-16/chinese-spies-accused-of-using-huawei-in-secret-australian-telecom-hack)

That’s it. Those are the four stories this week that you should check out and get informed by. Let me know if you liked this article, and want to continue to see more like it mid-week before my normal Friday Ops post. I like to read and I am a huge Slashdot.org fan, so I am always in the know.

Have a happy Fri-Yay and I will be posting new content next week!

![wolf of wall street friday meme](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F9aa78553-0d25-40eb-ad0c-ff9cbdf4738f_1200x772.jpeg align="center")