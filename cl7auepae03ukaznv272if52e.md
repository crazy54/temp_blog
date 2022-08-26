## This Week in Tech News: Week 34 2022

Welcome to my first official post on the new blog! Welcome, and I hope you are enjoying the speed and consistency of the new website. I do plan on setting up some custom CSS to go long with my dark and light logos, but for now things are stable, and articles are now flowing again. 

If you have tips on a story you want written, or want to write a guest article, send all ideas over to me at [ideas@aptgetops.tech](mailto:ideas@aptgetops.tech)  

Now on with the show. 

## T-Mobile & Space-X Combine Forces: In Late 2023 T-Mobile Phones Will Access Spacelink Satellites (No Dishy McFlatface Needed)

![StarLink](https://www.androidauthority.com/wp-content/uploads/2020/07/starlink-logo.jpg.webp)

Well no one saw this coming - and I mean literally no one. 

Elon and T-Mobile have penned a deal allowing the low earth orbit constellation of Satellites called 'StarLink' to  provide data service to compatible phones on the T-Mobile network sometime next year. The data will help to reduce the 5G towers T-Mobile has to deploy and will offer text messaging network data, but in the future, T-Mobile wants to have their customers use StarLink as a backup 5G network with high data speeds in the entire United States of America, Puerto Rico, and US territorial waters, starting with a beta in selected areas by the end of next year.

Yes, even parts of Alaska and Hawaii will get this great bit of innovation, which will actually be a huge help as both of those states have a severe lack of cell antennas and service. If I was in those areas, I would be ready to see how this pans out and how well the service works. If the cell phone service is as good as most internet users of Starlink suggest, it is going to end all complaints of poor signal strength and quality. The one thing that is going to be hard, especially in places such as Alaska, weather such as low cloud cover and rain/snow can really reduce the signal strength to home users **Dishy McFlatface** *(this is really what the SpaceX/Starlink direction manuals and warranty books call the dish home users of Starlink setup.) *

![Dishy McFlatFace](https://cdn.shopify.com/s/files/1/0173/8204/7844/articles/9606A885-460C-46E1-93FF-388599F7C3D8_1600x.jpg?v=1603907160)

That is not the end of the story. Oh no, not at all.

The two companies said that after this is up and running they plan to extend support to voice and data coverage, which is something you would assume. However, they also said that they hope to expand Coverage Above and Beyond globally by working with other global carriers. This is something for all of us to get excited about - this means it is not an exclusive agreement, and your phone ***could*** leverage Starlink in the future when you do not have a perfect 5G signal, which believe me - no one has these days. 

The promise of 5G data speeds are fantastic and I really want to see carriers succeed at the rollout of 5G, but because of the signal wavelength *(1 to 10mm)* and operating frequency *(28 GHz and 39GHz is where 5G mainly operates)* you need far more towers to really make a dent in the 5G signal quality for metropolitan areas. I even remember a few years ago when Verizon deployed the first mmWave High Band 5G site in Chicago and invited the press and bloggers to come out to try it out. What a show that was - using phones given to them by Verizon, they stood outside on a corner trying speed tests over and over, but the signal was so bad, not much was seen. What are the 3 types of 5G? Glad you asked. 

- **Low Band 5G** - This is basically the baseline and most common form of 5G. You can imagine this as the widest coverage, coast to coast in the USA. This is what you get on the highway in the middle of nowhere. It is around 4 times faster than 4G ***(in optimal conditions)***
- **Mid Band 5G** - coming in at 6 times faster than 4G networks, mid band 5G is currently getting deployed to major cities in the USA/Canada/Europe. This is what companies like to promote and sell you home internet on. 
- **mmWave High Band** - Finally, we have the king of 5G network signals, and the one you likely never will get near you. Harsh, but true. Why? This type of signal is so hard to spread over distance, since it is the highest frequency but it also has a wave that cannot be thrown far and requires a huge number of towers to make a blanket of coverage. it will not penetrate far into concrete, steel, even glass so this poses huge challenges in metropolitan deployments. However, with all the bad, comes the best 5G speeds you will ever see. It is rated to be around 10x faster than 4G networks, which, is up to 10Gbps. Most towers will not even have a 10Gbps connection, so I would not hold my breath for this for some time. However, once available, it will be super cool to have those speeds in your pocket!

<center>[Click Here to Read More on TheRegister.com](https://www.theregister.com/2022/08/26/tmobile_spacex_phone/)</center>


## Cloudflare and Twilio are Just Two of 135 Orgs Targeted by the Oktapus Phishing Campaign

<center>![Octopus Phishing Attack](https://cdn.dribbble.com/users/45541/screenshots/10572233/media/73a2bfc24d0334ba9e85e0eb8476179d.jpg?compress=1&resize=800x600&vertical=top)

Well, another week, another security story. 

If you are not a person who normally cares much about security, well, that ship has sailed. If you are online, you need to care and you need to keep your ear to the ground to learn about the latest in security attacks and if you want to keep you and your family safe, learn how to avoid them, and understand how to check an email header to see if the sender is legit. Attacks are getting too sophisticated and too common to not actively understand what is going on around you.

**Oktapus** is a phishing campaign that looked to have the intended victim open an email and navigate to links that were customized to mimic emails the intended recipient normally would send or recieve on a daily basis. For instance, Okta got emails for SSO logins and MFA approval. These emails are getting to be insanely intelligent and hard to spot unless you know exactly what you are looking for. The best method for checking any email is to view the HTML and/or message headers to see whom sent the email and the reply-to address. You can also pop the HTML into VS Code and see all the links to graphics and other resources. If they are not from the sender on their domain - something is up and you need to report the email ASAP to your SecOps team or TechOps team at your company. If they came to your personal email, report them here. 

You can also forward these spam emails or phishing scams to the Federal Trade Commission by attaching the email and sending it to: [spam@uce.gov](mailto:spam@uce.gov)

If you want to learn more about this attack [check out the full article here.](https://www.theregister.com/2022/08/25/twilio_cloudflare_oktapus_phishing/)

## IPv6 - Over Two Thirds of IPv6 DNS Requests to Chinese Servers Fail to Resolve

![China ASCii](https://s3.us-east-1.amazonaws.com/files.cnas.org/title/China-code-flag-cyber-IT-computer-quantum-Hero-GETTY.jpg?mtime=20181220141306&focal=none)

Well this comes as no surprise, but I did find this an interesting read. China is one of the most active countries on the internet (judging by the number of users anyway) followed up by India, the United States and strangely, Brazil. Below are the estimates from the US Government: 

1. **China **= 765 million
2. **India **= 391 million
3. **United States **= 245 million
4. **Brazil **= 126 million
5. **Japan **= 116 million
6. **Russia **= 109 million

Anyway, that is a ton of traffic that is generated, and as such, DNS is the cornerstone of any internet based application or website. When you hit a DNS server or nameserver, you expect, no: demand the right IP address to be given to you so you can continue on with your day. China is saying no to that thought process and instead of getting your AAA record an ip address it fails or times out. Seems China either hates IPv6 or has not had the Great Firewall of China upgraded yet. 

A research paper titled "A deep dive into DNS behavior and query failures" said that they found the following items:

-  **86.2%** of queries were for **A records** – the record for a resource with an IPv4 address
-  **10.4%** were for **AAAA records** that point to resources with an IPv6 address
-  **93.1%** of queries for** A records succeeded**
-  **35.8%** of requests for **AAAA records succeeded**

I found this to be pretty interesting - I am curious if the government there is trying to blackhole requests it has not yet setup filtering for, so instead of passing an IPv6 address back to the user, it just blackholes the request to /dev/null and everyone moves on with their day. Essentially you cannot use IPv6 in China. 

Here is the report that was generated:   [Click Here to See a Copy and Learn the Details](https://www.sciencedirect.com/science/article/abs/pii/S1389128622002511)

## Let's Drool Together!


![image-removebg-preview.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661539056357/6phdW91iO.png align="left")

Samsung makes a lot of things. Specifically, Samsung Display. For years, smart gamers such as your humble author, have asked for an OLED display so we would have not only the best HDR on the planet, but power savings that are really heat savings. I have dual 30 inch IPS displays (**One is 165Hz and the other is 144Hz - right now one is on top of the other. Both are 1440P - the magic sweet spot of gaming.**) LG is known for their OLED display technology and they are some of the best on the market. I have a 65" OLED for the main display in our living room. It can really change the way you view content, so grab one when they go on sale for Labor day. Samsung released a laptop display in 1440P 240Hz from MSI, but that is not what I want. A laptop for sure can use the power savings from an OLED but I want one for my desk. I want that LG OLED in my life.

Well LG has finally heeded our call - Enter the ***UltraGear 45GR95QE***!

LG has announced a new 45-inch ultrawide OLED gaming monitor with a refresh rate of 240Hz. The company is calling the UltraGear 45GR95QE its “first curved OLED display with a 240Hz refresh rate,” which is notable at a time when most OLED displays (including those with flat panels) are still capped at 120Hz. 

Now, however, we’re seeing OLED displays emerge that go all the way up to ***240Hz.***  Razer has also announced a 240Hz OLED laptop of its own. This week we saw Corsair announce a 240Hz OLED monitor, although the fact that it can be manually bent into a curved monitor stole some attention away from its high refresh rate. (Some people like things flat - one of my monitors is curved, and it is not my main display.)

LG's UltraGear 45GR95QE’s other specs include an aspect ratio of 21:9, a curvature of 800R, and the ability to display 98.5 of the DCI-P3 color gamut. It’s got a 1440p resolution, an HDMI 2.1 port with support for VRR, and an additional DisplayPort 1.4 connector. I love this. I think in the next 5 years we will see mini-LED and OLED dominate the display space. Your cell phone likely has an AMOLED display on it so you may be reading this on an OLED. LCD/LED monitors are creeping up to refresh rates that the human eye cannot keep up with nor perceive much difference with. Most computers cannot even push that number of pixels and frames that much so I think the sweet spot is 1440P OLED @ 240Hz. THat is where I want to see innovation, and let's get Dolby Vision in on this so I can view my Plex HDR content on my PC. 

I hope this quick round-up gave you some things to read and think about. Next week I will return to one of my series - either Ops Horror Stories or I will explain some low level technology for you again. I think another topic I really want to talk about is the perception about ARM CPUs and the compatibility with major OS/Software, and how you can make the swap at your company to save money. You can do anything you want on an ARM processor. Just need to understand it a bit more. 