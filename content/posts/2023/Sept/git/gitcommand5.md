---
title: "Mastering Git Commands: Part 5"
date: 2023-09-30T06:09:55+08:00
weight: 5
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

Welcome to the fifth and final installment of our series on advanced Git commands. In this part, we'll dive even deeper into Git's capabilities, exploring some lesser-known but highly useful commands and techniques.

## Git Bisect Automated

While we previously covered the `git bisect` command for manually finding the commit that introduced a bug, Git also provides an automated way to perform a bisect. You can define a script or command that returns whether a specific commit is good or bad, and Git will automatically search for the commit that introduced the issue.

Here's how to start an automated bisect:

```bash
# Start the automated bisect process
$ git bisect start

# Mark the current commit as bad
$ git bisect bad

# Mark a known good commit
$ git bisect good <commit_hash>

# Git will use your script/command to find the problematic commit
```

## Git Rerere

`git rerere` stands for "reuse recorded resolution" and is incredibly helpful when dealing with merge conflicts. It records how you resolved previous conflicts and can automatically apply those resolutions to future conflicts.

Enable `git rerere`:

```bash
$ git config --global rerere.enabled true
```

## Git Notes

Git notes allow you to attach additional information to a commit without altering the commit itself. They are often used to record information related to code reviews, issue tracking, or documentation.

Add a note to a commit:

```bash
$ git notes add -m "Additional information"
```

## Git Archive All Branches

To create archives for all branches in a repository, you can use a loop in your shell. This is especially useful when you want to archive the entire project history for backup or distribution.

```bash
for branch in $(git branch --format="%(refname:short)" --sort=-committerdate); do
  git archive --format=zip --output=$branch.zip $branch
done
```

This script iterates through all branches, creates a zip archive for each, and names them after the branch names.

## Git Hooks: Pre-push

The pre-push Git hook allows you to run scripts or checks before pushing your changes to a remote repository. This is useful for ensuring code quality or running tests before sharing your code with others.

To create a pre-push hook, you need to add an executable script named `pre-push` in the `.git/hooks` directory of your repository.

## Conclusion

With these advanced Git commands and techniques, you've reached a high level of Git proficiency. Git is a versatile and powerful version control system, and mastering these commands can make your development workflow smoother and more efficient.

As you continue to work with Git, remember that there is always more to learn and explore. Git offers a wealth of features and customization options, and adapting them to your specific workflow can make a significant difference in your productivity and collaboration efforts. Happy coding!