---
description: From Downey
---

# Dijkstra’s algorithm

Edsger W. Dijkstra was a Dutch computer scientist who invented an efficient shortest-path algorithm \(see [http://thinkcomplex.com/dijk](http://thinkcomplex.com/dijk)\). He also invented the semaphore, which is a data structure used to coordinate programs that communicate with each other \(see [http://thinkcomplex.com/sem](http://thinkcomplex.com/sem) and Downey, _The Little Book of Semaphores_\).

Dijkstra’s algorithm solves the “single source shortest path problem”, which means that it finds the minimum distance from a given “source” node to every other node in the graph \(or at least every connected node\).

I’ll present a simplified version of the algorithm that considers all edges the same length. The more general version works with any non-negative edge lengths.

The simplified version is similar to the breadth-first search in the previous section except that we replace the set called `seen` with a dictionary called `dist`, which maps from each node to its distance from the source:

```python
def shortest_path_dijkstra(G, source):
    dist = {source: 0}
    queue = deque([source])
    while queue:
        node = queue.popleft()
        new_dist = dist[node] + 1

        neighbors = set(G[node]).difference(dist)
        for n in neighbors:
            dist[n] = new_dist

        queue.extend(neighbors)
    return dist
```

Here’s how it works:

* Initially, `queue` contains a single element, `source`, and `dist` maps from `source` to distance 0 \(which is the distance from `source` to itself\).
* Each time through the loop, we use `popleft` to select the next node in the queue.
* Next we find all neighbors of `node` that are not already in `dist`.
* Since the distance from `source` to `node` is `dist[node]`, the distance to any of the undiscovered neighbors is `dist[node]+1`.
* For each neighbor, we add an entry to `dist`, then we add the neighbors to the queue.

This algorithm only works if we use BFS, not DFS. To see why, consider this:

1. The first time through the loop `node` is `source`, and `new_dist` is 1. So the neighbors of `source` get distance 1 and they go in the queue.
2. When we process the neighbors of `source`, all of _their_ neighbors get distance 2. We know that none of them can have distance 1, because if they did, we would have discovered them during the first iteration.
3. Similarly, when we process the nodes with distance 2, we give their neighbors distance 3. We know that none of them can have distance 1 or 2, because if they did, we would have discovered them during a previous iteration.

And so on. If you are familiar with proof by induction, you can see where this is going.

But this argument only works if we process all nodes with distance 1 before we start processing nodes with distance 2, and so on. And that’s exactly what BFS does.

In the exercises at the end of this chapter, you’ll write a version of Dijkstra’s algorithm using DFS, so you’ll have a chance to see what goes wrong.

### Exercise 1

_In a ring lattice, every node has the same number of neighbors. The number of neighbors is called the degree of the node, and a graph where all nodes have the same degree is called a regular graph._

_All ring lattices are regular, but not all regular graphs are ring lattices. In particular, if `k` is odd, we can’t construct a ring lattice, but we might be able to construct a regular graph._

_Write a function called `make_regular_graph` that takes `n` and `k` and returns a regular graph that contains `n` nodes, where every node has `k` neighbors. If it’s not possible to make a regular graph with the given values of `n` and `k`, the function should raise a `ValueError`._

### Exercise 2

_My implementation of `reachable_nodes_bfs` is efficient in the sense that it is in_ O\(n + m\)_, but it incurs a lot of overhead adding nodes to the queue and removing them. NetworkX provides a simple, fast implementation of BFS, available from the NetworkX repository on GitHub at_ [_http://thinkcomplex.com/connx_](http://thinkcomplex.com/connx)_._

_Here is a version I modified to return a set of nodes:_

| _def plain\_bfs\(G, start\): seen = set\(\) nextlevel = {start} while nextlevel: thislevel = nextlevel nextlevel = set\(\) for v in thislevel: if v not in seen: seen.add\(v\) nextlevel.update\(G\[v\]\) return seen_ |
| :--- |


_Compare this function to `reachable_nodes_bfs` and see which is faster. Then see if you can modify this function to implement a faster version of `shortest_path_dijkstra`._

### Exercise 3  

_The following implementation of BFS contains two performance errors. What are they? What is the actual order of growth for this algorithm?_

| _def bfs\(G, start\): visited = set\(\) queue = \[start\] while len\(queue\): curr\_node = queue.pop\(0\) \# Dequeue visited.add\(curr\_node\) \# Enqueue non-visited and non-enqueued children queue.extend\(c for c in G\[curr\_node\] if c not in visited and c not in queue\) return visited_ |
| :--- |


### Exercise 4

_In Section_ [_??_](http://greenteapress.com/complexity2/html/thinkcomplexity2004.html#dijkstra)_, I claimed that Dijkstra’s algorithm does not work unless it uses BFS. Write a version of `shortest_path_dijkstra` that uses DFS and test it on a few examples to see what goes wrong._

### Exercise 5  

_A natural question about the Watts and Strogatz paper is whether the small world phenomenon is specific to their generative model or whether other similar models yield the same qualitative result \(high clustering and low path lengths\)._

_To answer this question, choose a variation of the Watts and Strogatz model and repeat the experiment. There are two kinds of variation you might consider:_

* _Instead of starting with a regular graph, start with another graph with high clustering. For example, you could put nodes at random locations in a 2-D space and connect each node to its nearest_ k _neighbors._
* _Experiment with different kinds of rewiring._

_If a range of similar models yield similar behavior, we say that the results of the paper are robust._

### Exercise 6

_Dijkstra’s algorithm solves the “single source shortest path” problem, but to compute the characteristic path length of a graph, we actually want to solve the “all pairs shortest path” problem._

_Of course, one option is to run Dijkstra’s algorithm_ n _times, once for each starting node. And for some applications, that’s probably good enough. But there are are more efficient alternatives._

_Find an algorithm for the all-pairs shortest path problem and implement it. See_ [_http://thinkcomplex.com/short_](http://thinkcomplex.com/short)_._

