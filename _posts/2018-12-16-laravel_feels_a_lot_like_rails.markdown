---
layout: post
title:      "Laravel feels a lot like Rails"
date:       2018-12-16 13:01:02 +0000
permalink:  laravel_feels_a_lot_like_rails
---

I recently began to learn PHP, since it seems to be pretty popular. It also seems worthwhile, given that it drives a pretty big chunk of the web, whether that’s through WordPress or just running on a server. Either way, it’s a popular language, and certainly worth knowing at least enough to be dangerous.
Laravel is a popular MVC framework for running PHP on the web. It is relatively new to the scene, especially when you think about how long PHP has been around.  Its first couple of versions came out in 2011, written by a guy named Taylor Otwell. It was in 2014 that it really became a contender, though. The framework was completely re-written to include the use of Composer. Composer is a command-line package manager for PHP. Similar to how JavaScript has npm to manage packages, Composer makes it much easier to collaborate, you can be more sure that code written on one machine will load up and run on other machines. The current version is 5.7, and there’s still features being added.
I’ve only worked in a couple languages and the only server-side framework I’ve really worked in is Ruby on Rails. I’m sure a lot of the web frameworks share a certain amount of similarities, but it really seems like Laravel’s developers were trying to emulate a lot of what Rails does. Aside from the obvious MVC-centric parts there’s a lot in common. Laravel has Eloquent for it’s ORM, Rails uses  ActiveRecord. Ruby has Rake tasks and ‘Rails generate’, Laravel has ‘php artisan’. Blade is to Laravel as erb is to Rails. Those are just a few similarities I’ve noticed so far. I haven’t worked that much in Laravel yet, but one difference I’ve noticed so far is the default inclusion of ‘.env’ variables. Laravel uses them out of the box whereas Rails needs a gem or some sort of addon. Small difference, but something I noticed.
One general PHP note: self vs this. I’ve had many typos between these two. Ruby uses self, where JavaScript uses this, and I’ve accidentally swapped them several times. PHP uses both keywords in different situations, so my confusion just continues…
All in all I really like Laravel so far. I feel like I’ve barely scratched the surface, and aside from getting used to the syntax, it seems like a very useful tool. 
