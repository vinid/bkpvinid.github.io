---
permalink: /2020-12-31-emacs-org-mode-motivated
title: "Emacs and Org-mode helped feel me Motivated Again"
excerpt: "Recently, getting my hands on emacs and org-mode again helped me to get back to where it all started"
author_profile: true


defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true
      share: true
      related: true
---

## Old Me Nerdy Me

I remember the first time I installed Ubuntu 14 years ago. I felt like I true hacker. I remember the first time I implemented a (naive) solution for the [Eight Queens Problem](https://en.wikipedia.org/wiki/Eight_queens_puzzle). I remember the first time I installed Arch Linux (and also the first time I blew up the entire system by installing the wrong package in the wrong place) and Gentoo. I remember trying to configure everything from the command line and writing scripts to activate my wifi. I remember having fun writing the first programs with Haskell and with LISP.

All these moments felt in a nerdy way that brought a lot of joy and satisfaction to me. All this working towards a solution and custom configuring felt great. Eventually, I also remember switching back to a more standard Ubuntu because I had to get a distro that was quick to configure as I needed to to get a few things done and I could not spend any more time dealing with configurations.

This system stayed up for years and walked me through all the Master's and PhD work. A few months ago, I realized that my laptop and in general programming had become more a means towards an end than what it originally was: a fun thing.

Don't get me wrong, I love doing research and I love python programming. However, programming in this context is often the medium to build something that has to be prototyped,  tested, and then written in a paper.

With this decrease in love for programming and with a general lockdown situation of the last months, I realized that my motivation wasn't at the top and while I kept working relentlessly I felt more tired than ever. It was difficult to keep track of everything I was doing and everything I was running.

## Bring in the Emacs

I do not remember exactly why, but I suddently decided to install Emacs. If you do not know Emacs, it is this 40 years old weird text editor that I left it for VIM[^1] almost 9 years ago. I do not even remember why I left it, but maybe it was because Emacs is a difficult text editor to deal with. However, Emacs is much more than a simple text editor (the joke you usually hear is that "VIM is a text editor and Emacs has a text editor"). 

Emacs allows you to set up your own configuration for essentially everything. If something is missing, you can write the code for it. Emacs gives you extreme text edition capabilities that other editor do not give you by default and you can integrate it with a lot of stuff. There are many cool packages out there (I will talk about org mode in a momeny) and I could make tons of examples, but one that might stick is that you can even run [Spotify](https://github.com/danielfm/spotify.el) from Emacs. 

The small price to pay is a learning curve at the start, but it is totally worth it. While the keybindings might scare someone at first, I have luckly swapped CTRL and CAPS Lock years, so going all the way down with the CTRL based keybindings wasn't a problem. I also believe that what got me on the right track was the very recent series of tutorials by [David Wilson](https://www.youtube.com/watch?v=74zOY-vgkyw&list=PLEoMzSkcN8oPH1au7H6B7bBJ4ZO7BXjSZ).

All the configuring made me fell like I felt the first time I installed Ubuntu. The same feeling of nerdy exploration that made me join the University for a Computer Science degree. Emacs makes me happy to open my laptop just to tweak a few things and weirdly, it keeps me motivated.

On the more productivity related side, I am using the amazing [org mode](https://orgmode.org/) to keep track of my schedule and the notes of the courses I am following. By pressing a few keys I can see the calendar and open the related note file. Org mode is making me much more productive, I can follow the progress of different projects without losing track. For most things, I do not even need to open firefox anymore, that was and still is the main soruce of my general procrastination and distraction.

I was so satisfied by this whole emacs experience that I eventually decided to install the emacs desktop manager EXWM (getting rid of GNOME). This allows me to have emacs keybindings anywhere on my OS. For example, now I can use C-n and C-p to navigate all the pages.

I am very happy with this new set up and I plan to extend my configuration to support me even better :).

[^1] Vim is another very famous text editor.