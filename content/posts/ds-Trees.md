+++
draft = false
date = 2024-06-06
title = "Binary Search Tree in Python"
description = ""
slug = "ds-trees"
authors = ["Diogo Pessoa"]
tags = ["Data Structures", "Trees", "python", "interview-prep", "Binary Search Tree"]
categories = ["coding", "notes", "interview-prep", "data-structures"]
url = "ds-tree-in-python"
+++

{{< toc >}}

## Summary

A tree is a data structure that consists of nodes connected by edges. The top node is
called the root, and the nodes below the root are called children. Each node can have
zero or more children. The nodes that have the same parent are called siblings. The node
at the bottom of the tree is called a leaf node.

## Types of Trees

### Binary Trees

A binary tree is a tree where each node has at most two children.

### Full Trees

A full tree is a tree where each node has either zero or two children.

### Perfect Trees

A perfect tree is a tree where all the leaf nodes are at the same level.

### Complete Trees

A complete tree is a tree where all the levels are completely filled except possibly for
the last level, which is filled from left to right.

### Binary Search Trees

A binary search tree is a binary tree where the `left child` is less than the parent
node. The `right child` is greater than the parent node.

* If a new node is less than the parent node, it is added to the left (all the way back
  to the root).

* `Premise: left < parent < right`: If you get any node in the tree, all the nodes in
  the left subtree are less than the parent node, and all the nodes in the right subtree
  are greater than the parent node.

#### Code Implementation

* [coding-exercises DS/BinarySearchTree](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/dataStructures/tree/BinarySearchTree.py)

### Tree Nodes types

#### Parent Node

The parent node is the node that has children.

#### Child Node

The child node is the node that has a parent.

#### Leaf Node

The leaf node is the node that has no children.


### Big O Notation of Trees Operations

#### Table by tree type

| Operation | Binary Tree | Full Tree | Perfect Tree | Complete Tree | Binary Search Tree |
|-----------|-------------|-----------|--------------|---------------|--------------------|
| Search    | O(n)        | O(n)      | O(log n)     | O(log n)      | O(log n)           |
| Insert    | O(n)        | O(n)      | O(log n)     | O(1)          | O(log n)           |
| Delete    | O(n)        | O(n)      | O(log n)     | O(1)          | O(log n)           |

