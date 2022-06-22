---
title: "Installing and configuring Proxmox VE"
date: 2022-06-21 16:00 +2
categories: [virtualization, proxmox]
tags: [proxmox, virtual-machines, virtualization, VE, proxmox-VE]    
---
Proxmox VE is a completely open-source level 1 virtualization operating system. It can run on very low-end hardware, and is, therefore, one of the best virtualization operating systems out there for beginners and for professional users who want a free lab to work with. You can install Proxmox on any system as long as it has the minimum [requirements](https://www.proxmox.com/en/proxmox-ve/requirements).

## What you need
1. A system that meets the minimum requirements of Proxmox VE.
2. Another system that has an operating system.
3. A flash drive with 4GB of space.
4. A monitor.
5. Keyboard and mouse.
6. An HDMI or DisplayPort cable, as well as an ethernet cable.

## How to install
1. Download the official Proxmox VE [iso](https://www.proxmox.com/en/downloads/category/iso-images-pve) from proxmox.com. This might or might not take a while, as the file size for Proxmox VE is a bit large.
2. Download any flasher, in this case, I will use Balena Etcher, but Rufus and any other iso flasher will work. Download the flasher of your choice and choose the iso file you downloaded earlier and the USB stick. It is very important that you selected the right USB stick, as this will wipe the whole disk.
![Image of Balena Etcher](https://www.balena.io/static/steps-8006dca57323756b1b84fb9408742409.gif)

> If you are using Rufus, you will have to select DD mode. If you forget this, you will break your boot image.
{: .prompt-warning }

{:start="3"}
3. When you're done flashing your USB stick, you can insert the stick into any of the available USB slots on your computer. 

> On some desktops, the front usb ports may not be usable without an OS.
{: .prompt-info }

{:start="4"}
4. Plug in your computer power cable, display cable and an ethernet cable to your ethernet port.
5. Press the key to get to the boot menu, this can be the `ESC`, `F11`, `F12`, `F9` key or any other `F` key. If you are having problems with finding this key, you can check up on your pc manufacturer documentation.
6. In the boot menu, you have to select the USB stick. There will typically be a name with the manufacturer of your stick and the model of the stick.
7. After some time, there should pop up a screen that looks like this:
![Picture of Proxmox Install Screen](https://raw.githubusercontent.com/LucasoDevDotTk/.github/main/img/blog_website/_posts/2022-06-21-install-proxmox-ve/IMG_E5711.JPG)

> Before the Proxmox Install Screen is appears there is often a black screen which showes a bunch of text, this is normal.
{: .prompt-info }

{:start="8"}
8. Select "Install Proxmox VE". 
9. Press Agree to the EULA for Proxmox VE, if you do not agree, then you shouldn't install Proxmox VE.
10. Then input a good and secure password, enter your email address and click "Next".
11. Now you can enter your network details. Select your network card and choose a hostname. Then input your IP address, the gateway and the DNS Server.

> If you don't know your gateway, you can open command prompt on Windows and type `ipconfig`. Then you can search after the Default Gateway, use the same IP address as listed in command prompt when you enter the gateway.
{: .prompt-tip }

![Picture of network options in PVE](https://raw.githubusercontent.com/LucasoDevDotTk/.github/main/img/blog_website/_posts/2022-06-21-install-proxmox-ve/IMG_E5715.JPG)

{:start="12"}
12. Look through your settings and check if everything is correct, when you have checked and are sure, you can press install. This will install Proxmox VE and you can access it through your browser at the IP address you entered at port 8006.
![Proxmox in the Browser](https://raw.githubusercontent.com/LucasoDevDotTk/.github/main/img/blog_website/_posts/2022-06-21-install-proxmox-ve/Screenshot%202022-06-21%20195426.jpg)