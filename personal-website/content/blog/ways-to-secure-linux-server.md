---
title: "Ways to super secure your linux server"
summary: "Since most of the code we write is hosted on unix like operating systems - I will share some of the methods I use to secure my linux servers using various tweaks, tools and configurations"
cover_photo: "/rectangle/cyber-security.jpg"
read_time: "5 min"
---


Unix-like operating systems are renowned within the tech ecosystem as the backbone supporting a significant portion of the code hosted on the internet. This prominence is due to Unix-like systems' unparalleled flexibility, allowing for kernel-level configuration adjustments and enabling system administrators to tailor the operating system to their specific needs.

The extensive ecosystem of open-source software for Unix OS setups is an additional benefit, helping to minimize costs.

However, this flexibility comes with a significant responsibility for sysadmins to secure these Unix servers, as improper configuration can easily expose them to various attack vectors. By default, Unix systems are designed with security in mind and are inherently minimalist, but an improperly configured OS can quickly become vulnerable.

Below are some proactive measures I take whenever deploying a new Linux server, whether for my own needs or for clients.

## Distro Selection
The Linux kernel is packaged into various distributions, commonly referred to as "distros." You're likely familiar with names like Ubuntu and Debian, but there are many others tailored to specific requirements, including specialized server hosts and workstation distros for home and office use.

Key considerations when choosing a distro include:

- Active development roadmap for future releases
- Long-term support (LTS) for stable versions
- SELinux and AppArmor support
- Well-maintained package repositories, avoiding the need to compile and maintain packages
- Utilization of the most stable Linux kernel version
- Availability of enterprise-level support

While I personally favor Debian for fulfilling most of these criteria (except for enterprise-level support), companies requiring such support typically opt for Red Hat or CentOS.

## Keeping Your System Updated
Most Linux distributions include a default package manager for maintaining and updating installed packages. Setting weekly or monthly schedules to update packages to their latest stable versions is crucial for:

- Fixing newly discovered vulnerabilities
- Addressing bugs found in older versions
- Transitioning to newer kernel versions as older ones become unmaintained
- Refreshing package manager repositories for better version tracking

It's essential to verify the use of proper and stable package repository URLs, as some hosting companies may substitute them with their servers, potentially compromising package integrity. Always check the `/etc/apt/sources.list` file for accuracy.

Post-upgrade, reassessing the status of critical services is important to ensure their uninterrupted operation.

## Operating Using the Sudo User
Initial server setup often provides root account access, which holds super-admin privileges. The primary goal should be to protect this account.

Creating a separate user with sudo access and restricting the root login by editing `/etc/ssh/sshd_config` to set `PermitRootLogin` to off mitigates the risk of brute-force attacks targeting the root account.

## Safeguarding the SSH Protocol
Linux systems intended for web server use typically open only one public port: the well-known port 22 for SSH access.

Changing this default to a custom port and disabling password authentication in favor of SSH keys significantly reduces vulnerability to brute-force attacks. SSH keys offer a more secure method of server access, with the private key stored securely on your work computer.

Implementing security tools like fail2ban, denyhosts, and sshguard further strengthens your server's defenses.

## Building a Firewall Around Your Network
Firewalls act as a security barrier between the public internet and your server network, controlling traffic based on predefined rules.

While iptables is the default firewall program in many Linux distributions, its complexity often leads users to prefer ufw (Uncomplicated Firewall) for its user-friendliness. A standard practice is to deny all incoming connections by default, only allowing necessary traffic as needed.

## Setup Logging and Alert System
Monitoring service performance is crucial, with major packages typically generating log files in `/var/log`. Services like Papertrail help manage log data, providing alerts for abnormal patterns, while tools like m/monit and Munin monitor processes and analyze resource trends, respectively.

## Setup Snapshot Backups
The ultimate security measure for any server is a robust backup and restore capability. Regular snapshots ensure the preservation of your digital assets against physical data center risks.

I utilize a custom Python script to backup essential data nightly, uploading it to Backblaze B2 or a similar S3-compatible service. This includes project codebases, package lists, configuration files, logs, and databases, among other critical data.

Maintaining historical snapshots and purging redundant ones ensures data integrity and recovery capability.

