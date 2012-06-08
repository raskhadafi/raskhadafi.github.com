---
layout: post
category : rvm
tags : [rvm, gem]
---

To run a gem under RVM which should only be enabled in one ruby version and to prevent gem conflicts, install your gem into a dedicated gemset and create wrapper scripts:

Here is the example from [mailcatcher](http://mailcatcher.me/):

rvm default@mailcatcher --create gem install mailcatcher
rvm wrapper default@mailcatcher --no-prefix mailcatcher catchmail
