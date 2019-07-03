Depth-First Search Algorithm
============================

_Which parts of the graph are reachable from a given vertex?_
_Works for both directed and undirected graphs, but does not care about the time required to reach._

# Idea:
As soon as a vertex is discovered, explore from it and a colour is assigned to it:
  
  * White: not discovered yet;
  * Grey: discovered but not fully explored;
  * Black: finished.

## Note That:
For all u ∈ _V_: **1 ≤ d[u] ≤ f[u] ≤ 2|_V_|**

## For each node, 3 attributed are maintained (_for which OOP may be used to simplify the code_):
  * discovered time;
  * finished time;
  * predecessor node.
  
# Analysis of DFS Tunning Time:
  1. Colouring all vertex and calling DFS\_visit() take time Θ(|_V_|), excluding the time to execute DFS\_visit();
  2. DFS\_visit() is only called once ∀ _v_ ∈ _V_, since it will be called if and only if the vertex is white, and when it is called for a vertex, the vertex is immediately turned grey;
  3. when DFS\_visit() is run on on a vertex _v_ ∈ _V_, it takes time c₁|_Adj[v]_| ≤ _T(v)_ ≤ c₂|_Adj[v]_|, **excluding the recursive call in DFS\_visit()**.

Thus, T(n) ∈ Θ(|_V_|) + c₁(∑|_Adj[v]_) ∈ Θ(|_V_| + |_E_|).

# The DFS Forest:

## Tree:
  A tree is a graph that is:
  * Connected;
  * Undirected;
  * Acyclic (does not contain any cycle)

## Forest:
Multiple Trees that are not necessarily connected.

To define a DFS forest:
  
  * Define the set of edges : _E_ := {(π[u], u) : u ∈ _V_, π[u] != NIL} && G := (_V_, _E_);
  * The graph is a DFS forest;
  * _u_ is a **descendant** of _v_ only if it is so in the DFS forest, G, not just in the original graph, G (_dependent on the order of listing vertices_).

# Characterisations of descendancy in the DFS forest:

  1. Parenthesis Theorem:
    The exploration of a node cannot be finished until all of its descendants have been explored.
  2. White Path Theorem:
    Vertex v is a descendant of vertex u iff, at the time that the search discovered u, there exists a path from u to v consisting entirely of white vertices.

## Tree Edges:
Edges of the DFS forest. If (_u_, _v_) is a tree edge, _v_ is undiscovered when _u_ is discovered.

## Back Edges:
Leads from a node to one of its ancestors in the DFS tree. If (_u_, _v_) is a back edge, _v_ is grey when _u_ is discovered.

## Forward Edges:
Leads from a node _u_ to a non-child descendant.

## Cross Edges:
Leads neither to a descendant nor an ancestor. They can link vertices in the same tree or in different trees. If (_u_, _v_) is a cross edge, then _v_ is black when _u_ is discovered.

# Usages:

## Detection of cycles in linear time:
A directed graph has a cycle iff its DFS reveals a back edge.

# Topological Sort on Vertices:
Rule: _u_ comes before _v_ if the edge is (_u_, _v_).

## Procedures:
  1. Run DFS;
  2. Sort the vertices in decreasing order of finishing time.

## Claim:
In a directed acyclic graph, if (_u_, _v_) ∈ E, then f[u] > f[v].

Proof:
    Let (u, v) be an edge.
    When (u, v) is explored, u is grey.
    Consider the following cases:
      * v is white: v is undiscovered, and will be finished before u since v is a descendant of u => f[u] > f[v] (tree edge)
        
      * v is black: visit of v has been finished => f[u] > f[v];
      
      * v is grey: cannot happen, because it means the presence of a back edge.

# "Big Question": How does DFS related to Sudoku?"
To be answered...
