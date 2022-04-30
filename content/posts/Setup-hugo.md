---
title: "Setup Hugo"
date: 2022-05-01T00:38:49+08:00
draft: false
showToc: true
TocOpen: true
tags: ["HUGO","Static Site"]
cover:
    image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/af/Logo_of_Hugo_the_static_website_generator.svg/1024px-Logo_of_Hugo_the_static_website_generator.svg.png" # image path/url
    alt: "<alt text>" # alt text
---

# Cara Setup Hugo Static Site di Github Pages

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
