---
title: "Mastering Linux Administration Series Part 2"
date: 2023-10-19T17:41:22+08:00
weight: 2
tags: ["Linux", "Administration"]
author: "Haziq Rohaizan"
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
---
## File System and Permissions

Welcome back to the "Mastering Linux Administration" series. In this second part, we'll explore the fundamental aspects of the Linux file system and permissions. Understanding these concepts is crucial for effective system administration.

## File System Hierarchy

Linux has a well-organized file system hierarchy that forms the backbone of the operating system. Key directories include:

- `/` (root): The base of the file system.
- `/home`: Home directories for user-specific data.
- `/var`: Variable data files (e.g., logs, mail, spool).
- `/etc`: Configuration files.
- `/bin` and `/usr/bin`: Binary executables.
- `/lib` and `/usr/lib`: Libraries.

Knowing these directories and their purposes is essential for navigating the Linux file system efficiently.

## Navigating the File System

You navigate the file system using commands like `cd` to change directories and `ls` to list the contents. Here are some commonly used commands:

- To navigate to your home directory: `cd ~`
- To list files and directories in the current location: `ls`
- To change to a specific directory, e.g., `/var/log`: `cd /var/log`
- To move up one directory: `cd ..`

## File and Directory Operations

Linux provides several commands for file and directory operations. Here are a few you'll frequently use:

- `touch`: Create an empty file.
- `mkdir`: Create a new directory.
- `rm`: Remove files or directories. Be cautious, as this operation is irreversible.
- `cp`: Copy files or directories.
- `mv`: Move or rename files and directories.

Remember that many of these commands can be combined with options for more control. For example, `rm -r` is used to remove directories and their contents.

## File Permissions

Linux uses a robust permission system that ensures the security of files and directories. Each file or directory has three sets of permissions:

- **Owner Permissions**: Control what the owner of the file or directory can do.
- **Group Permissions**: Control what members of the group associated with the file or directory can do.
- **Others Permissions**: Control what everyone else can do.

These permissions are represented using symbols such as `r` (read), `w` (write), and `x` (execute). You can change permissions using the `chmod` command.

## Special Permissions

In addition to basic file permissions, Linux has special permissions, including:

- **SUID (Set User ID)**: Allows a program to be executed with the privileges of the file's owner.
- **SGID (Set Group ID)**: Allows a program to be executed with the privileges of the file's group.
- **Sticky Bit**: Protects files within directories from being deleted by others.

Understanding and managing these special permissions is crucial for certain system administration tasks.

In the next part of our series, we will delve into user and group management, covering how to create and manage user accounts and groups, and the concepts of user privileges and security. Stay tuned for more Linux administration knowledge.
