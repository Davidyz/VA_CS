Heap
====

A data structure that organises data in an essentially complete rooted tree.

The **height** of a tree is the longest simple path from the root to a leave.

For a binary tree:
  _h = floor(lg n)_

A heap can be implemented by an array, where a parent node is denoted by _A[i]_ and its child nodes are _A[2i]_ and _A[2i + 1]_. Hence, the parent node of a node, _A[i]_, is _A[floor(i / 2)]_.

The number of leaves of a binary heap with _n_ nodes is _floor((n + 1) / 2)_, and their indices rande fron _ceiling((n + 1) / 2)_ to _n_.

# Running Time of Max-Heapify():
O(log n) since the maximum number of swap required is _floor(log n)_.

# Running time of Make-Max-Heap():
## Loose bound:
_O(n)_ calls to Max-Heapify(), so it is _O(nlogn)_

## Tight bound:
The number of nodes at height of h is upper bounded by n/(2^h) and lower bounded by logn.
With reference to the summation of arithmetico-geometric sequence, _T(n)_ ∈ 2cn

# Proof of Correctness:
Can be associated with induction, but we want the algorithm to stop (terminate) at the desired step.

## Loop Invariant => Claim:
Each node is the root of a max-heap.

## Initialisation => Base Case:
Prove that the claim is correct before the algorithm is run.

## Maintaintence => Inductive Step:
If the claim was true at i-th iteration, it is true at (i-1)-th iteration.

## Termination:
At the end, we got the result we want. In particular, when i = 0, i.e. all the nodes up to the very root of the heap have been maxified.

# Implementations of Heap:
It offers a good compromise between insertion and extraction. With a heap, both operations can be done in _O(logn)_, more efficient compared to _O(1)_ and _O(n)_.

Examples include:
  * Inserting a new element, _O(logn)_;
  * Finding the maximum element, _O(1)_;
  * Removing the maximum element, _O(logn)_;
  * Modifying the value of one of the keys, _O(log)_.
