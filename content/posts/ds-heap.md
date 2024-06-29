+++
draft = true
date = 2024-06-09
title = "Heap Data Structure"
description = ""
slug = "heap-data-structure"
authors = ["Diogo Pessoa"]
tags = ["data-structures", "heap"]
categories = ["Data Structures"]

+++

{{< toc >}}

## Summary

A heap is a binary tree that satisfies the heap property.

The heap property is that the parent node is either greater than or less than its
children.

If the parent is greater than its children, it is a max heap.
If the parent is less than its children, it is a min heap.

making it a complete binary tree, which means that all levels of the tree are fully
filled except possibly for the last level, which is filled from left to right.

There's no guarantee of order in a heap (compared to a binary search tree). Making it
less efficient for searching.

- [Conventions](https://diogo-pessoa.github.io/posts/conventions)
- [My implementation of Heaps](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/dataStructures/heap)

## Operations

### Insertion

Insertion is done by adding the new element to the end of the heap and then "bubbling
up" the element to its correct position.

When inserting an element into a heap, the primary goal is to maintain the heap
property (max-heap or min-heap). Here's a brief overview of how it works:

* Insert the element: Place the new element at the end of the heap (bottom of the tree).
* Heapify-Up (or Bubble-Up): Compare the inserted element with its parent node.

### Deletion

Deletion is done by removing the root element and then "bubbling down" the new root to
its correct position.

When deleting an element from a heap, the primary goal is to maintain the heap property.


### Big O table for Heap operations

| Operation | Time Complexity |
|-----------|-----------------|
| Insertion | O(log n)        |
| Deletion  | O(log n)        |
| Peek      | O(1)            |
| Search    | O(n)            |
| bubble-up | O(log n)        |
| sink-down | O(log n)        |
