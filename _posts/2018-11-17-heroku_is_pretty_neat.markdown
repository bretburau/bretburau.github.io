---
layout: post
title:      "Heroku is Pretty Neat"
date:       2018-11-17 12:18:21 +0000
permalink:  heroku_is_pretty_neat
---


There are a multitude of ways to get your websites up on the internet these days. In a previous post we touched on classic shared hosting, and it seems like everybody's trying to figure out how to replace it. There are several ways to deploy to the cloud and Heroku is a very popular one, especially for lower traffic/hobby apps. Though it can get expensive to scale, it's free to start out!
From Heroku's website:
"Heroku is a cloud platform based on a managed container system, with integrated data services and a powerful ecosystem, for deploying and running modern apps. The Heroku developer experience is an app-centric approach for software delivery, integrated with today’s most popular developer tools and workflows."
To translate from Silicon Valley English to American English, Heroku takes as much pain of cloud deployment out of the mix as possible, freeing up time to work, not manage cloud scripts. The container system they refer to reminds me somewhat of Docker, and how it bundles everything into a package to be deployed. Whle Docker makes it easy to deploy images to services like Zeit Now, and makes it simple to get everything running on a co-worker's computer, Heroku is specific to its service.
Using Heroku is a little similar to using a service like github. You make a repo for your app, which you probably already had, and push it up to Heroku. From there Heroku sets up and compiles anything you need, and runs your app. Pretty simple, lets take a look!

I'll assume you've installed Heroku's CLI from their website. You'll also need to create an account with Heroku, as well. Once that's done, log in via your terminal:
```
heroku login
```
And follow the prompts.

Navigate to the folder where your app lives, and if you don't already have a git repo set up, do so now.
```
git init
```
We then need to create the Heroku app. Its similar to running `git init` but specific to Heroku.
```
heroku create
```
The initiates your Heroku container, and creates a remote for you on their servers. It'll also spit out a random name/URL for your app, some of which are really funny. Now as long as all the ducks are in a row for the app, we can deploy.
```
git push heroku master
```
Again, really similar to how github works, except now it's deploying. You get a long log of what's going on while Heroku puts your project together, and with any luck, it'll be mounted and running in the cloud! All we need to do is run
```
heroku open
```
and it'll pop open a browser window and navigate to your newly uploaded app! Much simpler than trying to configure all of that on your own!
You can manage your deployments from your account dashboard on the Heroku website, and there's obviously more complexity going on here, but for now your app is up and running!

