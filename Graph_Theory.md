Graph Theory
============

A graph, G = (V, E) is a collection/set of nodes and arcs.
V is the set of nodes and E ∈ V * V.

# Nodes
  _Points where arcs meet._

## Degree/order of nodes:
  The number of arcs connected to nodes. Can be _even or odd_.

# Arcs
  _Segments (directed or undirected) that connect nodes._

# Ways to store a graph in computers:

## Matrix/Array:
  n * n array whose (i, j)-th entry is 1 (if (vi, vj) ∈ E) or 0 (otherwise).

    * Presence of an edge can be checked in constant time;
    * Data structure has size **O(|V|²)**;
    * For an undirected graph, the matrix is symmetric.

## Adjacency Lists:
  Consist of |V| linked lists, one per vertex. The list for vertex _u_ holds the name of vertices to whick _u_ has an outgoing edge.

    * Presence of anedge is not checkable in constant time;
    * Data structure has size **O(|V| + |E|)**;
    * For an undirected graph, _u_ is in _v_'s adjacency list iff _v_ is in _u_'s.

Think:
  Q:
    Which one, matrix or lists, would you use to represent the World Wide Web (there is an edge between two sites iff they have a physical link)?

  A:
    The number of sites that a site is **physically** linked to is limited, so lists.
