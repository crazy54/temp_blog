## New SLA Report & Holy Prime Day Statistics!


![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa5d4c397-a782-4767-9415-023193c58997_900x600.jpeg align="center")


Good afternoon or good evening. I hope your Monday has been full of hard work that resulted in no pages, or on-call work. Two real quick things, and some announcements for the site/blog. First, **thank you to those of you subscribing to my newsletter and blog posts.** It helps me really get some useful metrics, and is a firm handshake that lets me know you enjoy the content, and you want more (or less). It is a small action, but it has some real world ramifications to me, as your author here.

The next item up for this out of sync post - I started a public SLA report for the blog, and upcoming services that will be part of my master plan to make Operations content exciting, teachable, and inspire those who come after all of us out there. I know a lot of the higher-end concepts that I learned were in books and blogs like this one, and those little nibbles of the big overall picture are what inspire me to create content that you can get the same thing from. **Anyway,** [here is the link](https://synthetics.newrelic.com/report/PoySpNRiWbB) if you want to check out the SLA report. It covers each operational day, the week, and month we are in. You can also find the link if you forget, on the [About](https://aptgetops.substack.com/about) page of this blog, near the bottom. If I am going to talk about topics like metrics and reporting, I want to share that with you. I think that is fair.

New Feature: The SLA Report
---------------------------

Do not confuse the New Relic SLA report I just linked to above. No, this SLA Report is what the new apt-get ops Newsletter is called. It will be a once a month round-up of the articles that I wrote along with some additional links from various engineering and tech blogs that I personally read. If you do not have time to read one article a week, well, read the SLA Report once a month.

As I see what you, the reader, read most, and talk about most on the site, I can adjust content schedules, what is pushed to you each week, and more. I am not out to spam you to death, but I do want you to get informed, and learn something from me or another author. I love to teach and this platform is what I see as my global education soap box. I can talk all I want, and you cannot stop me. Well, if all traffic stopped, then I suppose you have stopped me. But that will never happen, as. this is all content you want. I promise. I will not email things out that I would not want in my personal inbox.

Before I get to the final item - I **did go ahead and setup paid subscriptions.** Think about it as a method to support my work and ask for more. Paid members (whom I named _**NOC Engineers**_) will get extra personal lessons and more as I flesh out the publication schedule and the regular posts. I promise that I never will charge you to read my work. I strongly believe we have to work together and teach others about our craft so they can do great things of their own. More about this will come later, but it is an option. No pressure. Seriously.

Prime Day 2022 Operational Statistics
-------------------------------------

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc780ab3e-4dcc-4ef8-8749-81fa2f7b8175_725x441.jpeg align="center")

###### The Internet is a Series of Tubes…

So like I have said before, I do work at AWS right now. However, just because I work at AWS does not mean I see the global scale of how much elastic capacity AWS has all the time. Prime Day is a unique time for us at Amazon and AWS to work as a team to make sure everyone on the globe is able to have that perfect Amazon shopping experience they are accustomed to.

[Here is the link to the blog posted](https://aws.amazon.com/blogs/aws/amazon-prime-day-2022-aws-for-the-win/) today (July 25, 2022) about how Amazon used AWS and ate its own dog food to meet those massive expectations of our customers. The quick rundown of the facts that blew my mind are:

*   **AWS Aurora**: 5,326 database instances running the PostgreSQL-compatible and MySQL-compatible editions of [Amazon Aurora](https://aws.amazon.com/rds/aurora/) processed 288 billion transactions, stored 1,849 terabytes of data, and transferred 749 terabytes of data.
    
*   **AWS EBS (Elastic Block Storage)**: The Amazon team added **152 petabytes** of EBS storage. T**he resulting fleet handled 11.4 trillion requests per day** and **transferred 532 petabytes of data per day**. Interestingly enough, due to increased efficiency of some of the internal Amazon services used to run Prime Day, _**Amazon actually used about 4% less EBS storage and transferred 13% less data than it did during Prime Day last year!**_
    
*   **AWS SES (Simple Email Service):** 33,000 Prime Day email messages per second were sent out. That is 1.98 million per minute, 118,800,000 million per hour, and **2,851,200,000 trillion per day** during the Prime Day event.
    
*   **AWS SQS (Simple Queue Service)**: During Prime Day, [Amazon Simple Queue Service (SQS)](https://aws.amazon.com/sqs/) set a new traffic record by processing 70.5 million messages per second! That is a truckload of events to process!
    
*   **Amazon DynamoDB (NoSQL):** DynamoDB powers multiple high-traffic Amazon properties and systems including Alexa, the [Amazon.com sites](https://www.amazon.com/gp/navigation-country/select-country), and all Amazon fulfillment centers.
    
    *   Over the course of Prime Day, these sources made trillions of calls to the DynamoDB API. DynamoDB maintained **high availability** while delivering _**single-digit millisecond**_ responses and peaking at **105.2 million requests per second.**
        
*   **Amazon SageMaker**: If you do not know SageMaker, this is our machine learning platform and it takes care of some extremely large jobs at Amazon and for our AWS customers. The Amazon Robotics Pick Time Estimator, which uses Amazon SageMaker to train a machine learning model to predict the amount of time future pick operations will take, processed _**more than 100 million transactions**_ during Prime Day 2022.
    
*   **Package Planning**: In North America, and on the highest traffic Prime 2022 day, package-planning systems performed _**60 million AWS Lambda invocations**_, _**processed 17 terabytes of compressed data**_ in [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/), stored _**64 million items**_ across Amazon DynamoDB and Amazon ElastiCache, _**served 200 million events**_ over [Amazon Kinesis](https://aws.amazon.com/kinesis/), and _**handled 50 million Amazon Simple Queue Service events**_.
    

As a Technical Account Manager at AWS, I have the pleasure of planning large scale, highly visible (and business critical!) events that leverage our customer’s environment(s) or when they put a new application (or environment) into production for the very first time. These are the kinds of events I would write about here on the blog if they failed, mainly due to horrible planning and poor execution. AWS Enterprise Support customers get this service, which we call [AWS Infrastructure Event Management](https://aws.amazon.com/blogs/aws/amazon-prime-day-2022-aws-for-the-win/#:~:text=AWS%20Infrastructure%20Event%20Management) (IEM). Amazon.com uses this service from AWS to plan and scale every single year in two large IEMs - one for Prime Day, and the other is for Cyber Monday & Black Friday.

These IEMs allow AWS to properly scale out our services across Regions and AZs to better serve customers - so that one customer does not take up all the on-demand resources of that AZ or Region, but also that AWS makes certain our customers get the **same exact care, attention to detail,** and also make sure they are [Well-Architected](https://aws.amazon.com/architecture/well-architected/). (_look for a future blog about [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/) - that will be a fun blog to write!_)

The events AWS help with are done all the time, and range from helping customers keep media online to help you stream it and have a movie night with your kids, to making sure you can order that special deal you have been waiting for on Prime Day each year. No matter what the task is, as someone who helps make these events AWSome, I take immense pride in the fact that we have the opportunity to be part of these critical launches for our customers. I mean it - there are not many other jobs that get you to partner with engineers, operations teams, and more for a single common goal.

I hope you enjoyed this one off post - I never typically write on Monday as there is too much news coming out that I try to read, but it was fun to share the metrics AWS shared today about Prime Day. If you have questions pop them into the comments as I will personally reply to each one.

_**Take care, and try not to fat finger that next shell command!**_