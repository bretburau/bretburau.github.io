---
layout: post
title:      "Data Structures: Stacks and Queues"
date:       2018-10-06 07:27:36 -0400
permalink:  data_structures_stacks_and_queues
---


###Stacks

A stack is a data structure made up of nodes, not completely unlike an array. The major defining characteristic is that it is LIFO(last in first out). We can only operate on one end of the stack, weather it be adding a new node or removing one. The name makes perfect sense; picture a pile (or stack) of books on a table. In order to reach the lower books, we must first remove the books on top, one by one.
The methods for stacks generally include `.pop()` to remove a node from the top, `.push(item)` to add a node to the top, `.peek()` returns the top node leaving it in place, and `.isEmpty()` returns true if the stack is empty. 
The main benefit of implimenting a stack is that adding nodes is very performant. O(1) in fact, since no matter how large the stack is, it always takes the same amount of time to add something to the top of it. With an array, adding a node can take longer, depending on the size of the array and where we're adding it. To insert in the middle of an array would require shifting other nodes around and possibly moving the entire array to a different spot in memory. The story is similar when removing elements. It still involves shifting the reamaining nodes to collapse over the newly-empty spot, which again depends on the size of the array. Looking up an element is simple in an array, as we just need to reference the index. In a stack, looking up and/or removing an element is dependant on it's size. We can't access a node until we remove all of the nodes above it, so the bigger the stack and the further down the stack, the longer it takes.

###Queues

A queue is another data structure. The big feature here is that they are LIFO(last in first out), that is, nodes can only be added on one end, and removed from the other. Picture a queue at at theme park...everybody goes in one end, follows the winding path, and comes out the other end. Queue's generally have similar methods available to stacks, but swap `.pop()` and `.push()` for `add(item)` to add a node at the head and `.remove()` which pulls one off the end and returns it. The difference is mostly just show...pop and push imply woking on the same end, whereas add and remove is two differing ends. Performance-wise, the pros and cons are similar to stacks, as well. Adding and removing nodes would be O(1), as the complexity doesn't change dependant on the size of the queue. Things slow down when trying to find and access a specefic node. To search through but keep the queue in tact, each node needs to be removed and added one by one until the desired data is found. For this reason it's not the best use case for a queue.
