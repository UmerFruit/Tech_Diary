---
title: "Setting Up Enhanced Session in hyper-v for Linux"
date: 2025-08-09 10:00:00 +0500
categories: [Setup]
tags: [environment, tools]
---
# Install Ubuntu 20.04 on Hyper-V with Enhanced Session

While it does say linux in the title, i will mostly be referring to Ubuntu or debian based distros for this guide. The tools installed also have an **arch** version in the same repository so feel free to use that. 
***Skip to Post-Installation if you just need quick commands***

## Easy Way
if you don't really need the latest ubuntu version and are fine with ubuntu-22 just download it from the "quick create" in the hyper-v manager.

## Setup from Scratch
This is the method to goto if you are install a linux system that is not ubuntu and thus is not offered in quick create. So,

###**Create VM**  

1. In Hyper-V Manager, create a new VM (e.g., "Ubuntu Hyper-V"). 
2. Choose Generation 2
3. assign Required RAM, 4096 MB is great for most linux systems. Use dynamic memory only if you know what it does.
4. Select a virtual switch, I personally like the bridged network configuration (External adapter)
5. create a VHDX, 128 GB by default is good for most cases. Don't worry, it wont take up 128 GB instantly. Instead it fills that space as it needs.
6. Finally, Attach Ubuntu (or any other distribution) ISO.

###**Install Ubuntu**  
Follow on screen configurations if you know what you are doing or follow a tutorial on how to install that linux distro if you don't. 

***Important***: Remember to disable auto login during setup. i.e.  
- [X] Require my password to login  

##**Post-Installation**  
Get the latest version of linux tools from: [Hinara's Github](https://github.com/Hinara/linux-vm-tools/tree/master) they currently have support for arch and ubuntu (so any debian based distro is also covered). I personally haven't tried to run arch in hyper-v yet, so use that at your own risk.
**I'll list the commands to setup ubuntu 24.04 LTS as it is the LT at the time of writing.**
In terminal:
```bash  
cd ~/Downloads/  
wget https://raw.githubusercontent.com/Hinara/linux-vm-tools/refs/heads/master/ubuntu/24.04/install.sh  
sudo chmod +x install.sh  
sudo ./install.sh  
```
Reboot, then run script again.

**Host Configuration**  
In Hyper-V Manager, enable Enhanced Session Mode Policy. 

In PowerShell (admin):  
`Set-VM -VMName <Your-VM-Name> -EnhancedSessionTransportType HvSocket` 

**Side note**: Use quotes "VM Name" if your vm name contains spaces 
examples:

`Set-VM -VMName My_Ubuntu -EnhancedSessionTransportType HvSocket` 

`Set-VM -VMName "My Ubuntu" -EnhancedSessionTransportType HvSocket` 

Reboot host if needed. Start VM, configure display/resources, and log in with Ubuntu credentials.

**Conclusion**  
Enhanced session mode enables dynamic window resizing, clipboard sharing, file transfers, and resource access.