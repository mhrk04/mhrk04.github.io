---
title: "Setting Up GPG to Verify Commits on Windows"
date: 2023-10-10T00:21:21+08:00
tags: ["git","github","Windows","GPG","PGP","signing","verification"]
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

Git is a powerful version control system that allows developers to track changes in their codebase. When collaborating on projects, it's essential to verify the authenticity of commits to ensure the integrity of the code. One way to achieve this is by using GPG (GNU Privacy Guard) to sign and verify commits. In this guide, we'll walk you through the process of setting up GPG to verify commits on a Windows machine.

## Prerequisites

Before you start, make sure you have the following prerequisites:

1. **Git**: Ensure Git is installed on your Windows machine. If not, download and install it from [Git's official website](https://git-scm.com/downloads).

2. **GPG**: Download and install GPG for Windows from the [GnuPG website](https://gnupg.org/download/).

## Setting up GPG

Follow these steps to set up GPG for commit verification on Windows:

### 1. Install GPG for Windows

1. Download the GPG installer for Windows from the [GnuPG download page](https://gnupg.org/download/).

2. Run the installer and follow the on-screen instructions to install GPG on your system.

### 2. Generate a GPG Key Pair

To sign your commits, you need to create a GPG key pair:

1. Open a Command Prompt or PowerShell window.

2. Enter the following command to generate a new GPG key pair:

   ```shell
   gpg --gen-key
   ```

3. Follow the prompts to configure your key. You'll be asked for your name, email address, and a passphrase. Make sure to use the same email address associated with your GitHub or GitLab account if you have one.

### 3. List Your GPG Keys

After generating your GPG key pair, list your keys to get the key ID:

```shell
gpg --list-keys
```

Look for the key you just created and note the key ID (it's the long string of numbers and letters next to "pub").

### 4. Configure Git to Use GPG

Now, you need to tell Git to use your GPG key for signing commits:

1. Open a Command Prompt or PowerShell window.

2. Configure Git to use your GPG key:

   ```shell
   git config --global user.signingkey <your-key-ID>
   ```

   Replace `<your-key-ID>` with the key ID from step 3.

3. Configure Git to always sign commits:

   ```shell
   git config --global commit.gpgsign true
   ```

### 5. Add Your GPG Key to GitHub (Optional)

If you're using GitHub, you can add your GPG key to your GitHub account to verify your commits on the platform:

1. Go to your GitHub account settings.

2. Click on "SSH and GPG keys."

3. Click on "New GPG key."

4. Paste your GPG key (use `gpg --armor --export <your-key-ID>` to get the public key) and click "Add GPG key."

### 6. Sign a Commit

Now that everything is set up, you can sign a commit:

1. Make changes to your repository.

2. Stage the changes using `git add`.

3. Commit the changes with the `-S` flag to sign the commit:

   ```shell
   git commit -S -m "Your commit message"
   ```

4. Push your changes to your remote repository.

### 7. Verify a Commit

To verify a commit, simply check for the "Verified" badge on GitHub or use the following Git command:

```shell
git log --show-signature
```

This command will display information about the commit, including its signature status.

That's it! You've successfully set up GPG to verify commits on your Windows machine. This added layer of security helps ensure the authenticity and integrity of your codebase when collaborating with others on your projects.
