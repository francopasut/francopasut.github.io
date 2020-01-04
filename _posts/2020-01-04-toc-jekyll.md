---
toc: true
toc_sticky: true
toc_label: "My Table of Contents"
toc_icon: "cog"
excerpt: "About Table Of Contents (TOC) from Org-Mode to Jekyll Minimal Mistakes theme"
title: "Table Of Contents (TOC), from Org-Mode to Jekyll"
last_modified_at: 2020-01-04
categories:
  - Blog
tags:
  - GitHub
  - Jekyll
  - Emacs
  - Org-Mode
  - Minimal-Mistakes
---
## What's a Table Of Contents and why using it?

A Table Of Contents ("TOC") is an index of a document's content.

In the _world wide web_ environment it's usually a list of chapter and sub-chapter headings in the online articles.


Why using it? Obviously:  the _TOC_ can give you an overview of the documents' structure, so you can quickly jump where you're interested, without spending time reading the rest of the document.

As a [not-developer writer in GitHub](https://francopasut.github.io/blog/github-non-programmers/ "Please read my article") of some posts I'd like a simple and fast system to get the _TOC_ of my articles.

## Emacs Org-Mode and the autogenerated TOC

An excellent resource to generate a TOC is offered by Emacs with its extraordinary [Org-Mode](https://orgmode.org/): if you write structured documents in _Org-Mode_ you can easely export it in Markdown (`C-c C-c m m`, but you must previously customize Emacs with the command `org-export-backends` and enable the markdown backend) or HTML (`C-c C-e h h`) and getting an autogenerated TOC based on the document's headers fully functional in any environment.

![_config.yml]({{ site.baseurl }}/assets/images/toc-03.png)

By the way: try Org-Mode and you will enjoy it!


However the limit of this system is that the TOC generated by Org-Mode always appears at the beginning of the article and is not, therefore, dynamically moved while reading it in your browser.


## Minimal-Mistakes over Jekyll provides an automatic TOC

When I discovered the theme [Mimimal-Mistakes](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/) for Jekyll I found a very quick way to get the TOC of articles published in GitHub.

For automatic TOC use the following configuration in the Front Matter (the _icon_ is optional):


    ---
	toc: true
    toc_label: "My Table of Contents"
    toc_icon: "cog"
	---
You can also use the /sticky/ version by adding `toc_sticky: true` in the Front Matter:

    ---
    toc: true
    toc_sticky: true
	toc_label: "My Table of Contents"
    ---
	
![_config.yml]({{ site.baseurl }}/assets/images/toc-01.png)
	
The index will be at the top of the page on small format devices, such as smartphones, and on the left persistent on large display devices, such as tablets (in landscape mode) and computer monitors.

Scrolling the page causes the current zone to be highlighted in the TOC.

![_config.yml]({{ site.baseurl }}/assets/images/toc-02.png)

Thank you for you attention.