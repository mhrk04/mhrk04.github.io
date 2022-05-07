---
title: "Vimtutor - Tutorial for newbie Vim user"
date: 2022-05-06T18:57:05+08:00
draft: false
showToc: true
TocOpen: true
tags: ["Vim","Tutorial","English Content"]
cover:
    image: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9f/Vimlogo.svg/1022px-Vimlogo.svg.png" # image path/url
    alt: "vim logo" # alt text
---
> Base On : VIM  Tutor - Version 1.7

> Install vimtutor on Fedora 35 : `sudo dnf install vim-enhanced`

# Introduction

Vim is a very powerful editor that has many commands, too many to
explain in a tutor such as this.  This tutor is designed to describe enough of the commands that you will be able to easily use Vim as an all-purpose editor.

The approximate time required to complete the tutor is 25-30 minutes, depending upon how much time is spent with experimentation.

It is important to remember that this tutor is set up to teach by use. That means that you need to execute the commands to learn them properly. If you only read the text, you will forget the commands!

Now, make sure that your `Shift-Lock key` is **NOT depressed** and press the   `j`   key enough times to move the cursor so that [Lesson 1.1](#lesson-11--moving-the-cursor) completely fills the screen.

## Lesson 1.1:  MOVING THE CURSOR

   **To move the cursor, press the `h`,`j`,`k`,`l` keys as indicated.**

```
      ^
      k      
< h        l >     
      j      
      v
```

>Hint:
>
> - The h key is at the left and moves left.
> - The l key is at the right and moves right.
> - The j key looks like a down arrow.

 1. Move the cursor around the screen until you are comfortable.

 2. Hold down the down key `j` until it repeats.
     Now you know how to move to the next lesson.

> NOTE: If you are ever unsure about something you typed, press `ESC` to place you in Normal mode. Then retype the command you wanted.

> NOTE: The cursor keys should also work. But, using `h` `j` `k` `l` you will be able to move around much faster, once you get used to it. Really!

## Lesson 1.2: EXITING VIM

> **NOTE**: Before executing any of the steps below, read this entire lesson!!

1. Press the `ESC` key (to make sure you are in Normal mode).

2. Type: `:q!` and `<ENTER>`. This exits the editor, DISCARDING any changes you have made.

3. When you see the shell prompt, type the command that got you into this tutor.  That would be: vimtutor <ENTER>

4. If you have these steps memorized and are confident, execute steps 1 through 3 to exit and re-enter the editor.

> NOTE: `:q!` `<ENTER>` discards any changes you made. In a few lessons you will learn how to save the changes to a file.

5. Move the cursor down to [Lesson 1.3](#lesson-13-text-editing---deletion).

## Lesson 1.3: TEXT EDITING - DELETION

  **Press  x  to delete the character under the cursor.**

  1. Move the cursor to the line below marked --->.

  2. To fix the errors, move the cursor until it is on top of the
     character to be deleted.

  3. Press the `x`  key to delete the unwanted character.

  4. Repeat steps 2 through 4 until the sentence is correct.

```
on vimtutor file
---> The ccow jumpedd ovverr thhe mooon.
```

  5. Now that the line is correct, go on to [Lesson 1.4](#lesson-14-text-editing---insertion).

> NOTE: As you go through this tutor, do not try to memorize, learn by usage.

## Lesson 1.4: TEXT EDITING - INSERTION

**Press  `i` to insert text.**

  1. Move the cursor to the first line below marked --->.

  2. To make the first line the same as the second, move the cursor on top of the first character BEFORE where the text is to be inserted.

  3. Press  `i` and type in the necessary additions.

  4. As each error is fixed press `ESC` to return to Normal mode.
     Repeat steps 2 through 4 to correct the sentence.

```
---> There is text misng this .
---> There is some text missing from this line.
```

  5. When you are comfortable inserting text move to [lesson 1.5]().

