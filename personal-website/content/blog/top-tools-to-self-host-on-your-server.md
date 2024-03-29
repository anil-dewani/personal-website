---
title: "Tools which I self-host on my server"
summary: "I admire the process of self-hosting open source tools on my own server and being in total control of my own data. This also becomes a learning process as I have to maintain various different types of code-base on my server"
cover_photo: "/rectangle/self-hosted.jpg"
read_time: "12 min"
draft: true 
---

As it might be experience of everybody of us, human existence feels quite limited without our tools. Humans are called intelligent beings because we invent tools and tools in-turn build us further. It’s a cyclic thing. ...

In this modern world, we are almost bound to experience parts of our lives by using various tools. We use tools to cook, tools to organise our life, tools to earn a living by working. Tools are everywhere around us. Moving further into this evolutionary cycles, the future A.I tools shall probably build more tools for themselves automatically and finally this need of humans inventing new tools and managing them can be left out of the equation. However, this is just a probabilistic speculation at this point - just a random flight of my mind.

Anyhow, I quickly noticed that all the tools provide us with convince and Convince is almost like an addiction to most of us now, our reliance to our tools is too so extreme that we have forgotten how life would feel without our tools. 

This reliance on our tools, motivates the engineer mindset within me to look underneath into the tools, how they work and function, how these tools create meaningful functionalities by creating a eco-system of co-dependence amongst various smaller sub-sets of tools. It’s fascinating to me.


Hence, I’ve started to self-host various open source technological tools used by us in our day-to-day life to better understand them, it further develops my ability as a system administrator on how to maintain various different types of codebases on my linux servers. The diversity is quite fascinating. 


Below is a list of tools I self-host on my bare-metal linux server, both for conveince and my own knowledge expansion.


## Custom Browser Homepage Dashboard
Since I use a lot of tools, and self-host most of them. I have a custom home-page dashboard setup for quick access to all the tools, calendar, an search bar integrated to kagi (the search engine I use) - the dashboard even live streams my base linux server’s cpu usage and memory consumption statistics for a quick lookup via integrating dash.

I use an open-source tool named homarr, which makes this possible.

## Realtime System and Process Logs
Whenever I’m working on an project, I like to have a visualisation setup for streaming all the logs that are being generated by certain software packages which I’m using. For example, I would live stream error log file for nginx when I’m developing or launching a new web project. This helps me witness the errors popping up in real time so I can have a quick fix for them. 

For most of the part, I use lnav open as full screen on one of my desktop screens.

## System Process Monitoring & Alerts
Since I manage my own linux server, I need to monitor upon all the important process which are currently running on my server. It can be nginx server, my database server, or any other custom daemon scripts I’ve running. 

I use m/monit for this task - it can be configured to monitor various types of process and alert me as soon as some of these process start producing un-needed events. 

This helps me sleep at peace at night because I’m assured all my important process are running and functional on my server.

## Uptime Monitoring
Statping-ng is a web tool I self host as it helps me keep statistics on the current ping latency and total uptime of all of my web projects which are hosted online. These can be various websites, API endpoints and even actual servers.

The tool can be setup to see if the service is operational and alerts me as soon as an downtime is noticed, so I can quickly debug the issue. This helps me keep all of my web projects alive and kicking 24/7 without any interruptions.

## Resource Graphs
Often times, during a case of incident - we want to have a complete snapshot of how various resources and processes were functioning on the server at that given point of time, when the incident happen. 

Usually by default unix servers keep a text based log file records, but it eventually becomes too hard to keep track of all of them, specially when you’ve multiple different process running simantenously.

I use Munin, which automatically creates useful graphs of various vital factors which needs to be monitored. It’s certainly beautiful to look at it and see how various different things co-relate to each other.

## My own cloud
Since we all now operate multiple devices - it becomes crucial to have some sort of file synchronisation setup. Owncloud is something I self-host to host to give me a dropbox and google-drive like sync’d folders across all of the devices I use. It also keeps all of my sync’d files on my server as a backup - just in case. Which some services like Resilio sync can’t provide. 


## Notification Service
Notifications play a central role in our tech life as they are like our digital reports reporting us about crucial events which we want to be aware of. The use-case of notification server is quite wide. On my setup, I’ve setup following notification events:

> Every weekday 9am I get notified about my pending high priority tasks from my GTD setup

> Integration with system monitoring and uptime managers to alert me whenever any of important process or web-services start malfunctioning

> Instant notifications when somebody logs in via SSH on my server along with ip information

> Daily report on how my server backup script performed with relevant statistics

> Instantly notify me when there are new errors on all the log files I monitor - I like to keep them clean, especially the error logs.

> Since I maintain a digital garden about all the things I learn in life, I setup to send random quotes from it every few days

> Notifies me of upcoming holidays from the calendar so I can plan my week better

> Hydration alerts to keep drinking water, since I always skip it when I’m occupied with some tasks

> Reminder to import my financial statements on my firefly finance manager instance. I do this every first weekend of the month.

> Daily reports of how I spent my time on my devices organised into productive and non-productive activities. Provided by activity watch.

> Shares a random highlighted text out of all the kindle books/articles I’ve read. This helps me re-connect to small chunks of knowledge which I found insightful while reading the book.

> Monthly reports on my finances, categorized into various sub-sections and budgets.

> A list of all the links that were shared on all the IRC and telegram groups I’m part of. Always found gems through this method.

> Reminds me of my current biological age as a random notification once every 120 days


There are some more personal notification setups I’ve coded which I would like to keep private, but you get the deal. You can set it up and code it the way you want, you can integrate the notification server with various other softwares or even your own. Its definitely a great help.
 

## Chat setup
I’ve been an IRC lurker since almost a decade now, its not as vibrant as it used to be back in the days, but I still find it inspirational and engaging to be part of all the knowledge filled chats that constantly happen on the internet on these IRC servers and chats. Some are really whacky though, but most of them are true gems for any technology enthusiast as it keeps you in touch with what people are talking about in that particular eco-system.

I use znc server to keep my connected 24/7 on these IRC server and wee chat-android and thelounge as frontend to all these chat rooms.

I keep monthly logs of all the chat that happened in these servers just for my backups. 

Rooms I’m connected to are most tech related ones like #python, #linux, #archlinux, #django #nginx etc to name a few. The list goes on.


## GTD Setup
GTD (Get Things Done) is a popular task management system designed by productivity consultant David Allen. Since we are almost bombarded with constant stream of information in this Information Age, we need to build systems to keep track of what needs attention. The distractions are endless in this era, this has not been the case for our previous generations.

Changing times, need better tools. My GTD setup is my attempt to keep my attention streamlined to what is most necessary, so that I don’t blow off into the sea of informational distractions. 

I use tracks for my GTD setup - I like the minimalist design and ability to self-host all the data about my private life helps me feel better. 

I organise all of the tasks I need to work upon into various different projects, set them a relevant priority and due-dates if necessary. Everyday my notification server would provide me a mini report on how things are looking up on my GTD setup. Specially the high priority tasks. I do not allow myself to be lazy about those.

## Scanned Documents
We all have certain important documents we want to preserve, it can be legal documents, lecture notes, gift cards or even your secret love letters. 

All of the documents that scanned on my scanner machine can now be forwarded and maintained using paperless-ngx server. It provides front-end to browse, manage, tag and search all of your scanned documents.

The scanned folder gets added to my daily backup script and is available for access on all of my devices integrated it with my owncloud setup.

## Content Consumption
Since we are living in an Information Age, a lot of time we spend on our devices is consuming content. Most of these content platforms are designed to track your preferences and exploit it somehow by showing you exploitive consumer psychology influenced advertisements. 

Hence, I use alternative front-ends to browse all of the major content platforms like YouTube, twitter and reddit.

I use following browser extension to auto redirect links towards my privacy focused front-end.

I use piped for YouTube, xyzzy for twitter and libreddit for reddit.

Finally, it’s not as easy to track my content consumption for these tech companies.

## Business Analytics
All major business model requires reporting and monitoring tools to get an high level snapshot of how the business is performing. It’s too cumbersome to custom code all the reporting part of all the web development projects I do. Hence I use something like metabase and superbase - it quickly connects to various data-sources I’ve my business data located it.

Since most of the reporting and graph needs are similar, I use available presets on these open source tools to automatically create high-level business dashboards for all my current operations.

It’s very quick, forget about custom coding all your reports for ages.


## Ad Filtering
All of our internet traffic use domain names, hence a custom DNS filtering setup can be a classic way to filter out all of the unwanted connections that are being established from your network towards these illicit ad network, tracking servers and even porn sites.

I use pinhole for DNS filtering and it automatically blocks out ads, trackers and porn sites on my home network. You finally have a clean wifi network you can connect to, that’s my home. :) 


## Digital Garden
I’ve a wikijs setup to quickly note and organise all of the important points I learn consuming various knowledge inducing content online. It’s been my habit to always keep notes of important things I learn in life and keeping it organised in my own personal wiki is very helpful. It’s fascinating to see it growing. I call it my digital garden of knowledge. Somehow I can make it public for all of you. For now, there is a lot of randomness which I need to sort out.

## Finance Management
Since finances remain the integral part of our lives, they do need to be maintained well. Its useful to be in touch with your financial journey, keep track of how you’re performing on your pre-defined budgets and which categories you spent the most. All the useful insights helps create a feedback loop to re-adjust your financial tendencies, eventually helping you in your financial liberation journey. 

I self-host firefly-3 and have some custom auto-import scripts which automatically imports my transactions to the platform and organises it into various categories, tag, budgets, and bills. 

I’ve setup a few piggy banks within the system to accumulate the savings into various categories. These act like pre-allocated savings account for major goals like a new car or retirement.


## Activity Monitoring
Since a lot of my time is spent on my devices and the world right now is filled with extreme levels of distractions, it becomes vital to keep track of how I spent my time on all my devices. I use activity watch because it stores all the tracking data locally on my own devices and is privacy focused.

This helps me keep a track of which sites I browse the most, or which applications I use. I’ve integrated various custom rules and alerts to help me limit my usage of certain unproductive apps/sites on the weekdays. 

I also use it as a stopwatch to track how much time it took for me to build an feature I’m coding. Which is quite insightful. 

Below is list of Mac apps and android apps I’ve setup to enhance my tech life.

## Secure Note Taking
StandardNote is what I personally use as my note taking server. It has clients for all major desktop and mobile operating systems. I extend it using various extensions to enable editors which help me take notes in markdown, programming languages and WYSIWYG style. 

I use to to store useful code snippets, write my blog posts, take quick notes and even for brainstorming some pseudocode.

Following is an tentative list of all the softwares I use on my workstation and mobile phones:

Dash

Devbook

uBAR


LittleSnitch - https://www.obdev.at/products/littlesnitch/index.html
Network Monitoring

https://www.keka.io/en/ - file archiving

https://www.mediaatelier.com/CheatSheet/ - Cheatsheet to view keyboard shortcut to current app


https://xbarapp.com/ - custom plugins for mac menubar


https://magnet.crowdcafe.com/ window organiser

keepassxc - password manager keeweb file

https://objective-see.com/products.html security tools

https://www.dbklabs.com/ - standalone apps for netflix, youtube, prime.

https://www.browserfairy.com/ multi browser sandboxing

https://www.postman.com/downloads/ - API management

https://www.macbartender.com/ - menu bar magic

https://github.com/ohmyzsh/ohmyzsh - zsh shell for the terminal 😉

https://www.keyboardmaestro.com/main/ Automation engine for mac

https://numi.app/ - Calculator!

https://unclutterapp.com/

Medis 2
https://rdm.dev/
https://tableplus.com/
Flowchart Designer 3

https://www.espressoapp.com/ Web designer

https://proxyman.io/ network proxy

https://pypi.org/project/clearly/

Alfred 4 with custom scripts

Raindrop

## android apps
Aurora Store
Stellarium
Volv
Techontheedge
Feem
Pocket casts
Wee chat-android
Vysor
Snipd
Libretube
Otaku
KLWP/KWGT/KLCK
Slowly
Schildichat
Session
Bromite
Infinity 
Florisboard
Activity watch
Cloud stream 
Aniyomi 
Sleep as droid

Hope you found some valuable information reading about my tech arsenal. Feel free to ping me with your suggestions or if you want to hire me for your next tech project.
