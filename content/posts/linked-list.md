+++
draft = true
date = 2024-06-05
title = "Linked Lists"
description = ""
slug = "linkedLists"
authors = ["Diogo Pessoa"]
tags = ["Data Structures", "python", ]
url = "linked-lists-in-python"
categories = ["Data Structures"]
+++

{{< toc >}}

# Linked Lists

## What is a Linked List?

A linked list is a data structure where each node contains data and a reference (or
link) to the next node in the sequence. There is usually a head node, which is the first
element, and a tail node, which is the last element.
In some variations, like doubly linked lists, each node also has a reference to the
previous node, will explore on separate note.

- [My basic implementation of a linked list in python](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/dataStructures/linkedlist)

## The Big O Notation of Linked Lists Operations

### Adding to tail

- Time complexity: O(1)
- Space complexity: O(1)
- The time complexity is O(1) because we can add a new node to the tail of the linked
  list
  in constant time, regardless of the size of the linked list.

### Delete the tail

- Time complexity: O(n)
- Space complexity: O(1)
- The time complexity is O(n) because we need to traverse the entire linked list to find
  the second-to-last node, which is the new tail node.

### Adding to head

- Time complexity: O(1)
- Space complexity: O(1)
- The time complexity is O(1) because we can add a new node to the head of the linked
  list
  in constant time, regardless of the size of the linked list.

### Delete the head

- Time complexity: O(1)
- Space complexity: O(1)
- The time complexity is O(1) because we can delete the head node in constant time,
  regardless of the size of the linked list.

### Adding to middle

- Time complexity: O(n)
- Space complexity: O(1)
- The time complexity is O(n) because we need to traverse the linked list to find the
  node at the specified index before adding a new node after it.

### Delete from middle

- Time complexity: O(n)
- Space complexity: O(1)
- The time complexity is O(n) because we need to traverse the linked list to find the
  node at the specified index before deleting it.

### search element

- Time complexity: O(n)
- Space complexity: O(1)
- The time complexity is O(n) because we need to traverse the linked list to find the
  node with the specified value.

## Table of Big O Notation of Linked Lists Operations

| Operation          | Time Complexity | Space Complexity |
|--------------------|-----------------|------------------|
| Add to tail        | O(1)            | O(1)             |
| Delete the tail    | `O(n)`          | O(1)             |
| Add to head        | O(1)            | O(1)             |
| Delete the head    | O(1)            | O(1)             |
| Add to middle      | `O(n)`          | O(1)             |
| Delete from middle | `O(n)`          | O(1)             |
| Search element     | `O(n)`          | O(1)             |
