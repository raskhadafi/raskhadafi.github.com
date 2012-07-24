---
layout: post
category : ruby-on-rails
tags : [rails, activerecord]
---
{% include JB/setup %}

# Use of update_attributes in nested models

Since a few versions of rails the method `update_attributes` updates only the attributes which are definied with `attributes_accessible`. This mechanisem can be bypassed with setting the option `without_protection`.

The method `attributes_accessible` can be extended with the option `as` and the method `update_attributes` can also use the `as` option. That can be use to only pass the params to the nested model. In the nested model the `attributes_accessible` must also have the same `as` option.

## Small example

### Problem

I want just update the address which is nested in the person form.

### Solution

The classes:

    class Person
      attribute_accessible :street_attributes, as: :address
    end

    class Address
      attr_accessible :street, :city, as: :address
    end

In the controller:

    @person.update_attributes(params[:person], as: :address)
