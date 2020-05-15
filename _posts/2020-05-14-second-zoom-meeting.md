---
layout: post
title: "MATH 4391: Introducing 'Large Sparse Random Matrices of Network Models' "
---

![Introduction slide](/assets/intro.png)
* "sparse": lots of zeros
* "symmetric": (row, col) contains the same value as (col, row)
* "symmetric matrix": zero diagonal
* "random": some values are non-zero, some are zero
* "adjacency": graphs that represent networks
* "stochastic": the simulation uses on randomly generated numbers


![Network settings slide](/assets/network_settings.png)
* Two overlapping networks: First, generate the children's network then the parent network.

Children's network:
    * All children begin as susceptible (S) except for the 10 infected children (I).
    * Probability equation: A household with more children increases the likelyhood of a connection between nodes.
    * Random number (or rand) generated is between 0 and 1. (Uniform distribution)
    * If rand is less than the product of the probability equation, then a connection exists between nodes.
    * Rand is never less than 0.

Parent network:
    * Generate a rand for each parent node.
    * "If rand is less than Pret" means "if child node has a connection, then the parents retain their connection." (?)
    * If rand is greater than Padd, add a connection between the nodes. So, plus 1 to the matrix.