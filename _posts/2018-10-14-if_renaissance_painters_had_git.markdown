---
layout: post
title:      "If Renaissance Painters Had Git"
date:       2018-10-15 01:44:57 +0000
permalink:  if_renaissance_painters_had_git
---


The concept of git can be hard to understand. I happen to be married to a highly trained artist, I've used this type of thinking to relate other things, so here goes.
Many of the great works of art were only partially done by the 'great masters' who are credited with them. Most times, the understudies in their studios did much of the work, at least the more basic work. When it came to completing the paintings, the tiny minutae, and obviously the overall design, that's where the master stepped in.
This type of collaboration is very similar to what we see in software, but sometimes at a much much larger scale.
Imagine one of the masters have been commisioned to complete a massive 10 foot tall painting. There are 8 artists assisting with the work. Even with such a large work, they'd all be bumping into each other if they all worked on it concurrently. Imagine part of the painting will feature two children hugging...one artist is responsible for painting each child. There will be details that overlap, and if there's no system in place, the painters might actually work against each other. It'd be pretty slow for them to take turns.
What if we had a way fohem to both work at the same time, but in seperate spaces. In git we would call these workspaces *branches*. Both artists could work on their part of the painting while the other one worked on even the same part of the painting. 
Along the way, they'd use what in git-land are known as *commits*. If you commit something, it's sort of like saving a word document, or your spot in Zelda. The fun part of a commit, is it saves the whole state of your work. If you make a commit on your branch of the painting, and later on one of those other artists spills some of that local wine, you can jump back to the earlier commit and bam, no more spill.
So the two artists are working along, and they both end up commiting that they're done with their assigned chunk of the painting. What would then happen is known as a merge. Both artists have their branches, and the *master* branch is the overall final work. When they merge their works into master, there can be conflicts. If one artist changed the eye color of one of the children, you'd have a conflict. The artists would need to sort those out, but anywhere the branch can just be pasted over the master would merge in just fine.
Imagine how many more great works we'd have right now if git were available to DaVinci.
