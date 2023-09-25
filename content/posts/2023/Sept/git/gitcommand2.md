---
title: "Advanced Git Commands: Part 2"
date: 2023-09-25T08:20:12+08:00
weight: 2
tags: ["Git","Linux"]
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
cover:
    image: "https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png" # image path/url
    alt: "Git Logo" # alt text
    caption: "Git Logo" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/mhrk04/mhrk04.github.io/edit/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

In the first part of our [Git commands guide](/posts/2023/sept/git/masteringgitcommandsadevelopersguide/), we covered the basics of Git, from initializing a repository to pushing and pulling changes from remotes. Now, let's dive into some more advanced Git commands and concepts that will help you take your version control skills to the next level.

##  Git Branching Strategies

Branching is a fundamental concept in Git, and understanding branching strategies can greatly improve your workflow, especially when collaborating with others. Here are a few strategies:

### Feature Branching

- Create a new branch for each new feature or bug fix.
- Work on the feature in isolation.
- Merge the feature branch back into the main branch when it's complete.

Example:

```bash
# Create a new feature branch
$ git checkout -b feature/new-feature

# Work on the feature, make commits

# Merge the feature branch into main
$ git checkout main
$ git merge feature/new-feature
```

### Git Flow

Git Flow is a branching model that defines specific branches for features, releases, and hotfixes. It's great for larger projects with multiple contributors.

- [Git Flow Cheat Sheet](https://danielkummer.github.io/git-flow-cheatsheet/)

## Git Rebase

Rebasing is an alternative to merging that can make your commit history cleaner by incorporating changes from one branch into another. It's commonly used to update a feature branch with the latest changes from the main branch.

Example:

```bash
# Start with a clean feature branch
$ git checkout feature/my-feature

# Fetch the latest changes from the main branch
$ git fetch origin main

# Rebase the feature branch on top of the main branch
$ git rebase origin/main
```

## Git Interactive Rebase

Interactive rebasing allows you to edit, squash, or reorder commits during the rebase process. It's useful for cleaning up your commit history before merging or pushing changes.

Example:

```bash
# Rebase the last 3 commits interactively
$ git rebase -i HEAD~3
```

This will open an interactive editor where you can pick, squash, or edit commits.

## Git Cherry-Pick

Cherry-picking is the process of applying a specific commit from one branch onto another. It can be helpful when you want to bring a single commit or a few commits from one branch to another.

Example:

```bash
# Cherry-pick a commit from another branch
$ git cherry-pick <commit-hash>
```

Replace `<commit-hash>` with the actual hash of the commit you want to cherry-pick.

## 5. Git Bisect

Git bisect is a powerful tool for finding the commit that introduced a bug. It uses a binary search algorithm to efficiently identify the faulty commit.

Example:

```bash
# Start the bisect process
$ git bisect start

# Mark the current commit as bad
$ git bisect bad

# Mark a known good commit
$ git bisect good <commit-hash>

# Git will guide you to the commit that introduced the bug
```

## Conclusion

These advanced Git commands and concepts should help you navigate complex version control scenarios, collaborate more effectively, and maintain a clean and organized Git history. Git is a versatile tool, and mastering these commands will make you a more efficient and confident developer. Happy coding!