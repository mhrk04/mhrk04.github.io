---
title: "Mastering Git Commands: Part 6"
date: 2023-09-30T08:46:02+08:00
weight: 6
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

In this continuation of our series on advanced Git commands, we'll explore some additional techniques and commands that can further enhance your Git proficiency.

## Git Stash Pop

In addition to `git stash apply`, you can use `git stash pop` to apply the most recent stash and remove it from the stash list in a single step. This can help you streamline your workflow when temporarily saving changes.

Apply and remove the most recent stash:

```bash
$ git stash pop
```

## Git Worktree Prune

When working with multiple worktrees, you may sometimes need to clean up stale or unused worktrees. The `git worktree prune` command helps you remove worktrees that no longer exist or are no longer needed.

Prune unused worktrees:

```bash
$ git worktree prune
```

## Git Rerere Clear

If you've enabled `git rerere` (reuse recorded resolution) and want to clear its recorded resolutions, you can use the following command:

```bash
$ git rerere forget <commit_hash>
```

This command makes Git forget the resolutions for a specific commit, allowing you to reapply them or resolve conflicts differently in the future.

## Git Push --force-with-lease

While `git push --force` allows you to forcefully push changes to a remote branch, it can be risky, especially in a collaborative environment. `git push --force-with-lease` is a safer option that only forces the push if the remote branch matches the expected state.

Forcefully push changes with lease:

```bash
$ git push --force-with-lease
```

## Git Bisect Log

When performing a `git bisect` operation to find a bug, you can use `git bisect log` to display the history of the bisect process, showing which commits were tested and marked as good or bad.

View the bisect log:

```bash
$ git bisect log
```

This log can be helpful for documenting the bisect process and understanding which commits were involved.

## Conclusion

With these additional advanced Git commands and techniques, you've expanded your Git toolkit even further. Git is a versatile version control system that provides solutions for a wide range of scenarios, from tracking code changes to collaborative development.

As you continue to work with Git, remember that practice, experimentation, and customization are key to becoming a Git expert. Adapt these commands to your specific workflow, and explore Git's capabilities to maximize your productivity and collaboration efforts. Happy coding!