---
layout: post
title:      "Wordpress Github Sync"
date:       2018-12-02 12:55:43 +0000
permalink:  wordpress_github_sync
---


As we’ve discussed before, WordPress is a very powerful tool for building websites, and its roots come in blogging. Say we have a blog already up and running and we want to import all the posts into our WordPress site. Or imagine we’d like a way for more than one person to collaborate on posts, or even edit and update them, without needing to access the WordPress backend. Another possibility that works would be having one source of content that ends up on two different blogs, for whatever reason. Here we’ll explore doing that with WordPress Github Sync.
WordPress Github Sync is a plugin for WordPress that lets you tie a Github repository to your blog. You can commit and push markdown files to your repo, and your WordPress setup will automatically import them. Markdown is a type of formatting language. It makes it easy to add formatting and basic layout inside of a plain text document. It’s popular among some bloggers since its unobtrusive to the writing process. Instead of stopping to click a bold button, for instance, you can just wrap the text with two asterisks on each end. Any markdown interpreter will know to display the enclosed text as bold.

Installing this plugin is as simple as most WordPress addons. Simply go to the “Add plugin” area on your WordPress backend and search for “Github Wordpress Sync.” It should come up, click install, and activate it when it’s finished. To make life a little easier when working with markdown, search for, install and activate the plugin WP-Markdown, as well. 

On your Github site, create a personal oauth token with the scope of public_repo. Inside the repository go to your settings, and create a webhook. The payload URL field should be the URL of your blog. Content type should be “application/JSON.” Back at your WordPress setup, go to the settings for Github WordPress Sync. Enter the repository formatted like: your_username/repository_name, like in the Github URL. Copy in the Oauth token you created at Github, and also the Webhook Secret you created at your repo. 

You should be all set, and after saving your settings, click “Import from Github.” Viola! Your markdown posts are all imported into your WordPress site, no copy/pasting! They will be saved as drafts, and need to be published, but they’re all there!
