---
title: "Storage Configuring in Proxmox VE"
date: 2022-06-22 11:00 +2
categories: [virtualization, proxmox]
tags: [proxmox, virtual-machines, virtualization, VE, proxmox-VE]    
---

This is a follow-up tutorial on my last [post](https://blog.lucasodev.tk/posts/install-proxmox-ve/). Please make sure you have Proxmox VE installed.

- Log into your Proxmox server at the IP address of your server plus the port, 8006. Use the password you set earlier and the user `root`. The password you set should be very secure as the person who has the password has complete `sudo` control over the system. The browser should look something like this:
![Proxmox in the Browser](https://raw.githubusercontent.com/LucasoDevDotTk/.github/main/img/blog_website/_posts/2022-06-21-install-proxmox-ve/Screenshot%202022-06-21%20195426.jpg)
---

## Configuring storage

> You don't have to do these steps if you have multiple storage devices.
{: .prompt-info }

You might have noticed that Proxmox has made two storage devices, `local` and `local-lvm`. We want to get rid of one of them, so we don't have to deal with two storage devices.

1. To change this, you want to navigate to the Proxmox tab, on the far left. Then click on `Shell`. You should be presented with a terminal in the browser. 

2. We are going to delete the `local-lvm` volume, to increase the space in the `local` volume.

Type this into the Shell.

```bash
lvremove /dev/pve/data
```

> This command will remove the `local-lvm` volume.
{: .prompt-info }

> When it asks you if you are sure, type `y` and click `ENTER`.
{: .prompt-tip }

{:start="3"}
3. Then write:
```bash
lvresize -l +100FREE /dev/pve/root

resize2fs /dev/mapper/pve-root
```

> These command will resize the free space from the disk and assign it to `local`.
{: .prompt-info }

{:start="4"}
4. Now you have to navigate to Datacenter/Storage/local-lvm on the left bar in Proxmox and click on the remove button.
![Image of where to click](https://github.com/LucasoDevDotTk/.github/blob/main/img/blog_website/_posts/2022-06-22-configuring-proxmox-ve/Screenshot%202022-06-22%20124405.jpg?raw=true)

## Configuring Storage Permissions
Since I only have one disk, I will have to make sure that all types of storage can be stored using `local`. Go to Datacenter/Storage/local-lvm, like in the previous step. Select your drive and click `Edit`. 

![Image of Editing drive in Proxmox](https://github.com/LucasoDevDotTk/.github/blob/main/img/blog_website/_posts/2022-06-22-configuring-proxmox-ve/Screenshot%202022-06-22%20125511.jpg?raw=true)

Since I only have one drive, I need to configure it to allow all types of media.

> You can edit all types of drives. If you have more drives, you might want to only allow certain items into certain disks.
{: .prompt-info }