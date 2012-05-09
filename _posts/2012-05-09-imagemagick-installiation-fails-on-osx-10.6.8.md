---
layout: post
category : homebrew
tags : [imagemagick, osx, osx 10.6.8]
---

# Installation error

    ld: library not found for -lgvc
    collect2: ld returned 1 exit status

## The fix

With the command `brew install imagemagick` I couldn't install it.
So I had to modify the imagemagick formula so that it has the option `--with-gvc=no` for the configuration. I had to add it on the line 115.

To open the imagemagick formula use `brew formula imagemagick`.