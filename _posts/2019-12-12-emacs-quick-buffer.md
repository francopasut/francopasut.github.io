---
toc: true
toc_sticky: true
toc_label: "My Table of Contents"
toc_icon: "cog"
excerpt: "How to use Emacs to take fast notes without creating new files"
title: "Emacs: taking quick notes without creating new files"
last_modified_at: 2019-12-31
categories:
  - Editors
tags:
  - Vim
  - Emacs
---


## The standard way to create new files in Emacs
When you need to create a new file in the Emacs environment you, normally, must press a key combination like the following one: 

```
C-x C-f
```
and give a path and a name to the file itself.

In _the world of Vim_, instead, there's no need to open a new file every time you have only to take  some quick notepad ideas: you can simply  press the _Insert Mode_ and begin to write inside the editor. 

In this case, Vim automatically creates a new _buffer_ and you can write without naming a new file.


Is there a corresponding function in _vanilla Emacs_?

Apparently there isn't: you cannot simply begin to write inside it.

But it's  possible to achieve a very similar result by taking advantage of the Emacs buffers properties.

## Emacs environment: files as buffers ##

In the Emacs environment, you create _new buffers_ everytime you create  new files.

You  can also create _new buffers_ **without creating new files**.


Simply type on the keyboard: 

```
C-x b
```

and write a random name.

This way, you will have created a buffer with an effortless name that will be deleted when you exit the program.

No residual will remain in the disc. Unless you decide to give a file name by pressing 

```
C-x C-s
```

## Why not use the _scratch_ buffer?

Among the buffers already available by default every time you run Emacs you will find one called _scratch_.

As it is specified inside this buffer:

>This buffer is for text that is not saved, and for Lisp evaluation.

So you can use this buffer either to take notes without saving them in a file, or to test something in _Elisp_ (but that's another story).

## Another way: Evil Mode ##

If you activate the Evil Normal Mode in Emacs you can use the `:enew` text command as if you were in _vanilla Vim_.

But you cannot simply begin to press `i` and start writing: you aren't really in Vim but in a _Vim environment_ very similar to the original but not equal.

Thank you for your attention.
