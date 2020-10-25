---
toc: true
toc_sticky: true
toc_label: "My Table of Contents"
toc_icon: "cog"
header:
  overlay_image: /assets/images/gohugo-logo.jpeg
image:
  feature: /assets/images/gohugo-logo.jpeg
  thumb: /assets/images/gohugo-small.png
excerpt: "Simple scheme to switch to modules in a Hugo Academic based site under Linux Mint"
title: "GoHugo: time to move on to modules"
last_modified_at: 2020-10-25
categories:
  - Blog
tags:
  - Hugo
  - Academic
  - GitHub
---



## Hugo Academic: from _Theme_ to _Modules_ ##

I have a test site in Hugo environment with Academic theme.

The test site is hosted in GitHub.

Since September 2020, the structure of the theme has changed and is now controlled through modules.

This step has also been accompanied by a new name of the site building system:  the new name is **Wowchemy**.

I have found that the official guidelines for converting previous sites are a bit concise, especially for those who are not coders.

Here is the outline that I have followed in order to complete with success the passage under a Linux Mint operating system.

## Prerequisite: Go installation ##

In the _classic_ Academic Hugo theme it wasn't necessary to have a Go version working into the operating system.


Now it's necessary.

Then the prerequisite is to install a Go version: go to [Golang.org](https://golang.org/doc/install) and follow the instructions (dowload the newest release, extract it and adjust the PATH).

## The translation outline: from Academic to Wowchemy ##

Now you can translate your previuos Academic site to a Wowchemy site, following these steps:

- Place the cursor in the local folder where you store the site (i.e. `cd yoursitelocalfolder`)
- Remove or de-init the _Academic_ submodules: the fastest solution is the second one:
   - `rm -rf themes/academic` (which means: force the folder removal)
   - `rm -f .gitmodules` (which means: force the _.gitmodules_ file removal)
- Trasform your site in a module by typing: `hugo mod init github.com/(insert your Github username)/(insert your GitHub projectname)`
- Open che `config.toml` file but be careful that in _Academic_ **you will note find it in the root folder but in the `config/_default`subfolder** and add the following code:

```go
[module]
  [[module.imports]]
    path = "github.com/wowchemy/wowchemy-hugo-modules/wowchemy"
```

- Update the modules with `$ hugo mod get -u` and everything should be fine.

Now you can   enjoy your new _Wowchemy_ modular site by typing the _classic_ `hugo serve` command and push everything in GitHub with the usual _Git_ procedure.

Thank you for your attention.
