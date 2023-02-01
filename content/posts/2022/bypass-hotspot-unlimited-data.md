---
title: "Bypass Hotspot Unlimited Data"
date: 2022-05-04T20:18:30+08:00
draft: false
showToc: true
TocOpen: false
tags: ["Mobile Data","Hotspot"]
cover:
    image: "https://scontent.fkul4-2.fna.fbcdn.net/v/t1.6435-9/65504877_452578658875147_953493524374880256_n.jpg?_nc_cat=109&ccb=1-5&_nc_sid=09cbfe&_nc_ohc=feRYryg-nK0AX_9m4Cg&_nc_ht=scontent.fkul4-2.fna&oh=00_AT-Ovyp5vINSoECSpIQOmWQV1eLdHnxhGqDRFL6EbOhpTA&oe=62988FB6" # image path/url
    alt: "just pic from other site" # alt text
    caption: "<text>" 
---

> Cara ini terpakai kepada semua simkad yang mempunyai plan unlimited data tetapi hotspot **tidak dibenarkan.**

Terdapat pelbagai cara yang boleh kita gunakan untuk bypass hotspot pada plan unlimited data. Antaranya :

# Solusi bypass yang ada :

## 1. Menggunakan Proxy

Cara ini lebih mudah kerana hanya perlu install aplikasi [http proxy](https://play.google.com/store/apps/details?id=com.gorillasoftware.everyproxy) pada phone dan hidupkan http/https proxy. Jangan lupa juga hidupkan hotspot seperti biasa.

Selepas dihidupkan, anda akan nampak
```
Hosts 0.0.0.0 exposed via xxx.xxx.xxx.xxx(IP Address)
Port 8080
Auth None
```
Copy ip `xxx.xxx.xxx.xxx` tu ltak kan setting proxy kat device yang tersambung ke hotspot. Walla, dah boleh guna internet.

## 2. Mengubah ttl(time to live) pada komputer

Ini tricky sikit. Cara ini yang saya tahu boleh buat kat komputer.

### Windows

Buka CMD dan Run As Admin

paste command di bawah 

```
netsh int ipv4 set glob defaultcurhoplimit=65
netsh int ipv6 set glob defaultcurhoplimit=65
```

### Linux

Buka terminal dan paste command di bawah

```
sudo sysctl -w net.ipv4.ip_default_ttl=65
```