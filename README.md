#Problem

We want to create a path between a list of songs using Kruskal's algorithm.  The transition between 2 songs will be weighted based on the best transition on the segment level between the 2 songs.

#Questions

When interpreting a song as a list of segments, how do you store the best transition between 2 songs, both with the segments to transition between and their weight?

How will implementing Kruskal's algorithm differ between Prim's algorithm?

#Resources

1. [Kruskal's Algorithm]
2. [Prim's Algorithm]

#Mini-abstract and relevance of [Kruskal's Algorithm]

Kruskal's algorithm works by connecting the 2 nodes in a map with the shortest distance between them.  This process is repeated until all the nodes are connected.  If a connection forms a cycle before all the nodes are connected, this connection is discarded.

In terms of connecting music files at the segment level, the connection between 2 songs will be based on the best transition at the segment level between the 2 songs.  The runtime of this process is O(n*m) where n is the number of segments in the first song, and m is the number of segments in the second song.

To interpret the music files as a map with each node connected to all the other nodes, all the transitions between all the songs will need to be stored.  Each stored transition will need the 2 segments in question, and their weights. To prevent unnesessary recalculations, songs will not be backtracked.  Example: with songs a, b, and c, the transitions from a to b and a to c will be calculated, and then b to c will be calculated.  There will be no need to do b to a, c to a, or c to b since those will already be computed.

Lastly, since Kruskal's algorithm does not use a node as a seed, the transition with the highest weight (the last transition) will be used as the starting and ending song.  This is done to keep the total distance between all the transitions to its lowest possible, since removing the largest transition will have the greatest impact.

#Mini-abstract and relevance of [Prim's Algorithm]

Prim's algorith works by taking a seed node, and connects it to the cloest node.  The next node is connected to its closest node that isn't already in the cycle, and this is continued until all nodes are connected.

I have already implemented Prim's algorithm on the given problem.  The intent of this report will be to compare Kruskal's and Prim's algorithms for determining a cycle between songs.

[Kruskal's Algorithm]: https://www.cse.ust.hk/~dekai/271/notes/L08/L08.pdf
[Prim's Algorithm]: https://www.cse.ust.hk/~dekai/271/notes/L07/L07.pdf
