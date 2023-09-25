---
title: "Advanced Git Commands: Part 3"
date: 2023-09-25T10:04:47+08:00
weight: 3
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

Welcome back to our series on advanced Git commands. In this installment, we'll explore even more powerful Git commands and techniques that can enhance your version control skills and streamline your development workflow.

## Git Submodules

Git submodules allow you to include other Git repositories within your own repository as subdirectories. This is particularly useful when you want to incorporate external libraries or dependencies into your project.

Here's how to add a submodule to your repository:

```bash
$ git submodule add <repository_url> <path_to_submodule_directory>
```

And to clone a repository that contains submodules, you'll need to initialize and update the submodules:

```bash
$ git submodule init
$ git submodule update
```

## Git Stash

Sometimes, you may need to switch branches or perform other operations while you have uncommitted changes in your working directory. Git stash allows you to temporarily save these changes and switch to another branch, after which you can reapply the changes.

Stash your changes:

```bash
$ git stash
```

List your stashes:

```bash
$ git stash list
```

Apply a stash:

```bash
$ git stash apply stash@{n}
```

## Git Reflog

The Git reflog (short for reference log) keeps a record of all the changes to your repository's branches, even if those changes were later removed or lost. It's an invaluable tool for recovering lost commits or branches.

View the reflog:

```bash
$ git reflog
```

Restore a lost branch or commit:

```bash
$ git checkout -b <branch_name> <commit_hash>
```

## Git Hooks

Git hooks are scripts that can be executed before or after specific Git events, such as committing, pushing, or receiving changes. You can use Git hooks to automate tasks like running tests, formatting code, or notifying team members.

Hooks are stored in the `.git/hooks` directory of your repository. You can find example hook scripts in that directory, which you can customize to suit your needs.

## Git Worktrees

Git worktrees allow you to work on multiple branches or commits simultaneously without needing to switch back and forth between them. Each worktree is essentially a separate working directory attached to your repository.

Create a new worktree:

```bash
$ git worktree add -b <branch_name> <path_to_worktree_directory> <starting_commit>
```

List existing worktrees:

```bash
$ git worktree list
```

## Conclusion

With these advanced Git commands and techniques, you're well on your way to becoming a Git expert. Git is a versatile tool that offers solutions to a wide range of version control challenges, and mastering these commands will make your development workflow more efficient and productive.

As you continue to work with Git, don't hesitate to explore the official Git documentation and experiment with different workflows and strategies. Git's flexibility and power make it an essential tool for developers and teams of all sizes. Happy coding!