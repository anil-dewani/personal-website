---
title: "Ways to super secure your linux server"
summary: "Since msot of the code we write is hosted on unix like operating systems - i will share some of the methods i use to secure my linux servers using various tweaks, tools and configurations"
cover_photo: "/rectangle/cyber-security.jpg"
---

Unix like operating systems are well known amongst the tech eco-system as backbone that holds major part of the developed code hosted on the internet. This has a reason, because the unix like operating systems give complete flexibility of configuration upto the level of kernel and are allow system adminstrators the DIY approach to build the operating system and configure it to their specific necessities.

A large eco-system of open-source softwares for such unix OS setup become an extra benefit to keep the costs low.

However, this comes with a rather bigger responsibility on sysadmin's to secure these unix servers, as it is quite easy to configure such systems in a wrong manner. By default, unix systems are build keeping security in mind and are pretty minimalists, however an ill configured OS can easily expose itself to various attack vectors unknowingly.

Following are some pro-active measures i take whenever i deploy a new linux server for hosting services for my own needs or for my clients needs.

- Pick a suitable linux distro and stay on the LTS version
- Create a sudo user and disalbe root logins
- Change port of ssh from 22 to any other
- Setup password protected SSH keys and use it for authentication instead of plain-password
- setup ufw fireweall and disallow all traffic except the ports you open for your web services
- setup fail2ban
- setup denyhosts
- minimalist approach, less packages = more security
- update server packages every week or month
- setup logging and alerting

Done!