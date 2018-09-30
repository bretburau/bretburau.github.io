---
layout: post
title:      "Graphs and Trees, DFS vs BFS"
date:       2018-09-30 15:01:07 +0000
permalink:  graphs_and_trees_dfs_vs_bfs
---


###Graphs
Graphs are a type of data structure. They consist of nodes and edges. A node is a point where you would store a piece of data, be that a number, somebody's name, or even an object. The edges are where nodes are connected to eachother.

The edges in a graph can either be directed or undirected. Imagine the difference between a two-way and a one-way street. Picture there are nodes 'A' and 'B'. In an undirected graph, you could traverse back and forth between them as needed. If the graph were directed, however, you could only from one to the other, e.g. from A to B and either stop or traverse to one of B's other neighboring nodes. 

If we add a 'C' node, we can make the graph *cyclic*. B can now point to C and we can have C point to A. We can now go A -> B -> C -> A... as many times as needed, hence the term cyclic.

Lets make a 'D' 'E' and 'F' cycle, too. We can have them point to eachother in the same fashion as above, D -> E -> F. Now we have two subgraphs, and everything from A through F is considered a 'disconnected graph'. They're all part of the same graph, even though there's two seperate pieces. If we add an edge from B to E, now the entire thing is thought of as a 'connected graph'. One graph can consist of many disconnected subgraphs or be one large connected graph.

###Trees
A *tree* is a type of graph. All trees contain a root node at the top. We think of any other nodes as being below the root node. These are all refered to as *children*. Children can have their own children and so on. A family tree is an excellent example of this. Great-grandfather has several children who are a row lower than him, his grandchildren are a row lower, and so on down. 

Imagine that people for whatever reason can only have two children. If we plot this scenario out we'd end up with what's known as a *binary search tree*. Every node is limited to having two children, though they don't have to have any. If we arrange it so that the left child is always smaller than the right child, it becomes a *binary search tree*. It is so named because this type of tree can be very efficient for searches, because you can eliminate half of the possibilities on each iteration...though that's a little outside of the scope of this post. 

###Breadth-first-search
For a given graph, there are several ways to iterate over the nodes. One is breadth first search, or BFS. Using our family example above, we could start with great-grandfather, and print out his name. We then go down to all his children, and print out all their names in order. Then, on to the great grandchildren, until we run out of relatives. The approach of going all the way down the width of the tree is how we got the term breadth-first.

###Depth-first-search
Again looking at our family tree we can go a different direction. There are several different forms of DFS, but we'll be looking at the *pre-order* type of search. This means we look at the nodes left child, then self, then right child. We start as always with our parent node, the great-grandfather. We then look to his youngest on the left. If this node has any children we go directly to them, until we run into a *leaf* node, that is, one without children. We then print out this child's name, then progress to their parent. This parent prints out their name(as they've already explored the left side children) then we progress down their right hand children in the same fashion. This proceed through all of the great-grandfather's left children, until he prints out his own name. The the same process starts on his right side. In this method, all branches in the tree are explored to their ends before progressing down the next branch. This why it's known as depth-first, we progress as deep as possible before moving on.
