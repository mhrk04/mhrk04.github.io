---
title: "Run Command in Background on Linux"
date: 2022-05-20T16:11:26+08:00
draft: false
showToc: true
TocOpen: false
tags: ["Linux"]
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" 
---
> Tested on : Ubuntu Server 20.04 LTS

Today, I want to show you how to run linux command in background even the terminal close.

I will use rclone as example application to run in background. It's not difficult to run command in background. You just need to add `&` symbol and type `disown` command after the first command run in the background.

## Example :

```
rclone sync -P /mnt/disk4/pictures /mnt/disks/external/pictures > ./rclone-log.txt &
```
then run :
```
disown
```

> Rclone with `-P` tags will show the progress of sync

> The `>` symbol is to forward stdout to a file. So, the output not come out to the current session of terminal. This will able you to see the progress by run `tail -f ./rclone.txt` on the other terminal session.

***The ampersand will run the task in the background and `disown` will allow it to run even after you close your session. This will stop running once you reboot.***