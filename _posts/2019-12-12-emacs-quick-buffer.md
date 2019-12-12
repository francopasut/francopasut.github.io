---
title: "Emacs: taking quick notes without creating new files"
last_modified_at: 2019-08-08T17:20:02-05:00
categories:
  - Editors
tags:
  - Vim
  - Emacs
---


## The standard way to create new files in Emacs
When you need to create a new file in Emacs you, normally, must press a key combination like the following one: `C-x C-f` and give a path and a name to the file itself.

In _the world of Vim_ there's no need to open a new file everytime you have only to take  some quick notepad ideas: you can simply  press the _Insert Mode_ and begin to write inside the editor. 

In this case Vim automatically creates a new _buffer_ and you can write wihout naming a new file.


Is there a corresponding chance in _vanilla Emacs_?

Apparently there isn't: you cannot simply begin to write inside it.

But it's  possible to achieve a very similar result by taking advantage of the Emacs buffers properties.

## Vanilla Emacs: a buffer but not a file ##

In fact you can create, in Emacs, a _new buffer_ without creating a new file.

In this way you can start writing right away without worrying about where to save the file.

How can you get this result: `C-x b` and write a random name.

This way you will have created a buffer with an effortless name that will be deleted when you exit the program.

No residual will remain in the disc. Unless you decide to give a file name by pressing `C-x C-s`.

## The same result using Evil Mode ##

If you activate the Evil Normal Mode in Emacs you can use the `:enew` text command as if you were in _vanilla Vim_.

But you cannot simply begin to press `i` and start writing: you aren't really in Vim but in a _Vim environment_ very similar to the original but not equal.
