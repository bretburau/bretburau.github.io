---
layout: post
title:      "CLI Gem Project"
date:       2017-11-01 12:08:33 +0000
permalink:  cli_gem_project
---


I just finished writing my CLI gem project. It was very challenging from beginning to end, but I'm happy it's working.

The most difficult part I think is getting going with a blank page. Even though using bundler makes it easier to get set up initially, there's still a lot of project structure and spec files that I hadn't dealt with before. I didn't want to start writing code and having things working only to find out that something was set up incorrectly. Eventually though, I just went forward with building out the interface before actually scraping any websites.

The tough thing about putting together the command line was getting all the objects organized. As I said I didn't have any scraping set up yet, which makes easy to second guess. I didn't know exactly how the information was going to be coming down, so it was difficult to picture exactly how to work with it. If I'd had scraping set up first, though, I think I would've been tweaking and retweaking the scraping process over and over to suit the structure of my objects and methods, so it made sense to just have the CLI functioning first. Ultimatly no matter which way it comes down the data can be manipulated however I want, its just a case of deciding how I wanted to work.

The biggest challenge for me as far as actualy scraping goes was avoiding redundancy. I was gathering articles from several different websites. The methods I wrote for each site are very similar, but due to the nature of scraping and the reverse-engineering type nature I feel I couldn't really do much better. Scraping is challenging, and I spent plenty of time in my console trying to find just the right specificity as far as CSS selectors go. I could see how this would be very difficult on a larger scale, or involving more than a handful of websites. The selectors involved and the amount of possible regex could get unmanagble very quickly.

I also had a hard time getting the gem to actually build. The gemspec file, while technically written in Ruby is tougher to read, and I didn't want to play around too much...I'd rather avoid breaking something I really don't understand yet. Eventually though I did get it to encapsulate into a gem and pushed it up to RubyGems.

On to the next task!
