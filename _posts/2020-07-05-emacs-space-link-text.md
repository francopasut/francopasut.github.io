---
toc: true
toc_sticky: true
toc_label: "My Table of Contents"
toc_icon: "cog"
header:
  overlay_image: /assets/images/emacs-logo.png
image:
  feature: /assets/images/emacs-logo.png
  thumb: /assets/images/200pxemacsicon.png
excerpt: "How to insert text links in Emacs Markdown-mode (`C-c C-l`) with spaces inside them"
title: "Emacs, Markdown-mode, insert spaces in text links created by the `C-c C-l` command"
last_modified_at: 2020-06-06
categories:
  - Editors
tags:
  - Emacs
  - Markdown
---



##  The reference environment: Emacs, Markdown-mode, insert a link ##




This article applies to the following environment:


- Emacs: GNU Emacs 26.3 (build 1, x86_64-pc-linux-gnu, GTK+ Version 3.22.30) of 2019-12-03
- Markdown Mode: markdown-mode-20200622.20
- OS: Linux Ubuntu 20.4 LTS, Linux Fedora 32

The problem in a few  words: You need to insert a link in a document written using Markdown-mode for Emacs and in the _Link text_ you need to insert one or more spaces.

The following are the steps:

1. Activate the command `C-c C-l`
2. Insert the URL of a link and press `Return`
3. Insert _text link_ with some spaces inside it ... **STOP!**

You could notice that the minibuffer does not accept the spaces!
You also  get a "_No match_" advice.

Is there  a bug? Have I made an error?

None of them.

It is a deliberate behavior of the plugin.


I recently opened a New Issue in jrblevin/markdown-mode and the solution was immediate.


## The official assistance service solution  ##

If you need to insert spaces in you Link text in Markdown-mode you can  use `C-q` followed by `space`.

`C-q` runs the command quoted-insert (found in global-map), which is an
interactive compiled Lisp function.



It reads the next input character and inserts it where you are typing.

If the next input character is a _space_ it inserts a _space_ in the minibuffer and you've solved the problem.

If you want to use just the `space` key in your keyboard you can set _minibuffer-local-completion-map_ configuration in your _.emacs_ file as below: 


```elisp
(defun my/markdown-mode-hook ()
  (define-key minibuffer-local-completion-map (kbd "SPC") 'self-insert-command))
  
```



Now you can directly digit   text links with spaces inside the minibuffer.

Thank you to the  jrblevin/markdown-mode Team for the solution.

Thank you for your attention.
