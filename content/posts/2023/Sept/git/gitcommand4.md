---
title: "Mastering Git Commands: Part 4"
date: 2023-09-29T15:21:34Z
weight: 4
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

Welcome to the fourth and final installment of our series on advanced Git commands. In this part, we'll explore additional Git commands and techniques that can further enhance your Git proficiency and help you become a Git master.

## Git Revert

While `git reset` can be used to undo commits, it can be a risky operation, especially in shared repositories. `git revert` is a safer alternative that creates a new commit to undo the changes introduced by a previous commit.

To revert a commit:

```bash
$ git revert <commit_hash>
```

## Git Cherry-Pick Range

Cherry-picking multiple commits within a range is also possible. You can specify a range of commits to pick, making it a powerful way to transfer changes from one branch to another.

```bash
$ git cherry-pick <start_commit>^..<end_commit>
```

Replace `<start_commit>` and `<end_commit>` with the commit hashes you want to cherry-pick.

## Git Amend

Sometimes, you may need to make changes to the most recent commit. Instead of creating a new commit, you can amend the last commit:

```bash
# Make changes to your files

$ git add .
$ git commit --amend
```

This combines your staged changes with the previous commit, effectively rewriting the commit.

## Git Interactive Add

`git add -p` allows you to interactively stage changes within a file. This is useful when you have made multiple changes in a single file but only want to commit specific portions.

```bash
$ git add -p
```

Git will prompt you to select which changes you want to stage, allowing for fine-grained control.

## Git Archive

The `git archive` command is handy when you need to create a zip or tar archive of your Git repository's contents without including the Git history.

```bash
$ git archive --format=zip --output=archive.zip HEAD
```

You can replace `--format` with `--format=tar` if you prefer a tar archive. Adjust the `--output` flag to specify the archive file's name.

## Conclusion

Congratulations! You've now explored a range of advanced Git commands and techniques that will significantly boost your Git proficiency. Git is a powerful version control system that can adapt to various workflows and scenarios, and these commands provide you with the tools to manage your projects effectively.

As you continue to work with Git, remember that practice makes perfect. Experiment with different Git workflows, collaborate with others, and explore more advanced features to fully harness the capabilities of Git. Whether you're a solo developer or part of a team, Git is an indispensable tool in the world of software development. Happy coding!