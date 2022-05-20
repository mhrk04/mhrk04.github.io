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

# Use Your Laptop As A Server

> Tested on : Ubuntu 20.04 LTS

To disable entering the sleep mode I had to edit the `/etc/systemd/logind.conf` file and modify the line:

**Just uncomment the line by removing `#`**

from this :

```
#HandleLidSwitch=suspend
#LidSwitchIgnoreInhibited=no
#HandleLidSwitchDocked=ignore
```

to this :

```
HandleLidSwitch=ignore
LidSwitchIgnoreInhibited=no
HandleLidSwitchDocked=ignore
```


Then restart the OS via:

```
sudo service systemd-logind restart
```


Then you can close the laptop lid .