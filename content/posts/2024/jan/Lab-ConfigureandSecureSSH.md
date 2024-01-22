---
title: "Lab : Configure and Secure SSH"
date: 2024-01-22T05:20:21Z
tags: ["Linux","SSH"]
author: ["Haziq Rohaizan"]
description: "Configure ssh on linux securely with best practice"
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
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page
# editPost:
#     URL: "https://github.com/mhrk04/mhrk04.github.io/edit/main/content/"
#     Text: "Suggest Changes" # edit text
#     appendFilePath: true # to append file path to Edit link
---

> Outcomes
>- Authenticate with SSH keys.
> - Prevent users from directly logging in as the root user over the ssh service.
> - Prevent users from logging in to the system with SSH password-based authentication.


## Generate passphrase-less SSH keys 