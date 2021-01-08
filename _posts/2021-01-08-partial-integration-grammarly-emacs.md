---
permalink: /2021-01-08-partial-integration-grammarly-emacs
title: "A Partial Inegration of Grammarly in Emacs"
excerpt: "A very simple elisp function to copy a region and open a grammarly page"
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

## The Problem

I wanted to integrate grammarly into my day to day emacs life, so I can check notes, emails and papers directly from emacs. Comes out, there is no easy way to do this: there are no available APIs that can be called to pass text and get corrections. I have googled a bit and there are a few partial solutions (one that is OSX only) and others very interesting work arounds that makes the process a bit easier.

## My Solution

To brush up my elisp skills, that I do not use much since I can often copy and modify stuff I find on the web, I decided to implement a very simple and partial integration of grammarly.

Essentially, the function does two things:

+ Kills the region (as copy), so we can paste it into grammarly
+ Opens the grammarly webpage, so we can paste the text

It is quite simple, but it is effective. Let's see the function.

```elisp

(defun open-grammarly-with-kill ()
"A function to open a new grammarly document"
  (interactive)
  (progn  
       (copy-region-as-kill (region-beginning) (region-end))
       (browse-url "https://app.grammarly.com/docs/new")))
```

You might want to set this as a keybinding, I am currently using C-c C-g to do this.

```elisp
(global-set-key (kbd "C-c C-g") #'open-grammarly-with-kill)
```



