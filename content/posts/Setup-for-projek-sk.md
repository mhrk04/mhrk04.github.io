---
title: "Menyediakan lingkungan Pengembangan bagi Projek Sains Komputer"
date: 2022-04-29T22:25:02+08:00
draft: false
showToc: true
TocOpen: false
tags: ["IT","Sains Komputer","XAMPP"]
cover:
    image: "img/cover-page-design.png" 

---

# Menyediakan lingkungan Pengembangan bagi Projek Sains Komputer

> Amaran ! Laman sesawang ini menggunakan bahasa melayu rojak dan bercampur dengan bahasa inggeris. 

## 1) Memasang XAMPP

+ Link Muat Turun [XAMPP](https://www.apachefriends.org/download.html)

**Anda hanya perlu mengikut instruksi daripada installer tersebut.**<i>Tekan Next jer.</i>

> Pastikan anda memilih sistem operasi yang betul dan sistem anda sudah menyokong binaan 64bit.


## 2) Memasang VS Code
+ Link Muat Turun [VS Code](https://code.visualstudio.com/download)

> VS Code menyokong pelbagai binaan seperti 32bit, 64bit dan ARM.Pastikan semak terlebih dahulu spesifikasi komputer anda.
## 3) Memasang Extension pada VS Code dan menetapkan 'user snippet'

Extension yang dicadangkan :
1. Php Intelephense

> #### Perlu disable dahulu **PHP Language Features**
>
>> Pergi ke Extensions. Cari `@builtin php`. Disable PHP Language Features. Biarkan PHP Language Basics enabled untuk syntax highlighting.


2. Auto Rename Tag
3. Indent-rainbow
4. Beautify
5. HTML Snippet

Tetapkan User Snippets:

1. Tekan File>Preferences>User Snippets
2. Tekan *New Global Snippets* , kemudian type nama snippet **"html.json"**

Salin `html.json` ini :
```
{
	"PHP Tag": {
		"prefix": "php",
		"body": "<?php $1 ?>"
	},
	"Inline Echo": {
		"prefix": "phpp",
		"body": "<?= $$1; ?>"
	},
	"Input Label": {
		"prefix": "formel",
		"body": [
			"<label>",
			"\t${3:Username}",
			"\t<input type=\"${1:text}\" name=\"${2:username}\">",
			"</label>"
		]
	},
	"My Form": {
		"prefix": "myform",
		"body": "<form method=\"${1|get,post|}\" action=\"$2\">$3</form>"
	}
}
```

+ `setting.json` semasa
```
{
    "editor.tabSize": 2,
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "HookyQR.beautify",
    "explorer.openEditors.visible": 0,
    "[html]": {
        "editor.defaultFormatter": "HookyQR.beautify"
    },
    "explorer.confirmDelete": false,
    "editor.fontSize": 20,
    "editor.lineHeight": 40,
    "editor.fontFamily": "'Source Code Pro',Consolas, 'Courier New', monospace",
    "html.format.templating": true,
    "git.allowForcePush": true,
    "liveServer.settings.donotShowInfoMsg": true,
    "liveServer.settings.donotVerifyTags": true,
    "[php]": {
        "editor.defaultFormatter": "bmewburn.vscode-intelephense-client"
    },
    "git.confirmSync": false,
    "workbench.startupEditor": "none",
    "bracketPairColorizer.depreciation-notice": false,
    "files.exclude": {
        "**/.classpath": true,
        "**/.project": true,
        "**/.settings": true,
        "**/.factorypath": true
    },
    "git.autofetch": true,
    "workbench.colorTheme": "Noctis Minimus",
    "workbench.iconTheme": "vscode-icons"
}
```