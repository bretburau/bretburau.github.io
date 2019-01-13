---
layout: post
title:      "Build pipelines can be silly"
date:       2019-01-13 19:00:36 +0000
permalink:  build_pipelines_can_be_silly
---


So I've continued my adventures in learn VueJS this week, and these things get more and more complex as I dive in. Before Flatiron I'd played around with using Webpack, before the `create-react-app` days (I think?), and it can be a scary beast. Its clearly a very powerful tool, but with that power comes a lot of complexity. The Vue CLI comes with some scaffolding, but the builds are always there.
I don't really know why, but Laravel and Vue seem to have become connected with each other. You can hook Vue up with any backend you'd want, but when you start a new Laravel project, Vue basically comes bundled in. Again, I don't know why, but whatever, it works. Well, once you get it all working, I guess. It's strange how difficult it can be to get a frontend framework up and running vs. the backends I've worked with. It may have something to do with the stability of the backend languages/frameworks, or the contant crazy change in the frontend. When I was starting to learn Laravel, its a pretty painless installation and I was able to fairly quickly get an MVC project up and running. The similarity to Rails and my experience there certainly helped me out quite a bit.
When I decided it was time to learn some Vue and get a more modern frontend, that's where I ran in to problems. The concepts and components weren't thattough for me, but I fell right in to configuration hell. There's a lot of tutorials and documentation out there, but it's hard to tell whats up to date, and what's not. I struggled for two days just trying to get a base compnent to render. It turns out I had something nested incorrectly, and the component wouldn't mount. I'm still not entiirely sure why it didn't work, but now it does.
I just today started working on adding authentication using JWT through Vue. The walkthrough I found is pretty recent, but there's a few places where it contradicts materials that I'd used for other parts of my app. That can really be challenging, especially when the whole language/concept/framework is new, so I don't even know how some things should look at all.
