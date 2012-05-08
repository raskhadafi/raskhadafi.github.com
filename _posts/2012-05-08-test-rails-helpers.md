---
layout: post
category : rails
tags : [rails engine, mountable, test, testunit]
---
{% include JB/setup %}

# Howto test a rails helper in a mountable rails engine

    require 'test_helper'

    class DummyHelperTest < ActionView::TestCase
      test "should create a div" do
        render :text => div_tag('content')

        assert_select 'div' do
          assert_select 'content'
        end
      end
    end
