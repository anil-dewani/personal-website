---
title: "Ways to super secure your linux server"
summary: "Since msot of the code we write is hosted on unix like operating systems - i will share some of the methods i use to secure my linux servers using various tweaks, tools and configurations"
cover_photo: "/rectangle/cyber-security.jpg"
read_time: "10 min"
---

Unix like operating systems are well known amongst the tech eco-system as backbone that holds major part of the developed code hosted on the internet. This has a reason, because the unix like operating systems give complete flexibility of configuration upto the level of kernel and are allow system administrators the DIY approach to build the operating system and configure it to their specific necessities.

A large eco-system of open-source softwares for such unix OS setup become an extra benefit to keep the costs low.

However, this comes with a rather bigger responsibility on sysadmin’s to secure these unix servers, as it is quite easy to configure such systems in a wrong manner. By default, unix systems are build keeping security in mind and are pretty minimalists, however an ill configured OS can easily expose itself to various attack vectors unknowingly.

Following are some pro-active measures I take whenever I deploy a new linux server for hosting services for my own needs or for my clients needs.

## Distro Selection
Linux kernel comes bundled into varieties of distributions which are called “distros” in short. You may have already heard the famous names like ubuntu and Debian, but there are many more which are pre-configured for specific necessities. There are special OS for server hosts, while there are different ones which focus more on the personal workstation for your home and office needs.

Following are some key points which are vital while choosing the distro to use on your server:

> Should have an active development roadmap for future releases

> Should offer LTS support for their stable versions

> Ability to enable SELinux and AppArmour

> Package repositories should be well maintained and updated with new stable packages so you don’t have to compile packages yourself and maintain them.

> Uses the most stable version of the linux kernel

> Should provide Enterprise Level Support

There might be more, but the above listed one’s are the most vital.

I personally prefer Debian as it ticks all the boxes above except there is no enterprise level support. If you as an company want enterprise level support, you only have two options, you can go with red-hat or centOS. 


## Keeping your system updated
Most linux distributions comes pre-bundled with a default package manager which is used to maintain and update all the packages that are installed on the system. You will have to set a weekly or monthly schedules to update all the packages to their latest stable versions. The frequent updates help you fix the following.

> Fix new vulnerabilities found in your current packages

> Fix any bugs that were discovered in the old versions

> Helps you shift to newer kernel versions once the old version becomes goes unmaintained

> Refreshes the package manager repositories to keep better track of package versions

It is vital to use proper and stable package repository URL’s as many hosting companies are known to replace it with their own servers. This gives them access to control which packages gets installed on the servers they provide. You can always check them at /etc/apt/sources.list file on your system.

Sometimes upgrades can fail your services, its important to re-evaluate your important service status after each upgrades.

## Operating using the sudo user
When you setup a new server, you’re probably given access to the root account. This is the account which has super-admin access, and the first attempt should be to protect it at all costs.

As you will not usually need super-admin access to run all the services you intent to run on your server, you can create a different user and provide it sudo access. This helps you keep the main root user to be used only when its very vital.

Once you’ve created a new user and added it to the sudoers group - you should immediately disable root logins by editing /etc/ssh/sshd_config file and setting the PermitRootLogin parameter to off.

This will help your server from getting hacked by brute force attacks trying to break into your root account. 

## Safeguarding the SSH Protocol
Any linux system focused on being used on web servers only usually have one open port allowing public connections. That is the infamous port 22. This port allow you to login to your server via the SSH protocol.

It is vital to change this port to a custom port which only you as an sysadmin would know, because most brute-force attacks are done on public ports which are well-known. Changing it to a custom port will decrease the attack vector to an extent. 

You can set the new port on /etc/ssh/sshd_config file and restart the sshd server.

However, this doesn’t allow the hackers to discover your new port as they can always do a brute-force attack to discover all the open ports on your server. Hence, we’ve to add an extra level of security. And that is to disable password authentications completely.

Yes, thats possible. You can login to your servers using SSH-keys, this way you can keep your private key file hosted on your work computer and only a person with that private key and its unique passphrase will be able to access the server. This decreases the attack vector significantly. 

You will have to keep your SSH key’s secure. I usually have them listed on my keychain access utility on my MacBook. This adds an extra layer of security because only a person with the password to your MacBook can view these keys.

[How to Setup Passwordless SSH Login | Linuxize](https://linuxize.com/post/how-to-setup-passwordless-ssh-login/)

Bonus points if you setup fail2ban, denyhosts and sshguard on your server. These makes you bulletproof. 

## Building a firewall around your network
Firewall is a network security system you configure on your server to setup rules and policies to safeguard your network. Consider it as a bridge between the public internet and your private intranet network of servers. 

You can accept, drop, reject, redirect the network traffic according to pre-defined rules and policies you set on the firewall system. It helps you keep track of the ports you’ve exposed to the public internet along with their individual access control rulesets.

Usually linux distributions comes with an pre-installed firewall program called “iptables” but it is quite cumbersome to use and setup. I prefer installing ufw as my firewall as its very user friendly and straight-forward for basic use cases.

Usual practice I do is to disallow all incoming connections until I deliberately enable it on my firewall. So when I install a new service which operates on a particular port. I’ve to manually enable that port or else by default it will be denied the access.

sudo ufw default deny incoming

sudo ufw default allow outgoing

sudo ufw allow ssh

sudo ufw allow 80/tcp

sudo ufw allow 22/tcp

## Setup logging and alert system
Since the server will be running a lot of process and it will be executing the code endlessly, it is vital to keep a track of how each particular service you are hosting on your server is performing. All major packages come pre-packaged with logging facility, they usually create log files In the /var/log folder.

I usually setup a service called papertrail for all my log management necessities. The tool keeps tracks of all of the lines of log data generated on my server every day, and alerts me on when it detects abnormal patterns.

I can always debug the issue in depth by intercepting the log files as they are stored on the cloud. This is vital because many a times a server goes dead due to OOM due to DDoS attacks or memory leaks but you can’t login to your own server to intercept the log files. Its vital to keep a logs backup on another system in such use-cases.

On top of that, I setup m/monit to monitor all the important process I run on my server and I setup Munin to analyse the resource trends on the server.

## Setup Snapshot backups
No server is secure until you’ve a backup/restore facility configured on it. We’ve to remember all of your digital assets might appear virtual to you on your screens, but they are actually stored as physical bits on a hardware setup at the datacenter somewhere. Datacenter can face natural calamities or your hardware setup might just die due to un-seen circumstances.

Hence, it is vital to create daily, weekly and monthly snapshots of your server - so you can be at peace all of your work stays safe as you will always have recent and historical snapshots of your system stored somewhere.

I use my own custom developed python script to perform backup of all the essentials and upload it to the backblaze b2 facility. 

I do daily backups of the following:

> The Home Folder which usually contains all of my active project codebases

> List of all the package installed along with their versions

> List of all source URLs of the package repositories I use on my server

> All the GPG keys I’ve stored on my system for secure package management

> List of all the python packages I’ve installed on my server

> Backup of /etc/ folder which usually hosts all my config files for software packages I use

> All the log files

> All the dot folders that are setup on my root and sudo user so I do not loose configurations

> Docker containers along with the volumes

> Full Database backup of Postgres and mariadb instances

> List of all the running processes and services on my server along with meta-data

The backup data is compressed and uploaded to backblaze b2 or any s3 enabled object storage service every night.

I usually keep 10 historical snapshots of daily, weekly, and monthly backups each and delete all the redundant ones automatically.

[GitHub - solution-coder/unix-server-backup: An python script to do full system backups of unix like systems](https://github.com/solution-coder/unix-server-backup)

