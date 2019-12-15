---
title: "TeXLive full installation in Linux Manjaro via pamac-manager"
categories:
  - Writing
tags:
  - LaTeX
  - TeXLive
  - Linux
  - Manjaro
---



## TeXLive in Linux repositories

TeXLive is one of the most comprehensive distributions for the LaTeX language in the Linux world, as well as in other operating environments.

However not every Linux distributions offer an updated TeXLive installation inside their repositories.

For instance Linux MINT 19.1, offers (today 2019, 15 dec) only a 2017.20180305-1 release, dated 2017.11.29 and  DEBIAN 10 offers a 2018.20190227-2 release.

Manjaro, on the other hand, offers the 20190517–1 release in 
[AUR Repository](https://aur.archlinux.org/packages/texlive-full/).

Of course, in every Linux distribution you can install the original TeXLive distribution following [this tutorial of mine](https://francopasut-en.blogspot.com/2016/07/simple-and-fast-installing-of-texlive.html).

But the internal installation is faster, also for future updates.

Here is the step-by-step installation in Linux Manjaro through _pamac-manager_ with some additional steps to be completed after installation.

## TeXLive full installation in Linux Manjaro using _pamac-manager_

As the first step you must previously  check if in AUR Repository is available the _texlive-full_ installation.


If you found it, you have, now,  to check if there are  any partial TeXLive installations in your system and uninstall every TeXLive distribution other than “full”.

You’ll probably find _texlive-bin_ and _texlive-core_ already installed by default: delete them and go beyond.

You can, now, select and install _texlive-full_ from AUR repository as any other application.

But when the installation is finished, a few steps still need to be taken.

## The additional steps to complete the installation ##

As the first additional step, you have to add the _permanent path_ to the new installation. 

Usually you’ll find the new installation in a path like the following one: `/opt/texlive/2019/bin/x86_64-linux/`.

If you do not find it in that path you can search with the commands

``` 
$ sudo updatedb
$ locate texlive
```

Of course the specific name of the distribution varies depending on the version downloaded.

Then you must edit the hidden file  named `.profile` in the _root_ (note the point before the file name).

You can use the editor you prefer, such as, for example _Nano_ or _Vim_ with a simple string like the following one:

```
sudo vim ~/.profile
```

and add the following line at the bottom of the file>

```
export PATH="$PATH:/opt/texlive/2019/bin/x86_64-linux".
```

adjusting the string with  the actual distribution name.

To complete the  procedure, in `/usr/local/bin` add  the following symbolic links:

```
sudo ln -s /opt/texlive/2019/bin/x86_64-linux/latexmk
sudo ln -s /opt/texlive/2019/bin/x86_64-linux/bibtex
```

here too, adjusting the strings.

Now you can restart you system and enjoy your TeXLive full!
