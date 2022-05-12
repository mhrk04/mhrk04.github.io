---
title: "Ubuntu Server - Laptop Lid Ignore"
date: 2022-05-12T17:44:36Z
draft: false
showToc: true
TocOpen: false
tags: ["Ubuntu"]
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" 
---

# Use your Laptop As A Server

To disable entering the sleep mode I had to edit the `/etc/systemd/logind.conf` file and modify the line:

**Just uncomment the line by removing `#`**

```
#HandleLidSwitch=suspend
#LidSwitchIgnoreInhibited=no
#HandleLidSwitchDocked=ignore

```