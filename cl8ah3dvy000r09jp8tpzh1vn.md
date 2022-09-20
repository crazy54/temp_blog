## It's Real: RTX 4000 Series Cards & More!

If you have been under a rock for the last 6 months, well, you are in for a surprise. NVIDIA has had their RTX 40 Series Launch Event today (STREAM IT HERE) and boy it sure did not disappoint. I am going to cover the main points from the stream, and summarize the stuff you need to know. Sadly, I am not able to help you get your hands on a fresh new Ada-based GPU, but hey,  if you want to send me one, I would love to have it. 

**Let's Go. **
## Ada Lovelace 3rd Gen RTX Cores Power RTX 40 Series GPUs

![Screenshot 2022-09-20 123250.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1663695180464/FZRY71o3H.png align="center")

It's no secret. NVIDIA has been the leader in the GPU game for the last decade and a half - the speed of innovation paired with advances in transistor size and GDDR-memory have been able to keep NVIDIA far ahead of team AMD no matter what AMD has attempted to try and make their niche of late - Team Green just comes out with their next architecture and destroys the niche AMD attempted to take away from them.

It is no different with the Ada-Lovelace RTX cards. 

These are the 4th generation Tensor cores from NVIDIA and those are paired with their 3rd generation RTX or Ray Tracing compute cores that power real-time ray tracing in games that support it like Call of Duty MW2. Ray tracing allows your GPU to generate real-time lighting in various ways. For instance, maybe you are swimming in Far Cry, and you see beams of light from the sun refracting into the water just like you saw on your last vacation. Maybe you are in Night City in CyberPunk 2077 and it just began to rain and the street lights are lighting up single drops of water on your windshield or face. Games that are not using ray tracing use light maps, which are pre-defined lighting that game developers generate when compiling the game. Typically, humans design them, and lighting artists are the people responsible. This tech allows their job to be far less hands off, and eliminates the need for multiple lighting maps. 

NVIDIA is now more than **doubling** peak throughput with the launch of Ada-Lovelace, packing up to ***90-TFLOPs*** of Shader power on NVIDIA GPUs, with 83-TFLOPs on the GeForce RTX 4090. Compare that to the ***40 Shader-TFLOPS*** of their fastest previous-generation GPU, the RTX 3090.

## DLSS 3.0 & NVIDIA Reflex

The RTX 4000 series cards are launching with new versions of their DLSS technology or Deep Learning super sampling. DLSS is an AI powered technology that allows your GPU to quickly and intelligently leverage the tensor cores onboard to generate more frames per second (FPS) at a lower resolution than what the user has selected for their final rendered resolution. It is well known that running a game such as Cyberpunk 2077 at 1080P is much less demanding than at native 4K. The 1080P image has 4x fewer pixels to render in each frame, so it only makes sense that you should figure out a way to allow deep learning to scale up that 1080P rendering to 4K, and fill in the gaps or missing pixel data so the image appears to have no loss or very minimal loss of quality. 

![DLSS](https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/ada/technologies/dlss/nvidia-dlss-3-ada-performance-chart-dl-v2.svg align="center")

DLSS 3 is new for the RTX 40 launch, and the highlights of the new version of Nvidia's DLSS are:

- DLSS 3 and Nvidia Reflex are now integrated with each other in the rendering pipeline: this means you should see less latency and better rendering performance when using DLSS and Reflex together. Team Green said they see NVIDIA Reflex making games even more responsive, with system latency as low as 10 milliseconds in top esports titles. 

- DLSS 3 is able to exponentially increase FPS counts using the new Optical Flow Accelerator

- RTX Remix enables the community to easily make mods with ray tracing and DLSS for classic games, like Portal with ray tracing

- The new Optical Flow Accelerator: This feeds pixel ***motion data*** from subsequent frames to the DLSS neural network, generating new frames on the GPU, ensuring performance accelerates even in CPU-bound scenarios. NVIDIA says this innovation can improve performance by a large order of magnitude.

## Okay - What Else?

![shadertime](https://images.nvidia.com/aem-dam/Solutions/geforce/ada/news/rtx-40-series-graphics-cards-announcements/geforce-rtx-40-series-shader-execution-reordering.jpg align="center")

On the performance front, NVIDIA talked about current and last generation shading pipelines and that since they are made by humans, performance is hit or miss and typically requires a ton of time and effort to make them run perfectly. Of course, the RTX 40 series has a method to fix this issue, or rather, improve it at least. Shader Execution Reordering takes the compute of the tensor cores on the RTX 40 cards and applies the compute power to reordering shader rendering pipelines in whatever the tensor cores and software decide is best. NVIDIA stated that this new innovation takes existing shader performance by up to 2X, and in-game frame rates by up to 25% depending on the card and title.

## Dual AV1 Encoders

Finally, let's talk about the video encoder side of the house. RTX 4000 series cards carry the eighth-generation NVIDIA Encoders (NVENC) on board. NVIDIA states they now support AV1 encoding which may sound lame, but those who deal with video encoders and decoders will be happy to see this included. This will enable a number of new possibilities for livestreamers, video editors and video callers alike. I think the real ramifications will be seen once the cards and drivers are in the wild - right now most cards focus on H265 or 264 encoding and decoding. 

**AOMedia Video 1 **(AV1) is an open source, royalty-free video coding format initially designed for video transmissions over TCP networks such as the internet. AVIF is an image format that uses AV1 compression algorithms to render content into its final form. The AV1 bitstream specification includes a reference video codec. In 2018, Facebook conducted testing that approximated real world conditions, and the AV1 reference encoder achieved 34%, 46.2% and 50.3% higher data compression than libvpx-vp9, x264 High profile, and x264 Main profiles. 

Now that NVENC supports AV1 as a first class citizen format for encoding, I think AV1 is going to begin taking off as the picture quality is just as good if not better than commonly used encoders today, but since it's open source and has no royalty structure, this is poised to now take off like H.265 and x264 have in years prior. This is something to watch, for sure.

## Final Improvements & Generational RTX Changes

![4000improvements](https://images.nvidia.com/aem-dam/Solutions/geforce/ada/news/rtx-40-series-graphics-cards-announcements/nvidia-rtx-full-stack-innovations.jpg align="center")

As you can see in the image above, each RTX release thus far has taken the existing RTX platform up to new heights. This generation is much more focused on taking the games of yesterday and tomorrow, and trying to design problems of those titles away. This can be seen in the shader reordering tech I talked about above, and in the DLSS 3.0 release highlights. Before you know it, 4K displays will be the norm, and 1440P and 1080P gamers will not always be around. However, we can leverage rendering tech in 1080P or 1440P and make the rendering happen and upscale to 4K making the gains and high frame rate numbers obtainable for professional and bedroom gamers alike.

No matter what you think about AMD vs. NVIDIA, it is hard to deny NVIDIA's growth and technology improvements each time a new generation card series comes out. I think most of us would have been perfectly fine with a new GPU and minor improvements to the software pipelines in the drivers, but instead, we got a complete overhaul and new release of these machine learning based assistive technologies.  It is important to look at the software and hardware as a complete package, and that is something AMD needs to get on board with. 

Last but not least, NVIDIA ShadowPlay can be used to capture gameplay at up to 8K at 60 FPS, in HDR. Not sure who is playing at that resolution much less streaming 8K signals out online since Twitch and YouTube do not support 8K at 60 FPS. YouTube does support 8K at 60 FPS and HDR. Good luck getting your content in native 8K 60FPS as this is still a long, long ways out and nothing you should even think about now. Besides, more content is upconverted from 4K60 to 8K60 than found in native 8K. I for one have finally gotten to a point where 90% of my media is in 4K60 HDR via Dolby Vision or HDR10+ and I plan to stay with 4K for some time. 

## Closing

Those are the main things you should take away from the NVIDIA stream today. I hope this has helped you learn about the Ada-Lovelace based cards and hopefully you can pick up an RTX 4080 or 4090 soon, minus the bots beating you to a NewEgg sale, or Founders Edition card from NVIDIA. 

If you like the content I make here at aptgetops.tech please subscribe and hit the like button to give me some feedback on the article. I also love to collaborate on posts or get ideas from you, the readers. Send me an email with what you want to do at [ideas@aptgetops.tech](mailto:ideas@aptgetops.tech) and I will make sure to let you know what I think. 
