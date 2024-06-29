+++
draft = true
date = 2024-06-09
title = "Graphs"
description = ""
slug = "graphs-in-python"
authors = ["Diogo Pessoa"]
tags = ["graphs", "data-structures"]
categories = ["Data Structures"]
+++

{{< toc >}}

## Summary

Graphs, consists of a finite set of vertices and a collection
of edges that connect pairs of vertices. Graphs are used to model relationships between
objects.

- A Vertex can connect to another (or more) Vertex through an Edge.
- A Graph can be directed or undirected.
- A Graph can be weighted or unweighted.
    - A weight can be useful to calculate the shortest path between two vertices.
- Bidirectional graphs are graphs where the edges are bidirectional.
- A Tree is a form of a graph where there is only one path between two vertices.
- A linkedList is a form of a graph where each vertex has only one edge to another
  vertex.
- Adjacency matrix is a way to represent a graph in a matrix form.
- Adjacency list is a way to represent a graph in a list form.

- [Conventions](https://diogo-pessoa.github.io/posts/conventions)
- [My implementation of Graphs](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/dataStructures/graph)

### Graph Representation

#### Adjacency Matrix

An adjacency matrix is a way to represent a graph in a matrix form. The matrix is a 2D
array with size V x V where V is the number of vertices in the graph. Let the 2D array
be adj[][], a slot adj[i][j] = 1 indicates that there is an edge from vertex i to vertex
j. Adjacency matrix for undirected graph is always symmetric. Adjacency Matrix is also
used to represent weighted graphs. If adj[i][j] = w, then there is an edge from vertex i
to vertex j with weight w.

Where V is the number of vertices in the graph and E is the number of edges in the
graph.

weight = 1 if the graph is unweighted

- If the graph is weighted, the weight of the edge is stored in the matrix.
- Symmetry in Adjacency Matrix: If the graph is undirected, the adjacency matrix is
  symmetric. If the graph is directed, the adjacency matrix is not symmetric.

- [Implementation](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/dataStructures/graph/GraphAdMatrix.py)
### Adjacency List

An adjacency list is a collection of linked lists or array that lists all the adjacent
Each vertex has a list of its adjacent vertices stored.

- [Implementation](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/dataStructures/graph/GraphAdList.py)

## Big O of Graphs

| Operation     | Adjacency List | Adjacency Matrix | Comments |
|---------------|----------------|------------------|----------|
| Add Vertex    | O(1)           | `O(V^2)`         |          |
| Add Edge      | O(1)           | O(1)             |          |
| Remove Vertex | O(V+E)         | `O(V^2)`         |          |
| Remove Edge   | O(E)           | O(1)             |          |
| Query         | O(V+E)         | O(1)             |          |
| Storage       | O(V+E)         | O(V^2)           |          |



