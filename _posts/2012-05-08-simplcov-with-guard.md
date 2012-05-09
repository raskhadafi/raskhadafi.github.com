---
layout: post
category : ruby-on-rails
tags : [testunit, simplecov, guard]
---
{% include JB/setup %}

# Simplecov & test::unit with guard in a rails project

After initializing guard I had the issue that `rake test` and `guard` created
two different coverage quotes. The rake task told me 100% and guard 78%.
To solve the problem just add to every unit test file:

    SimpleCov.command_name 'test:units'
