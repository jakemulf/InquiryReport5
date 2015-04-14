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




