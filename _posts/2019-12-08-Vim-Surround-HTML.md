---
title: "Vim: surround a list of sentences with HTML tags"
last_modified_at: 2019-08-08T17:20:02-05:00
categories:
  - Blog
tags:
  - Vim
  - GVim
  - HTML
---



If you have a **list of words or sentences in Vim** and you need to add a couple of tags around each of them you cannot simply use the `V` (upper v) command to select all of them before using _vim.surround_ because in this case you get only one couple of tags
for all the list. 


You must use the *VISUAL BLOCK* command before the
selection of all the content. 

Let's go to see it step by step.  

You have a list with tree sentences:

```
This is a sentence.
This is another sentence.
And this is a third sentence.
```
If you  simply  select all these sentences in _visual mode_ and activate _vim.surround_ with `St`, you'll get the following wrong result:

```
<p>
This is a sentence.
This is another sentence.
And this is a third sentence.
</p>
```
That's not your proposal because you need to add **a couple of tags around each one sentence** not a single couple of tags for all sentences together.

Then you must use another strategy as like the following one:

1. `Ctrl-v` (or `Ctr-q` in Windows) to activate the visual selection, 
1. `2j` to select all the rows, 
1. `$` to select all the sentences till the end, 
1. `St` to surround all sentences with a tag, 
1. `<p>` (or any other tag) to specify the desired tag.

At the end you'll get:

```
</p><p>This is a sentence.</p>
<p>This is another sentence.</p>
<p>And this is a third sentence.</p>

```

That's the desired result.

Thank you for your attention.

Originally published at [My Tumblr Account](https://francopasut-en.blogspot.com/2018/08/vim-surround-list-of-sentences-with-tags.html)
