## Trends in Cloud Customers Today

![Image](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1661019f-7c46-4a5e-9880-f3303ab73f74_1346x427.jpeg)


* * *

Get on My Level
---------------

Most customers I deal with in my job are just about average when it comes to how they operate on the cloud, their DevOps, FinOps, and development teams all have their roles and functions and they do enough to make things run well. They move on to the next task without thinking about the task they just finished until their manager yells at them about it, or the NOC senses a drop in site/app availability.

I never see developers thinking about cost. They let the architect and systems engineers decide all of that. Developers should do what they are best at - which I hope for most is developing applications that take low levels of the compute stack into consideration. However, with the most popular languages in use today (_See Chart A)_ being very abstracted from their underlying compute and runtimes, who needs to worry these days about clock cycles and how to make the most out of every CPU clock cycle? Heck, most Python I see is not even Async or Multithreaded anymore - single threaded compute speeds and floating point calculation is at levels I only dreamt of when I was little. I have worked with new developers who have no idea how a computer fundamentally works. How they progress up the ladder is something I have no idea about.



![](https://cdn.hashnode.com/res/hashnode/image/upload/v1660849552832/R-ufQRaVit.png)


        Chart A - Most Used Languages via Pull Request on GitHub (Q1 2022)



![](https://cdn.hashnode.com/res/hashnode/image/upload/v1660849554052/oJW4KqrsR.png)


                Chart B - Most Used Languages Plotted Out (Q1 2022)

There is a large amount of overlap in the roles most enterprise customers have today. For instance, take FinOps - just like anyone that works on their companies DevOps team, they want to tag resources so their forecast and spend review reports are nice and simple. However, you need to work with your DevOps team to have the right tags added into the Infrastructure as Code (IaC) source code and wait for the next deployment to get those resources tagged.

Those same DevOps folk will have to work with the SRE/NOC/SysOps team to get tags setup for monitoring, and so the resources that serve up every microservice/application/service can be monitored with the entire stack as one swim lane. Think about a swim lane as your _**application’s path in**_, from the internet or customer site: you enter at an edge device which sends you to some method of SSL/TLS termination then from there you get handed over to a server or serverless compute response from a database/webserver. Also you have to map multiple microservices as one large application or service.

I have seen more people come into the tech space that have no idea what they are doing becuase companies want warm bodies to fill their headcount up, training can resolve all issues - right? No, but it helps. You cannot teach someone to modify the way they think unless it is done over a long period of time, and you have to give them material and tasks that re-enforce that way of thinking. As more jobs open up, the quality of the available workforce goes down, and down, and down. Those Reddit posts you’ve seen where someone is lip sync'ing for a video interview? I had it happen to me. It is far more common than you can imagine. Just one more thing to worry about and look for during the interview process.

Site Reliability Engineering - The “Hot” Ops Role
-------------------------------------------------

Not only do hot tech words come and go, it seems like job titles do too. [Google has literally written the book on site reliability engineering](https://sre.google/sre-book/table-of-contents/). The big bad 600+ pager is likely my most read over and used book in my collection. The content in the book is a must read for anyone in current day operations. I would bet my 10 year old self that if that book was available to me it would have been my pandoras box of information.

If you have not dove into that operations bible, it is able to get downloaded in PDF/eBook format for free but I suggest you pay a bit, [and get this bundle](https://www.amazon.com/hz/wishlist/ls/3QEMW4VPQ95LV?ref_=wl_share) - it has the paperback book from O’Reilly Publishing, plus the workbook that was dropped a few years ago by Hulu, Pinterest, and more. Finally it has a newer book called “Seeking SRE” and it covers even more about how SRE has changed since those other books came out. It takes you into the hot topics SRE teams around the country are having to figure out, and how they solve for their problems.

> _**“Inspired by that earlier work, this book explores a very different part of the SRE space.**_
> 
> _**Listen as engineers and other leaders in the field discuss different ways of implementing SRE and SRE principles in a wide variety of settings; how SRE relates to other approaches like DevOps; the specialties on the cutting edge that will soon be common place in SRE; best practices and technologies that make practicing SRE easier; and finally hear what people have to say about the important, but rarely discussed human side of SRE.”**_

If you are a manager, get your team to read a chapter each week. Then, have a huddle Friday afternoons and talk about the chapter. You will see how it changes the thinking of your team(s) faster than you think. I got so involved with the book I read it all in one week. I was able to apply the things I learned instantly and was promoted for it.

Think of this as _**‘Reading Rainbow’**_ for adults.

Personally, AWS has offered me things that no other employer ever has before. I stay plugged in, and learning so much as part of my normal working day, that I never want to do other things. I typically have moved to new jobs ~1.5-2 years as I fix everything, get bored becuase I am not learning anything new, and my ideas to improve things around the environments get denied by management. You do know that technical debt is still doing work right? 10 hours of fixing some rushed project is just as important (sometimes more so really..) as getting new features out to customers. Tech debt just is not flashy to shareholders.

Anyway, that wraps up this blog. It ended up being more of a rant, but I think it is important to call out things for what they are: buzz words, flashy shiny thing that will be laughed at in 3 years. It’s time we start working on ourselves, our old code, and improve it. After all, it can save you a headache, or even getting fired when your DR scripts fail in a real world failover. I think it is better to go back and fix stuff up, or learn something new and implement it so others can benefit.

I promise next week I have a great topic coming up and a long juicy writeup. Take the last bit of time in the home or work office and teach yourself something you can use come Monday morning after that first standup of the week where you want to go back to bed and shove tons of coffee down your mouth-hole.