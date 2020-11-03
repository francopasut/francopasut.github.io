---
toc: true
toc_sticky: true
toc_label: "My Table of Contents"
toc_icon: "cog"
image:
  feature: /assets/images/vim-transparent.jpg
excerpt: "Add blank lines under text lines using Vim editor"
title: "Vim: two methods to append blank lines under multiple text lines"
last_modified_at: 2020-11-03
categories:
  - Editors
tags:
  - Vim
  - GVim
  - Regular Expressions
  - RegEx
---

## What are we talking about?

One of the most fascinating aspects of Vim is that you never end up learning new solutions and tricks

It's really amazing how you can always find new ones in Vim that makes writing work faster.

A few days ago I needed to separate some text lines with blank lines under each line.

This happens frequently in _LaTeX_ in wich an empty line determines the carriage return of the text.

My instinctive solution was to go to each line in Normal mode, type "O" ("o" uppercase) to activate the Insert mode and adding a line below, type Return, exit Insert mode, go down one line with "j" and start again into the new line, until the last line.

But it didn't seem to me a Vim-style _modus operandi_.

So I looked for some faster solutions on the net.

I found many interesting solutions. Here are two of my favorites.


## The Regular Expression solution

Regular expressions save a lot of time.

Here is a _one shot_ solution to my purpose:

``` vim
:s/$\/r/
```
What the hell does it mean?

Here is the action of each symbol:

- `:s` to enter the Command mode followed by the _substitution_ prefix
- `/$` to highlight the end of each line
- `\` to escape the next character
- `/r` to insert a carriage return
- `/` to close the regular expression

## The Global Command solution

The same result can be obtained with the Global Command using the following string:

```vim
:g/./normal o
```

Here is the action of each symbol:

- `:g` to enter the Command mode followed by the _global_ prefix
- `/./` to select every non-blank line
- `normal o` to add a blank line above every selected line

The last string is an example of a Normal command inside a Global command string.

That's unbelievable: _Vim Is Magic_!

Thank you for your attention and... **_"Discite Vim"_**
