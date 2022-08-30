## Most Useful Bash/ZSH/CLi Tools & Applications

## Here We Go Again...

Any time I see a blog post that tells me I am going to read its contents and then become some insanely productive sysadmin/engineer/developer. However, 9 of 10 of the recommendations are garbage and I can typically already perform tasks quicker than without moving to the suggested tool. I leave the article feeling like I got click baited and I go on with my day without becoming a superhero as I was promised. 

My hope for the article here is to give you practical advise that can save you time in your daily work. I am not trying to make you superman - to do that you have to keep on leveling up your skillsets. The items listed here are just nice things to use in a terminal. I do use Powershell for things at home but at work and at home my primary shell is ZSH as it is the gold standard these days. You can pimp it out to whatever level you please or you can leave it bone stock and enjoy the features that are built in from a bone stock config. 

The second bit I will be talking about are dot files. To those not familiar with the term, a dot file is literally a file named ```.file / .zshrc /.vimrc``` - these are you personal configuration files for any applications you use in your shell environment. They retain the settings and addons you have installed so each time you launch that application, like Vim, you always get the settings you spent time setting up. 

Now that I have explained what we will be looking at, let's jump in. 

## Dotfiles
![dotfile](https://miro.medium.com/max/700/0*nq_HSl77KnQ8Balc.png align="center")

To begin, I want to talk about dotfiles. Here is the list of items and a short paragraph about why they are so useful, and something I personally use. 

**Dotbot **| https://github.com/anishathalye/dotbot/

Before we jump in too far, let's talk about dotbot. If you use programs like Homebrew or other pkg management software, you will discover a lot of the repos will upgrade and remove your dotfile or other config files. This awesome little bit of code called dotbot makes it simple to change out large numbers of dotfiles in a single line of code. Lets pretend you find a sick repo with some dotfiles you want to try out but you are not sure you want to keep them all. 

Dotbot can be installed with pip if you prefer python over bash/zsh, or you can use the default package installed with homebrew or the source released on Github. Just to give you an idea on how simple it is to install a lot of dotfiles quickly with dotbot using a github repo of dotfiles you want to setup, all you have to do is type: ```git clone $url && cd dotfiles && ./install```

I highly [suggest reading this blog post](anishathalye.com/2014/08/03/managing-your-dotfiles/) which was written by the owner and creator of dotbot. It teaches you how you can make a configuration for your personal dotfiles so if you replace them testing out a repo online, you can easily return your files back to their original state. It also talks about how all the functions and advanced features work. If you operate a repo with dotfiles, you want to learn this tool and include a configuration that works with dotbot so people can easily test your dotfiles out. 

**adoyle-h/dotfiles** | https://adoyle.me/dotfiles/

***This is for bash only - zsh users need not apply!***

This repo has a load of really nicely organized and easy to understand dotfiles for the bash users out there. I won't call each one out, but these are some of the better bash exclusive dotfiles I have found. 

This repo works perfectly with the following environments: **iTerm, Bash 4.4 & 5.0+, Tmux 2.7+, MacOS in both Intel and ARM flavors, all Linux/Unix distributions.**

 The repo has a great file structure and in the tree there is a comment for each entry so you know what is going to be installed. It has dotbot configurations for MacOS, and Debian server and desktop versions. It also comes with all the required dependencies so you do not need to install anything else. 

The link above to the website contains a long list of preview screenshots so you know what you are getting into.

**Awesome Dotfiles** | https://project-awesome.org/webpro/awesome-dotfiles
![awesome](https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/awesome/awesome.png align="center")

I would hope most readers here know about the Awesome project - if not, I can give a short explanation. The project is geared towards users that are developers, engineers, you name it. The project puts their stamp on Github repositories they deem awesome and very useful. The stamp so to speak is the well known pink sunglass emoji they created, and it is pretty well known these days. I always begin my search with Awesome branded repositories as I know I am getting good stuff. 

Anyway, this repo is the Awesome Dotfile repo. It contains so many dotfiles, I can't possibly list them on this post, but you can trust that the file you want is likely in this repo. This repo contains dotfiles for the following shells:```Bash, ZSH, and Fish```. They also have Ansible and many other tools included to help with deployment - and yes, it works with dotbot. 

This repo also links to other repositories that contain Awesome approved dotfiles, so you will be setup well starting with this repo and you may not need anything else. 

**YADR - Yet Another Dotfile Repo** | https://github.com/mente/dotfiles

Yup, this is the last dotfile repo I am going to link to, but I may link to application specific dotfiles since most people want to control what they enable - esp. when it comes to applications they use daily, and likely have a dotfile they always want to keep setup how it is today. Keep in mind, you can merge your settings with the dotfile settings if you wish. I suggest that you try using the dotfile from a repo alone - remove your personal dotfile so you can see what the developer was going for. Sometimes your settings can conflict with a setup in a downloaded dotfile, so make sure you test. 

This repo contains a lot of things: 90+ Vim plugins, the best of all the "top" dotfile repos, with vim/zsh plugins curated in one single place to make troubleshooting or making updates simple. All the things in this repo are setup to use vim and work well with the editor, so if you hate vim, too bad. 

**BONUS REPO**: *The Ultimate Vim Configuration* | https://github.com/amix/vimrc

This is one repo I always get installed as soon as I land on any new VM/laptop! The choices and configurations are vast - even though it is really just for vim! You can get ***extremely ***close to however you want you vim config to be and use the other things you may not want to learn about how they were setup so in the future you can add in items to your own .vimrc file. I highly suggest using the "Awesome" version of this repo as it contains the most useful configuration choices that you will use once you know about them and understand how they work.

## Shell Setups

![terminal](https://i0.wp.com/mycodetips.com/wp-content/uploads/2019/09/terminal-512.png align="center")

**Awesome zsh plugins** | https://github.com/unixorn/awesome-zsh-plugins

This is awesome approved -and highly suggested for anyone new to zsh or you've used zsh for years. There is a plugin for everyone and I know you can find something you can add to your configuration! It also helps you learn about which zsh plugin manager is best and why. 

After plugins, it runs through themes, fonts, auto-complete solutions, and more. You can spend a few days going through all the material here, so make sure you have a good chunk of time. Just wanted to warn you now - don't start before dinner is put on the table or the wife will yell at you. 

**oh-my-zsh** | https://github.com/ohmyzsh/ohmyzsh 
![omzsh](https://ohmyz.sh/img/OMZLogo_BnW.png align="center")

If you are not familiar with oh my zsh well, we need to chat. Oh My Zsh is an open source, community-driven framework for managing your Zsh configuration, and it also controls themes and plugins. It has a huge community for support, hundreds of themes you and apply, and so many plugins your brain would melt trying to remember all the ones you installed. 

One suggestion here is to not go insane with adding 30+ plugins unless you use each one all the time. The more plugins that you install and manage in oh-my-zsh the longer your shell will take to launch. You may want to look into Antigen and some other ways you can optimize your zsh plugins with so you can fire up a terminal and not have to wait so long you can have a biobreak before the shell is ready and loaded. You also have to manage them and keep them updated, so just install the ones you need. 

** Awesome Shell** | https://github.com/alebcay/awesome-shell | also on: https://unix-shell.zeef.com/caleb.xu

The final entry in this category is Awesome Shell - it is a repo that contains the best and most used customization for the top shells - Zsh/Fish/Bash. Fish and Zsh users can find really cool plugins and configs that are ready to go so you don't need to take time and setup all the features you want - you have a good baseline that you likely will not touch until you find a few small things that you want to change becuase they annoy you. 

Besides the typical customization items, it has applications, games, shell package management, script deployment, and guides. There is so much material here, but it is all packed up so well you won't need hours to get it running on your machine. The guides and how-to articles are also super simple and have all the sample code you need to make the installation and configuration work without much input from you. Make sure you keep the repo up to date though, as a lot of the scripts in here pull from the local repo, so to update static material that Zsh/Fish/oh my zsh/Antigen/etc. typically would not update on their own. Great repo, keep this one handy. 

**Bonus**: Bash Awesome | https://bash.awesome-programming.com/

This is not so much a way to organize plugins or themes, but more along the lines on how you can be better at programming in Bash, learning the inner-workings of the shell, and it has materials on the site itself, Youtube, and in a Discord and forum. It is a bookmark you should keep around for reference and examples. 

## Terminals

![terminal_blinking](https://cdn.dribbble.com/users/94656/screenshots/1141726/media/6f11441efdf89c25ac8a26c0b62f6730.gif align="center")

 **Awesome Terminals** | https://github.com/cdleon/awesome-terminals

This is a pretty simple one. It has a list of terminals that are known to exist depending on the platform you use. You can try out all the options until you find one you like, but the repo ReadMe has a good descriptive list as to what each terminal has that makes it unique. **It covers the following platforms**:** iOS, Linux, Android, MacOS, Windows, and even web browsers.**

Then, it talks about Shells and once those have been covered, it opens up the can of worms called Tools. Now the tooling section is special as it has so many platforms, code bases, you name it - it is here. I have never seen so many tools for terminals in a single place. Make sure you bookmark this one as you never know when you will need it!


**Terminals are Sexy** | https://github.com/k4m4/terminals-are-sexy

![trs.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661879231982/N-_0NpeKW.png align="center")

Chances are you likely have seen this repo if you have googled for terminals before. Well since it has been in my bookmarks for years at this point, I wanted to share it with you. This repo contains a lot of the same things Awesome Terminals has, but it is setup differently. In this repo things are organized by tool type, not platform.

**For example, you can browse by:**

**Shells | Terminal Emulation | Package Managers | Text Editors | Tools/Plugins | Communication | Other**

This makes finding what you want or need much simpler than some of the other repos around the internet. I highly suggest keeping this repo around becuase it is actively updated and there is always something new when I go back each time. 

## Apps for the Command Line

This section is dedicated to the apps that you likely never knew existed and you really should know what is out there. You can leverage these in scripts, config files, etc. There are a ton of ways you can use the command line, and as someone who prefers to live in a terminal, this is one of my favorite sections in this post!

**Awesome CLI Apps** | https://github.com/agarrharr/awesome-cli-apps 

![asa.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661879455458/jq980TsIL.png align="center")

This is an awesome certified repo, so you know right off the bat this is a good place to get info. If you need to do something in the command line, you can safely bet it is here or someone has not yet made it. I have used Slack in the command line, I use openBB for stock viewing and stock related investigations, I read books, I game, the list goes on and on for what is possible here. 

***Don't forget - those of us who were alive for the Commodore 64 era and on, we lived our entire lives in the command line***, and could not just download an app to make something work. We had to type in all the code and run it, and save the working code to a floppy. So when you look over this list, just remember that it is not old school but it was normal. Heck, maybe you will get converted to command line and CLI all the things!

**Project Awesome: Awesome CLI Lists** | https://project-awesome.org/umutphp/awesome-cli
![awesome](https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/awesome/awesome.png align="center")

**Yup, this is a list of lists. **

The Project Awesome folks have lists on their site that list all the user created lists they support and endorse. This makes it simple to find what you are looking for, all in one place. No need to Google anything, just use their site. 

If they have endorsed someone for an awesome list of content related to CLI, you will see it in this list. There are too many to list the great ones. Project Awesome makes it a mission to ensure all the lists they share with the community are upkept and have unique content users can enjoy. 

## Conclusion

I hope this list helps you in your quest to become the best engineer/developer/etc. you can be. Learning and being able to navigate a terminal is not something you should put off - you should master it the fastest you can. These links contain tools that will help you do things smarter, not harder - but they won't tell you how they are doing it, and you should know how things happen behind the scenes. So if you are a junior engineer coming up in TechOps, make sure you do yourself a favor and read and learn the source code to all the things you decide to install in your shell. You will be so happy you did down the line when it comes up as an interview question later in life. 

**If you have suggestions to add into this list, please shoot me an email at**: [ideas@aptgetops.tech](mailto:ideas@aptgetops.tech) 

I would be happy to take any suggestions into consideration for the next post, or just comment below on other things you want to see - other Awesome lists, what topic you want - just let me know and I can take your idea and run with it. 

*If you have someone you know would want to see this please send it over to them and make others gain the superpowers of the terminal! *