---
layout: post
category : homebrew
tags : [imagemagick, osx, osx 10.6.8]
---

# Turn off the pipeline assets log

To remove these logs

    Started GET "/assets/application.js?body=1" for 127.0.0.1 at 2012-02-13 13:24:04 +0400
    Served asset /application.js - 304 Not Modified (8ms)

just add to your Gemfile

    gem 'quiet_assets', :group => :development


and execute

    bundle