---
title: "Connecting to Github With SSH on Windows"
date: 2023-09-30T10:15:20+08:00
tags: ["Git", "Github", "SSH", "SSH Keys", "SSH Agent","Windows"]
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
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/mhrk04/mhrk04.github.io/edit/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

Secure Shell (SSH) is a cryptographic network protocol used for secure communication over unsecured networks. It's commonly used for securely accessing remote servers and services like GitHub. By setting up SSH on your Windows machine and linking it to your GitHub account, you can interact with your repositories using secure, encrypted connections. In this guide, we'll walk you through the steps to set up SSH on GitHub and Windows.

## Prerequisites

Before we begin, make sure you have the following:

- A GitHub account (if you don't have one, you can sign up [here](https://github.com/join)).
- Git installed on your Windows machine. You can download it from the official website: [Git Downloads](https://git-scm.com/downloads).

## Step 1: Generate SSH Key Pair

The first step is to generate an SSH key pair on your Windows machine. This key pair consists of a private key (which you should keep secret) and a public key (which you can share with services like GitHub).

1. Open a Git Bash terminal on your Windows machine. You can do this by searching for "Git Bash" in the Start menu.

2. In the Git Bash terminal, run the following command to generate an SSH key pair. Replace `<your_email@example.com>` with the email address associated with your GitHub account.

    ```markdown
    $ ssh-keygen -t ed25519 -C "<your_email@example.com>"
    ```

   Press Enter when prompted to save the key in the default location (`~/.ssh/id_ed25519`) and to set a passphrase (optional but recommended for additional security).

3. This will generate your SSH key pair. You can find your public key in `~/.ssh/id_ed25519.pub`. You can use a text editor like Notepad to open and view this file.

## Step 2: Add SSH Key to SSH-Agent

The SSH-Agent is a program that manages your SSH keys. To use SSH keys with GitHub, you need to add your private key to the SSH-Agent.

1. In the Git Bash terminal, start the SSH-Agent by running:

    ```markdown
    $ eval $(ssh-agent -s)
    ```

2. Add your private SSH key to the SSH-Agent:

    ```markdown
    $ ssh-add ~/.ssh/id_ed25519
    ```

   If you set a passphrase during key generation, you'll need to enter it now.

## Step 3: Add SSH Key to GitHub

Now that you have generated your SSH key and added it to the SSH-Agent, you can add it to your GitHub account.

1. Copy your public SSH key to the clipboard:

    ```markdown
    $ clip < ~/.ssh/id_ed25519.pub
    ```

2. Visit [GitHub](https://github.com) and log in to your account.

3. Click on your profile picture in the top right corner and select "Settings."

4. In the left sidebar, click on "SSH and GPG keys."

5. Click the "New SSH key" button.

6. Give your SSH key a title (e.g., "Windows SSH Key") and paste your public key into the "Key" field.

7. Click the "Add SSH key" button to save your key.

## Step 4: Test Your SSH Connection

To ensure that everything is set up correctly, you can test your SSH connection to GitHub.

1. In the Git Bash terminal, run the following command:

    ```markdown
    $ ssh -T git@github.com
    ```

   You might see a security warning; type "yes" to continue.

2. If everything is set up correctly, you'll receive a message like:

    ```markdown
    Hi <your_username>! You've successfully authenticated, but GitHub does not provide shell access.
    ```

   Congratulations! Your SSH connection to GitHub is working.

## Conclusion

Setting up SSH on GitHub and Windows is an essential step for secure and convenient interaction with your repositories. With SSH, you can securely push, pull, and clone repositories without the need to enter your GitHub password each time. This guide should help you get started with SSH on Windows and GitHub. Happy coding!
