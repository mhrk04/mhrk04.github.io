---
title: "Setup Hugo"
date: 2022-05-01T00:38:49+08:00
draft: false
showToc: true
TocOpen: true
tags: ["IT","Linux"]
cover:
    image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/af/Logo_of_Hugo_the_static_website_generator.svg/1024px-Logo_of_Hugo_the_static_website_generator.svg.png" # image path/url
    alt: "<alt text>" # alt text
---

# Cara Setup Hugo Static Site di Github Pages
> + **Bahan ini disalin terus daripada website [hackmd](https://hackmd.io/bNjRJTVxQ_u6r5GfwSveOA?edit). Hanya tujuan rujukan semata-mata. Ada beberapa bahagian diubah.**
> + **Tutorial boleh ditonton di youtube 
    - [Tutorial: Blogging with Hugo and GitHub Pages-Sarah Gibson](https://www.youtube.com/watch?v=_STFQc9Y2zY)**
    
> Saya akan membawa anda melalui penciptaan tapak web anda sendiri, dihoskan pada GitHub Pages dan dibina dengan Hugo. Anda boleh melihat contoh tapaknya dipautkan di bawah.
>
> - website : <https://mhaziqrk.uk> (website ini)
> - Repo : <https://github.com/mhrk04/mhrk04.github.io/tree/main>

## 🎯 Objektif

- Bina kandungan html daripada Markdown menggunakan [Hugo](https://gohugo.io/)

- Lancarkan kandungan sebagai tapak web statik menggunakan [GitHub Pages](https://pages.github.com/)

- Automasikan proses pelancaran dengan [Continuous Deployment](https://www.atlassian.com/continuous-delivery/continuous-deployment) melalui [GitHub Actions](https://github.com/features/actions)

- Fahami cara mencipta dan membenamkan kandungan dengan Hugo

## 📌 Keperluan

- Akaun Github
  - Anda boleh [sign up secara percuma](https://github.com/join)

- Terminal
  - [Linux](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners)
  - [Mac](https://www.businessinsider.com/how-to-open-terminal-on-mac?r=US&IR=T)
  - Windows: [Linux Bash](https://www.laptopmag.com/uk/articles/use-bash-shell-windows-10) **(preferred)**, [Command Prompt](https://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/)
        - Jika menggunakan command prompt, beberapa arahan yang saya gunakan di bawah akan berbeza dan anda mungkin ingin merujuk [cheatsheet](http://www.cs.columbia.edu/~sedwards/classes/2015/1102-fall/Command%20Prompt%20Cheatsheet.pdf)
- `git` version control
  - [Panduan pemasangan](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) untuk semua sistem operasi
- `hugo`
  - [Panduan pemasangan](https://gohugo.io/getting-started/installing/) untuk semua sistem operasi
- text editor pilihan ! Contoh:
  - VSCode
  - nano
  - gedit
  - Notepad++
  - emacs
  - vim

## 🤷🏻‍♀️ Adakah saya perlu menggunakan terminal?

Ya, hanya sedikit! GitHub menawarkan templat [Jekyll](https://jekyllrb.com/) terbina dalam yang boleh diakses melalui tetapan repositori GitHub. Lihat panduan [di sini](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).


<!-- belum translate -->

## ❓ Ok... kenapa Hugo dan bukan Jekyll?
First time terjebak dengan static site generator. Jadi, hugo ialah static site generator pertama saya cuba

- **Menggunakan Hugo menjadikan repositori yang lebih bersih.**

Jekyll memerlukan banyak "barangan" tambahan (seperti templat gaya untuk pemaparan html) untuk dikomit terus ke repositori yang menyukarkan saya untuk bersenam _di mana_ saya sepatutnya meletakkan sesuatu. Hugo menggunakan [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) untuk menyediakan bahan yang sama ke tapak web anda tanpa benar-benar memasukkannya. 

| ![repo_layout_with_jekyll](https://i.imgur.com/lmRvdK7.png) | ![repo_layout_with_hugo](https://i.imgur.com/lG7MsYs.png) |
| :---: | :---: |
| Repo layout with Jekyll | Repo layout with Hugo |

- **Binaan Hugo lebih pantas daripada binaan Jekyll.**

Saya hanya akan membiarkan tangkapan skrin bercakap untuk diri mereka sendiri tentang yang ini... Tetapi pada asasnya, membina dengan Hugo agak serta-merta, manakala Jekyll boleh mengambil masa beberapa minit untuk membina.

| ![build_time_with_jekyll](https://i.imgur.com/htSXcut.png) | ![build_time_with_hugo](https://i.imgur.com/eZsKqrG.png) |
| :---: | :---: |
| Build time with Jekyll | Build time with Hugo |

- **Hugo mempunyai kebergantungan(dependencies) yang jauh lebih sedikit daripada Jekyll.**

Hugo dibina di atas [Go](https://golang.org/), manakala [Jekyll memerlukan Ruby, RubyGems (dan pengikat untuk memasangnya), GCC (sejenis pengkompil) dan [Make](https://jekyllrb.com/docs/#prerequisites) - kesemuanya ditambah sebagai persekitaran yang sukar untuk disediakan dan diselenggara.

| ![broken_jekyll_build](https://i.imgur.com/MCu2RZd.png) |
| :---: |
| 😱😱😱 |

Ini bukan untuk mengatakan bahawa Jekyll tidak mempunyai _sebarang_ positif! Sebagai contoh, ia mempunyai ekosistem plugin yang lebih kaya daripada Hugo. Walaupun, saya tidak perlu menggunakan plugin _hanya_ untuk menerbitkan catatan blog semasa saya menggunakan Jekyll, dan setakat ini Hugo telah memenuhi semua keperluan blog saya.

Anda boleh membaca lebih lanjut tentang perbezaan antara Hugo dan Jekyll [di sini](https://opensource.com/article/17/5/hugo-vs-jekyll).


> # Selebihnya dalam bahasa inggeris
## 🏃🏻‍♀️ Let's go!

:::info
:wave: I will be demonstrating using another GitHub account I own, `HelmUpgradeBot`, so as not to interfere with my currently deployed website.
:::

### 1️⃣ Create and Setup your repository on GitHub

In this first section, we will create the repository that will host our website on GitHub. We will do this entirely in the browser.

1. Go to https://github.com and sign in to your account
2. In the top, right-hand corner of the browser, click the plus `+` symbol and select "New repository" from the dropdown menu.
3. Give your repository the name `YOUR_USERNAME.github.io`, filling in your username as appropriate. This is a special GitHub repository that will act as your website. Make sure that it is **public**! (You can have private GitHub Pages sites, but they cost money!)
    - Also add a README file to your repository and a license (I've used MIT in the example below but you might prefer [Creative Commons](https://github.com/idleberg/Creative-Commons-Markdown)).
    - Once you're happy, click "Create repository"

| ![new_repo_page](https://i.imgur.com/MArQIPr.png) |
| :---: |
| Example of how to fill in GitHub's create repository form |

:::warning
:warning: At this point, I will add myself as a collaborator to the repository. This is because I have created this repo with a different account but will push to it using my usual account. **YOU DO NOT NEED TO DO THIS.** It just saves me a load of faff.
:::

4. Once your GitHub repo has been created, click the large, green "code" button in the top-right, make sure "HTTPS" is selected, and click the clipboard icon to copy the contents of the text box.

| ![github_repo](https://i.imgur.com/xmGrx9l.png) |
| :---: |
| Where to find the address of your GitHub repo |

### 2️⃣ To the Terminal

Now we will "clone" our GitHub repository - meaning we will add a copy of it to our local machines. This is where we will make changes to our repository.

1. Open up your terminal app on your machine
2. Change to a "sensible" directory somewhere on your filesystem.
   - This could be `Desktop`, or maybe you have a folder called `projects` - wherever makes sense to you is the right place to go! I have a `source/github` folder where I keep my local repos, so I'll change into there.

    ```bash
    cd source/github
    ```

3. Now clone the repository using the `git clone` command and pasting the address we copied in step 4 of section 1.

    ```bash
    # Replace `HelmUpgradeBot` with your username
    git clone https://github.com/HelmUpgradeBot/HelmUpgradeBot.github.io.git
    ```

4. `git clone` will have created a new directory named after your repo, containing all the files currently in your repo (only the README and LICENSE files so far!) You can use the command `ls` to check this. Now change into that directory.

    ```bash
    # Replace `HelmUpgradeBot` with your username
    cd HelmUpgradeBot.github.io
    ```

5. The first action to take in good [gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) is to create a new branch to work on, so we are not saving our work to the `main` branch until we are ready. I'm going to call my new branch `setup-hugo`.

    ```bash
    git checkout -b setup-hugo
    ```

6. And now we use hugo to create our website! The below command will auto-generate all of the structure we need to generate html files using hugo's site template. The most important file this command will create is `config.toml` which will allow us to control the look and feel of our site. (:sparkles: [Click here](https://learnxinyminutes.com/docs/toml/) for a tangent into the TOML file format! TL;DR it's a simpler form of YAML :sparkles:)

    ```bash
    hugo new site . --force
    ```

    :::info
    :wave: Some things to note about the above command:
    - The `.` means "Create the site right here please", not in another directory.
    - We needed to use the `--force` flag as hugo would have complained that our directory wasn't empty - remember the README and LICENSE? Using `--force` means that hugo will ignore those files when it generates the site.
    :::

7. Next we will add a theme. You can choose any of the free themes available at https://themes.gohugo.io/ but, for this tutorial, we will use [Anatole](https://themes.gohugo.io/anatole/). Add the theme to your repository using the `git submodule` command.

    ```bash
    git submodule add https://github.com/lxndrblz/anatole.git themes/anatole
    ```
    :::info
    :wave: Now under the `themes/anatole` directory, we will have checked out a single reference of the anatole repository to build the content from.
    :::

8. Now we need to update `config.toml` to use the theme. Open up the file in your favourite text editor and add the following line to the bottom.

    ```toml
    theme = "anatole"
    ```

    While you have the config file open, let's make a few more edits to personalise our site. The templates provide a guide on common configuration options - Anatole's guide is [here](https://themes.gohugo.io/anatole/#modifying-the-configtoml).

    Firstly, I strongly recommend updating the `baseURL` field to be that of our GitHub repository, like so:

    ```toml
    # Replace `HelmUpgradeBot` with your username
    baseURL = "https://HelmUpgradeBot.github.io/"
    ```

    Another _super useful_ field to add here is the one that will enable the rendering of emojis in your posts :wink: 

    ```toml
    enableEmoji = true
    ```

    We are now going to create a new section in our config file called `[params]` and list some more metadata about our site there.

    Give your website a cool name in the `title` field, describe what your site is about in the `desription` field, and add your name under the `author` field:

    ```toml
    [params]
    title = "A Bot with a Blog"
    author = "HelmUpgradeBot"
    description = "Automatic blogging from a GitHub bot"
    ```

    All together, your config file should now look like this:

    ```toml=
    baseURL = "https://HelmUpgradeBot.github.io/"
    languageCode = "en-us"  # Update to "en-gb" if you prefer, or another language!
    theme = "anatole"
    enableEmoji = true

    [params]
    title = "A Bot with a Blog"
    author = "HelmUpgradeBot"
    description = "Automatic blogging from a GitHub bot"
    ```

    Make sure to save the file!

    :::warning
    :warning: Some of the information I've asked you to add to your `config.toml` file will be specific to the "anatole" theme and will not work if you swap themes. You shoud always check the documentation and example site of the theme you wish to use as they will outline what fields can be used and what their expected values will be.
    :::

9. Now check your site builds by running the below command in your terminal, and then visiting `http://localhost:1313` in your browser.

    ```bash
    hugo server
    ```

Our blog doesn't look very exciting yet, but it's good to know that it works! Let's save what we have and think about how to get it online.

**Close your browser window displaying your website and run `Ctrl+C` in your terminal to stop the hugo server command.**

### 3️⃣ Push to GitHub

1. First of all, we need to tell git to track all of the changes we have created. We do this by **adding** them to git's staging area.

    ```bash
    git add .
    ```

    :::info
    :wave: As we saw before, here the `.` means "please add everything in this current location."
    :::

    If you now run `git status` you should see a similar output as below.

    ```bash
    $ git status
    On branch setup-hugo
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
        new file:   .gitmodules
        new file:   archetypes/default.md
        new file:   config.toml
        new file:   themes/anatole
    ```

2. To tell git to make a snapshot (or "commit") of the current state of our files, we use the `git commit` command, passing the `-m` flag in order to leave a message about what we've changed.

    ```bash
    git commit -m "Initial setup of blog site"
    ```

    The output should look similar to below.

    ```bash
    $ git commit -m "Initial setup of blog site"
    [setup-hugo 62d794e] Initial setup of blog site
     4 files changed, 19 insertions(+)
     create mode 100644 .gitmodules
     create mode 100644 archetypes/default.md
     create mode 100644 config.toml
     create mode 160000 themes/anatole
    ```

    :::info
    :wave: Now if we run `git status` again, we should see the message `nothing to commit, working tree clean`
    :::

3. Now we push this commit from our local commit up to the GitHub server using the `git push` command. In the below command, `origin` is a reference to the original repo we setup on GitHub, and `setup-hugo` represents an instruction to create a new branch on the GitHub-hosted repo with the same name as our locally-created branch.

    ```bash
    git push origin setup-hugo
    ```

4. If we head back onto GitHub to our repo's page, we should now see a banner informing us that a branch has been updated and providing us with an option to "Compare & pull request". Click that big, green button!

| ![updated_github_page](https://i.imgur.com/NmyOTOJ.png) |
| :---: |
| GitHub repo page with a banner and "Compare & pull request" button |

You will be redirected to GitHub's interface for opening a Pull Request (PR). Give your PR an informative title and a descriptive summary in the relevant boxes, then click "Create pull request".

If we had any tests for our website, this is where they'd run before we merged the PR. However, we'll set up our tests next, so go ahead and click "Merge pull request", followed by "Confirm merge".

If you head back over to the repo's landing page, you'll see our changes have now been added to the `main` branch - but that doesn't mean our blog is live and deployed yet!

| ![updated_repo_home](https://i.imgur.com/uhopm0H.png) |
| :---: |
| The GitHub repo's `main` branch with the hugo files now added to it |

First, let's update our local copy of the repo and then we can add a GitHub Action workflow to automatically deploy our website for us.

In your terminal, run the following:

```bash
git checkout main  # Switch back to the main branch
git pull           # Pull the changes to the main branch down from GitHub
```

### 4️⃣ Continuous Deployment

The concept of Continuous Deployment is as follows:

> For every change we integrate or merge into our GitHub repo, a fresh version of our website should be created and deployed automatically for us.

In this section, we will create a workflow that will achieve this for us. It will run on [GitHub Actions](https://docs.github.com/en/actions).

1. Let's start by checking out a new branch in our local repo.

    ```bash
    git checkout -b add-cd
    ```

2. GitHub Actions are automatically triggered by files that are stored in a special folder called `.github/workflows`. So let's create that folder!

    ```bash
    mkdir -p .github/workflows
    ```

    :::info
    :wave: The `-p` flag here means "If the parent directory doesn't already exist (i.e. `.github/`), then please create that too." Try running the above command without this flag first and see what error message you get!
    :::

3. Create a `cd.yml` (`cd` is short for **C**ontinuous **D**eployment :wink:) file inside the `.github/workflows` folder and open it in your favourite text editor. (:sparkles: [Click here](https://blog.stackpath.com/yaml/) for a tangent into the YAML (`.yml`) file format! :sparkles:)

4. I've created a workflow for us to use below which you should feel free to copy and paste into your `cd.yml` file, and then we'll go through each section.

:::warning
:warning: Whitespace **matters** with YAML so be careful when you copy and paste!
:::

```yaml=
name: Build and Deploy Site

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build-and-deploy-site:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v2
        with:
          submodules: true
          fetch-depth: 0

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'

      - name: Build site with Hugo
        run: hugo --minify

      - name: Check HTML
        uses: chabad360/htmlproofer@master
        with:
          directory: "./public"
          arguments: --only-4xx --check-favicon --check-html --assume-extension --empty-alt-ignore --disable-external
        continue-on-error: true

      - name: Deploy to GitHub Pages
        if: github.event_name == 'push' && github.ref == 'refs/heads/main'
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

- The `name` parameter on line 1 defines what our workflow should be called
- The `on` block beginning on line 3 defines what events should trigger our workflow to run. We have two defined here:
    - `on.push.branches = [main]`: This tells GitHub Actions to run the workflow whenever a push is made to the `main` branch. This is most commonly when a PR is merged.
    - `on.pull_request.branches = [main]`: This tells GitHub Actions to run the workflow every time a PR intending to merge something into the `main` branch is opened.
- The `jobs` section beginning on line 11 defines which jobs the workflow will run when triggered. We have one job to run called `build-and-deploy-site` (defined on line 12) and we have requested the latest version of the Ubuntu Operating System to run this job on (defined on line 13; Windows and Mac OS's are also available to execute jobs).
- The `steps` section beginning on line 14 defines each step involving in running the job
    - Step 1 (line 15) is a checkout step. This clones the repo like we did manually in step 3 of section 2. The `fetch-depth: 0` line asks GitHub to not download the full repo history, only the most recent commit, and the `submodules: true` line asks GitHub to also checkout the submodules we depend on. Without this, our `themes` folder won't be populated with the info we need to build the site!
    - Step 2 (line 21) installs the latest version of Hugo
    - Step 3 (line 26) builds the site using Hugo. The `--minify` flag ensures that the output HTML files are compressed to take up the minimum amount of space required. The ouput files are stored in a folder called `public/`.
    - Step 4 (line 29) runs a tool called `htmlproofer` over the generated HTML files in `public`. This tool checks for things like broken links across the site.
    - Step 5 (line 35) will commit the HTML files to a new branch on our repo called `gh-pages`. It only publishes the HTML files contained in the `public` directory as they are the only ones required to create the site at this point.
        - Note this step has an `if` statement (line 36) that states this step should only be executed when the event that triggered the workflow was a push to the `main` branch (most commonly a merged PR). This prevents the live website being redeployed by unreviewed/unapproved changes in a PR.
        - This step also requires a secret `GITHUB_TOKEN` (line 39). You do not have to worry about creating and/or storing this token. It is a special token that is automatically generated by GitHub for every triggered workflow run and allows the workflow to commit and publish new branches.

Add, commit and push the `cd.yml` file to GitHub as we did before.

```bash
git add .github/workflows/cd.yml
git commit -m "Add a GitHub Actions workflow to build and deploy the site"
git push origin add-cd
```

Create another PR in GitHub's browser interface as we did previously. You should see the check now running and report a status at the bottom of the open PR page! Merge the PR once the test has passed. At any point, you can click the "Actions" tab at the top of the GitHub page to see the status of your GitHub Action workflows.

We now need to configure some more settings for the GitHub repo.

1. Click the "Settings" tab along the top of the GitHub webpage.
2. Select "Branches" from the menu on the left-hand-side (4th option from the top).
3. We will add a branch protection rule to prevent changes that could break our site from being deployed. Click "Add rule".

| ![add_branch_protection_rule](https://i.imgur.com/ovFhyLT.png) |
| :---: |
| Add a branch protection rule to the repo |

4. In the "Branch pattern name" type `main`, then select the "Require status checks to pass before merging" box. Finally select the `build-and-deploy-site` status check from the list and click "Create" at the bottom of the page. (You may be asked to reenter your GitHub password.) This means that the `build-and-deploy-site` job **MUST** pass, otherwise merging the PR will be blocked.

| ![create_branch_protection_rule](https://i.imgur.com/NhMHYOz.png) |
| :---: |
| Create the branch protection rule |

5. Now select the "Pages" option from the left-hand-side menu (second option from the bottom). This is where we configure GitHub Pages to host the website.
6. In the "Source" section, select `gh-pages` from the "Branch" dropdown and leave the folder dropdown as `/ (root)`. Then click "Save".

| ![configure_github_pages](https://i.imgur.com/hrXDSUl.png) |
| :---: |
| Configure GitHub Pages in the repo Settings |

7. After a few moments, refresh the page. The banner along the top should now be green and read "Your site is published at `https://YOUR-USERNAME.github.io`". Click the link in the browser and see your site live!

:tada: :tada: :tada: **Congratulations! Your site is now live on GitHub Pages!** :tada: :tada: :tada:

It's still a little bare though, so let's update our local repo in our terminal and then add some content.

```bash
git checkout main
git pull
```

### 5️⃣ Generating Content

Let's start to make our site a little more attractive by adding some content :sparkles: 

First, check out a new branch to add content to:

```bash
git checkout -b adding-content
```

#### Profile Pic

It'll be good for people to know who we are by adding a photo of us or a logo that reflects our branding!

1. Images go into a special folder that Hugo will parse when generating the HTML - so let's create that folder!

    ```bash
    mkdir -p static/images
    ```

2. Now copy an image (of you, a logo, your pet!) into this folder. You can do this by just saving an image directly here or using the below bash command. I'm going to call my image `profile_pic.png`. What you call it isn't really important, just remember it!

    ```bash
    # Example only - this command won't actually work!
    cp /path/to/my/picture.png ./static/images/profile_pic.png
    ```

3. We let Hugo know where our profile picture is by adding the following line to the bottom of our `config.toml` file.

    ```toml
    profilePicture = "images/profile_pic.png"
    ```

    :::info
    :wave: Notice how we didn't have to define the path as `static/images/profile_pic.png` here? That's because `static` is a special folder to Hugo that it knows how to parse. In fact, it's called `static` as Hugo won't modify these files in any way, just import them into the HTML files it creates - hence they are "static".
    :::

4. Run the `hugo server` command again and visit `http://localhost:1313` in your browser. You should now see your image on your site! :tada: 

| ![homepage_with_profile_pic](https://i.imgur.com/SbOddIV.png) |
| :---: |
| Blog homepage with profile picture |

#### Creating a blog post

Next let's add our first blog post! This is equivalent to creating a new Markdown file with some extra metadata that Hugo will read. Hugo has a built in command to generate new Markdown files with the appropriate metadata and it will deposit all of these in the `content` folder. The command looks like this:

```bash=
# Example only - don't run this!
# (It'll work, but it's probably not what you want)
hugo new path/to/content.md
```

:::info
:wave: If any of the folders `path/` or `to/` don't already exist under `content/`, Hugo will create them automatically.
:::

1. So let's create a new blog post!

    ```bash
    hugo new blog/my-first-blog.md
    ```

    This will create the `my-first-blog.md` Markdown file in the `blog` folder underneath the `content` folder.

2. If you open this file, you will see that it is not empty!

    ```
    ---
    title: "My First Blog"
    date: 2021-05-06T13:40:20+01:00
    draft: true
    ---
    ```

    This is the metadata Hugo generates that we talked about before. Hugo has prefilled the `title` field from the name of the Markdown file, the timestamp of when the file was created, and it has automatically put the file into draft mode.

    :::info
    :wave: Draft mode means that Hugo will **NOT** build and publish this file unless the `--buildDrafts [-D]` flag is passed to the `hugo server` command or the metadata is changed to `draft: false`
    :::

    You can edit these fields as you wish. I **strongly recommend** updating the `draft` field to `false` right now so that it will automatically build when this file is merged to `main`.

    You can then write your content underneath the metadata field as you like. I'm just going to leave the massage "Hello World! :earth_africa:" All together, the file looks like this:

    ```=
    ---
    title: "My First Blog"
    date: 2021-05-06T13:40:20+01:00
    draft: false
    ---

    Hello World! :earth_africa:
    ```
    
3. We'll edit the `config.toml` again to place our blog post on the homepage of our site. And the following line to the bottom of the file:

    ```toml
    mainSections = ["blog"]
    ```

4. Run the `hugo server` command again and visit `http://localhost:1313` in your browser. You should now see your blog post listed on your site with, as promised, a properly rendered emoji! :tada: You can then click through to the full post.

| ![homepage_with_blog_post](https://i.imgur.com/a4tDtVw.png) |
| :---: |
| Homepage with a blog post listed |

**Close your browser window displaying your website and run `Ctrl+C` in your terminal to stop the hugo server command.**

#### Embedding External Content using Hugo Shortcodes

The beauty of using Markdown to build a blogsite is that it is a very simple file format - what you type is what is rendered. However, blogs often contain _more_ than just words (images, tweets, videos) and Markdown is not always equipped to cope with all of these extra sources. The solution would be to manually construct a HTML block to embed the content, which breaks the simplicity of the Markdown document.

| ![md_with_html](https://i.imgur.com/1Y35l5w.png) |
| :---: |
| An example of a Markdown file using HTML blocks to embed a Google calendar and Twitter timeline into a blog page |

Hugo's solution to this problem is to provide a set of [shortcodes](https://gohugo.io/content-management/shortcodes/#use-hugos-built-in-shortcodes) that handle this embedding in the backend for a range of external sources including instagram, twitter, youtube, and more. So let's experiment by adding a tweet to our blog post.

Earlier on, I sent a (slightly self-important looking :joy:) tweet claiming how cool HelmUpgradeBot is: https://twitter.com/drsarahlgibson/status/1390312389346828291

All we need to embed this tweet into our blog post is the tweet ID, or the **numeric** part of the tweet URL.

| ![tweet_id](https://i.imgur.com/7yDTkq4.png) |
| :---: |
| The ID of a tweet is the numerical section of the URL |


All together, the file now looks like this.

```=
---
title: "My First Blog"
date: 2021-05-06T13:40:20+01:00
draft: false
---

Hello World! :earth_africa:

```

Save and close the file, then rerun `hugo server` and visit `http://localhost:1313` in your browser again. The tweet won't show up in the short summary of the blog post on the homepage, but if you click through, it should be embedded in the full blog page! :tada: 

| ![blog_with_embedded_tweet](https://i.imgur.com/uD5enj2.png) |
| :---: |
| Blog post with embedded tweet |

**Close your browser window displaying your website and run `Ctrl+C` in your terminal to stop the hugo server command.**

Other shortcodes you will find useful:

- [`figure`](https://gohugo.io/content-management/shortcodes/) for linking an image from a URL
- [`ref` and `relref`](https://gohugo.io/content-management/shortcodes/) for creating links within your blog, such as to another post or section of a post

**info**
:wave: Want to add your own image to your site by committing it to GitHub? Add it to the `static/images` folder, as we did with the profile picture. You can then include the image using the standard Markdown syntax `![image_alt_text](images/my_image.png)`
:::

:::info
:wave: If you are feeling **super brave**, you can even [create your own shortcodes](https://gohugo.io/templates/shortcode-templates/) to embed specific content. Check out the ones I created [here](https://github.com/sgibson91/sgibson91.github.io/tree/main/layouts/shortcodes).
:::

#### Pushing to GitHub and Merging to `main`

Let's save what we've done to GitHub and set it live on the website using the same add, commit, push, open and merge Pull Request that we've used previously.

```bash
git add .  # Add everything we've changed
git commit -m "Add our first blog post to the website"
git push origin adding-content
```

1. On the GitHub interface, click "Create & pull request"
2. Give your PR an informative title and summary, then click "Create pull request"
3. After the continuous integration test has passed, click "Merge pull request" then "Confirm merge"

While waiting for CD/GitHub Pages to deploy the update, let's update our local repo.

```bash
git checkout main
git pull
```

Then visit `https://YOUR-USERNAME.github.io` in the browser to see your site live.

## 🏁 Conclusion

So here's what we've achieved over the course of this tutorial.

- We've setup a repository on GitHub with a Hugo site template and a theme via a git submodule
- We've added a Continuous Deployment pipeline that automatically builds our website and publishes it to GitHub Pages whenever we merge a change
- We've created a new post with Hugo and added content, including updating our profile picture and embedding content from external sources using shortcodes

From here, you can:

- Continue to use the site as it is and begin publishing your blogs
- Further customise your site by editing the `config.toml` file (see the [anatole documentation](https://github.com/lxndrblz/anatole/) and [my config file](https://github.com/sgibson91/sgibson91.github.io/blob/main/config.toml) for examples)
- Or try implementing a new theme from https://themes.gohugo.io/! You can do this by running the `git submodule add` command again with your new theme and then updating the `config.toml` file. Be warned, some settings we've used during this tutorial may break when changing themes!

I hope you've enjoyed learning how to get setup with Hugo and GitHub Pages. Happy blogging! :sparkling_heart: 