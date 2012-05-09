---
layout: post
category : homebrew
tags : [imagemagick, ghostscript]
---
{% include JB/setup %}

# Ghostscript broken after imagemagick installation

## The problem

I got first ghostscript installed and then imagemagick.
Which broke my ghostscript installation.
As I tried to start ghostscript I got following error message:

    dyld: Library not loaded: /usr/local/lib/libtiff.3.dylib
      Referenced from: /usr/local/bin/gs
      Reason: image not found

## The fix

So I had to uninstall ghostscript and imagemagick to fix the problem with following lines:

    brew remove little-cms --force
    brew remove libtiff --force
    brew remove libjpeg --force
    brew remove ghostscript
    brew remove imagemagick
    brew install ghostscript
    brew install imagemagick