---
title: "Assignment 1 - Installation of VirtualBox and Fedora 38"
date: 2023-10-29T01:59:39Z
weight: 3
tags: ["Linux","VirtualBox","Fedora"]
author: ["Haziq Rohaizan"]
showToc: true
TocOpen: true
draft: false
hidemeta: false
hideSummary: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "/img/osa/fedora-virtualbox.jpg" # image path/url
    alt: "virtualbox logo" # alt text
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/mhrk04/mhrk04.github.io/edit/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

## Installlation of VirtualBox

###	Download the latest version of VirtualBox application for Windows

1. [Download Link](https://download.virtualbox.org/virtualbox/7.0.12/VirtualBox-7.0.12-159484-Win.exe)

2. Save to Download folder.

### Installation of VirtualBox

1.	Doubleclick on the `VirtualBox-7.x.x.exe` file

2.	Follow the installation step by step dialogue-boxes until Finish

3.	Install [Ext.Pack](https://download.virtualbox.org/virtualbox/7.0.12/Oracle_VM_VirtualBox_Extension_Pack-7.0.12.vbox-extpack). Complete it.


##	Installation of Fedora 38

>  Use torrent for fastest download speed.

### Download ISO file

- [Fedora 38 use http](https://download.fedoraproject.org/pub/fedora/linux/releases/38/Workstation/x86_64/iso/Fedora-Workstation-Live-x86_64-38-1.6.iso)


> Torrent Client for Windows: [transmission](https://github.com/transmission/transmission/releases/download/4.0.4/transmission-4.0.4-x64.msi)

- [Fedora 38 Torrent file](https://torrent.fedoraproject.org/torrents/Fedora-Workstation-Live-x86_64-38.torrent)

###	Setting up VirtualBox environment for Fedora38

```
Name: Fedora38
CPU Core: 1
RAM: 4 GB
HDD: 20 GB
Attached Fedora-Workstation-Live-x86_64-38-1.6.iso to Storage
```

`Setting>Storage>Storage Device>Controller: IDE`

`Click Empty Disk and Choose a Disk File`

![](https://pureinfotech.com/wp-content/uploads/2021/05/virtualbox-manager-mount-iso.jpg)


### Start the Installation Process in VirtualBox

1. Click the Start Button on VirtualBox Manager with Fedora38 selected

2. Choose Install Fedora from the DialogBox

3. Set the Installation Language: English

4. Set the Installation Destination: Automatic(click Done)

5. Click Begin Installation ..  until Finish

### VirtualBox Setting after installation complete

Unmount ISO file from storage

### Reboot Fedora38 Linux:

1. Start Setup Click next, next skip

2. At the AboutYou Page: 
    - Set your fullname, username click next
    - Set your password and clik next
    - Click Start Using Fedora Linux

