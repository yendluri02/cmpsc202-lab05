# Lab 5: Introduction to Graphs

This lab introduces you to a new data structure: graphs. Graphs are a fundamental data structure in computer science and are used to model relationships between objects. In this lab, you will learn about the basic concepts of graphs, including vertices, edges, and various properties of graphs. 

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Complete all of the exercises below. Once you have completed the lab, push your changes to your forked repository.

Your name: ___________________________

## Introduction to Graphs

Graphs consist of a set of vertices (also called nodes) and a set of edges that connect pairs of vertices. Graphs are used to model relationships between objects in various domains. We can represent real-world problems using the language of graphs and solve them using graph algorithms. Common applications include finding the shortest driving route between cities, identifying fraud in financial transactions, or determining social media influencers. Graphs can represent diverse systems like communication networks, circuits, internet routing, social relationships, and protein interactions.

![Representation of a graph](images/representations.png)

## Core Definitions
- **Graph**: A graph $G=(V,E)$ consists of a set of nodes (vertices) $V$ and a set of edges (pairs of vertices) $E$.
- **Size**: A graph has $n=\vert{}V\vert{}$ vertices and $m=\vert{}E\vert{}$ edges.
- **Edges**: An edge $e=\{u,v\}$, usually written as $e=(u,v)$, is a set of vertices. The vertices $u$ and $v$ are neighbors, are adjacent, and are the endpoints of $e$. The edge $e$ is incident to $u$ and $v$.

### Exercise 1

For the following graph, list the vertices and edges. What is the size of the graph?

![ex1](images/ex1.png)

- **Vertices**: 0, 1, 2, 3, and 4

- **Edges**: (1, 0), (2, 0), (0, 3), and (3, 4)

- **Size**: 5 vertices and 4 edges (so the graph is fairly small, but it is connected enough to show the basic idea)


## Paths and Distances

- **Path**: A sequence $P=v_1, v_2, ..., v_k$ such that each consecutive pair $v_i$, $v_{i+1}$ are joined by an edge in $G$.
- **Simple Path**: A path where all vertices are distinct.
- **Cycle**: A path $c=v_1, v_2, ..., v_{k-1}, v_k$ where the first and last vertices are the same ($v_1=v_k$), the first $k-1$ vertices are distinct, and all edges are distinct.
- **Distance**: The distance from vertex $u$ to vertex $v$ is the minimum number of edges in a $u-v$ path.

### Exercise 2

The graph below shows the state of the internet in 1970s. Vertices represent computers and edges represent connections between them. Use this graph to answer the following questions.

![ex2](images/ex2.png)

1. Find a path from RAND to SRI. What is the distance between these two vertices?

- **Path**: RAND, STAN, SRI

- **Distance**: 2

2. Find a path from RAND to MIT. What is the distance between these two vertices?

- **Path**: RAND, SDC, MIT

- **Distance**: 2

3. Classify each of the following paths as simple, not simple, or a cycle. State your reasoning!

- **Path 1**: LINC, MIT, LINC, CASE
- **Classification**: Not simple, because a vertex is repeated before the path ends and it does not start and end at the same place

- **Path 2**: UCSB, SRI, STAN, UCLA, UCSB
- **Classification**: A cycle, because it begins and ends at the same vertex and the internal vertices are all distinct

- **Path 3**: UCSB, SRI, UTAH
- **Classification**: Simple, because all vertices appear only once and there are no repeated stops

## Connectivity and Trees

- **Connected Graph**: A graph with paths between every pair of vertices.
- **Tree**: A connected graph with no cycles.

### Exercise 3

Think through these with your partner(s) before answering the questions below. If you get stuck, try drawing a few graphs to help you visualize the problem.

1. A connected graph is defined as a graph with paths between every pair of vertices. If a graph with 10 vertices has exactly 8 edges, is it possible for the graph to be connected? Explain your reasoning based on the minimum number of edges required to link all vertices.

- **Answer**: No, a connected graph with 10 vertices needs at least 9 edges to keep all the vertices linked together. With only 8, the graph would be too sparse to connect every vertex, so it would not be connected.

2. A tree is a connected graph with no cycles. If you take an existing tree and add exactly one new edge between two non-adjacent vertices, what structural property is immediately violated?

- **Answer**: The tree would immediately gain a cycle, which violates the defining property that a tree has no cycles. It would still be connected, but it would no longer be a tree.