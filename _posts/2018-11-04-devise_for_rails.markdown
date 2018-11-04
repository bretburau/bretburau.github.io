---
layout: post
title:      "Devise for Rails"
date:       2018-11-04 16:03:50 -0500
permalink:  devise_for_rails
---


Devise is an all-encompassing authorization gem for Rails. It's based off of the older Warden gem, and offers many options for securing your Rails application.

###Installation

Open your gemfile and add
```
gem 'devise'
```

Then run
```
bundle install
```

This will install the actual gem. Devise comes packaged with a bunch of generators, but an important one is the model installer.
```
rails generate devise:user
```
This will add a `User` model and add all the necessary code for securing it. Inside `user.rb`. You can change the name of the model if you need to, but 'user' works well here. We can configure the options for securing the model.
```
class User < ApplicationRecord
  # Include default devise modules. Others available are:
  # :confirmable, :lockable, :timeoutable, :trackable and :omniauthable
  devise :database_authenticatable, :registerable,
         :recoverable, :rememberable, :validatable
end
```
Is the default setup for the model. The options can all be defined after the keyword `devise` on line 4. 
