---
layout: post
title:      "Laravel Telescope"
date:       2018-12-30 02:53:51 +0000
permalink:  laravel_telescope
---


As developers, most of what we do is debugging. Say "programmer" and most people picture some super genius sitting alone in the basement under an exposed light bulb hacking into the pentagon. That couldn't really be any farther from the truth. For me, at least, it seems that all I do is iron out bugs in my code. Solving one bug just ends up leading me to three others. It keeps me out of trouble I guess!

In my recent journey into the php world, I've been learning a lot about Laravel. It's a cool framework, and at the surface feels like a somewhat modernized version of Ruby on Rails, even though it's a different language. Debugging is still there, clearly, but I've recently come across a very good tool to help: Telescope.

Telescope runs inside your local development environment. It's pretty easy to install...
```
composer require laravel/telescope
php artisan telescope:install
php artisan migrate
```
And you're up and running. 

To access Telescope's toolset is even easier, it's just served up along with your project. Just navigate to ```localhost/telescope```, where localhost is whatever IP your Laravel app is running. The Telescope dashboard is pretty self-explanitory, but there's a lot of power here, and some excellent places to track down bugs.

The home page is generally a list of requests the server has recieved. This is like a fleshed-out version of what your command-line server is spitting out. It gives you the endpoint that's been hit, the status returned, and how long it took to process. If you click the little eye, there's even more detail, any data sent up or down, headers, and any other pertinant information.

The "Exceptions" page can be very useful, too. It tracks any errors that your Laravel server has thrown and basically gives you all the information that was there at the time it happened. On a related subjuct is the "Dumps" page. It can be really usefule when debugging to just stick a line of code in to say "tell me what is happening right now". If you ```dd($variable)``` it'll dump it, but again, all your dumps are saved here. It can be helpful in seeing how your changes have affected the app.

There's a lot available in here, from seeing all of the actual SQL queries logged to records of any time your models are created/modified. Seeing anytime an email is setup and sent, and likewise with other notifications, e.g. texts or even toasts is pretty cool. Telescope is a very powerful tool, and it helps to keep my apps under control!

