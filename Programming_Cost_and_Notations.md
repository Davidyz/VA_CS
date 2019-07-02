Programming Cost and Asymptotic Notations
=========================================

# Overview:
  *Asymptotic notation;
  *Graphs and Depth-First search algorithm;
  *Heaps and Queues;
  *Breath-First search algorithm.

## Measuring Running Time
  _Implimentation_:实现

### Big-O
  _An upper bound for an algorithm._

  This may also be used to characterise _the worst case running rime, the amount of space required, etc._ However, the big-O notation do not show how tight the bound is.
    Eg:
      `n=O(n²)`
      is true but obviously n is far below n².

### Big-Ω
  _A lower bound for an algorithm._

  This is, to some extent, the opposite notation to the big-O.

### Big-Θ
  **f(n) ∈ Θ(g(n))** if a\*g(n) <= f(n) <= b\*g(n) where a and b are constants.
  Or,
  **f(n) ∈ Ω(n)** and f(n) { O(n).

  _An upper bound and a lower bound that are linearly-relavent_

  If f(n) is in O(g(n)) and g(n) is in O(f(n)):
 `f(n) is in Θ(g(n))`

  log(n!)=Θ(nlog(n))
