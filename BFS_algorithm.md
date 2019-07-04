Breadth-First Search Algorithm
==============================
Finding out the route from one vertex on a graph to another that minimise the cost (_time, length, etc._)

**Input**: A graph, _G = (V, E)_, either directd or undirected, and a source point, _s_.  
**Output**: For v ∈ _V_, an integer d[v] and a back pointer π[v], such that d[v] = δ(_s_, v) and π[v] is the predecessor of v.

## Weight:
The cost of going through an edge.

_ω(E)_: a function that denotes the weight of the edge _E_.

The weight of a path, p = {v₀, v₁, v₂, .....} is: `∑ω(Ei)`.

### SHortest Path:
The path with smallest possible weitht, denoted by _δ(u, v)_.  
If a vertex, _v_ is unreachable from another vertex, _u_, _δ(u, v)_ = ∞.

## Queue:
A _first-in-first-out_ (FIFO) data structure with 3 basic operations:
  * Enqueue(_Q_, _x_);
  * Dequeue(_Q_);
  * IsEmpty(_Q_).

The queue in a BFS algorithm is used to store all discovered but not explored nodes, aka nodes whose adjacent nodes are not discovered. Thus, only after all reachable vertices have been reached will the queue be empty.  
Ref: CLRS 10.1

### Implementations:
Linked list with an extra END pointer to the tail of the list.  
All operations above are _O(1)_ since the head of the queue correspond to the head of the linked list.  

## Running Time Analysis:
_T(n)_ = _O(|V| + |E|)_  
_O(|V|)_ because every vertex will at most be examined once.  
_O(|E|)_ because an edge, _(u, v)_, will only be examed once u is dequeued, and the edge will only be examined once (in a directed graph) or twice (in an undirected graph).  

