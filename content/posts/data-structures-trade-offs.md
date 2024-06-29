+++
draft = true
date = 2024-06-09
title = "Data Structures Trade-offs"
description = ""
slug = "trade-offs-in-data-structures"
authors = ["Diogo Pessoa"]
tags = ["data-structures", "big-O", "algorithms"]
categories = ["Data Structures"]
+++


{{< toc >}}

## Summary

As I walk through different Data structures. I noticed each has a best fit to a specific
problem. Since everything has a trade-off. Let me try to cover a few here.



### specific trade-offs

* **Inserts Binary Tree Search** vs **Inserts in a Hash Table**

    - Binary Tree Search: O(log n) vs Hash Table: O(1)
    - Hash Table is faster for inserts.
    - There's an edge case:
        - Binary Search Trees are sorted which makes them better at searching for all
          values that fall within a range
* **Look-up** for values in Hash-tables are not `O(1)`, but `O(1 + k)` where `k` is the
  number of values that hash to the same index.

# big O notation table for different data structures and operations

| Data Structure | Access | Search | Insertion | Deletion | update | Comments |
|----------------|--------|--------|-----------|----------|--------|----------|
| Stack          | O(n)   | O(n)   | O(1)      | O(1)     | O(n)   |          |
| Queue          | O(n)   | O(n)   | O(1)      | O(1)     | O(n)   |          |
| Linked List    | O(n)   | O(n)   | O(1)      | O(1)     | O(1)   |          |
| double linked  | O(n)   | O(n)   | O(1)      | O(1)     | O(1)   |          |
| Hash Table     | N/A    | O(1)   | O(1)      | O(1)     | O(1)   |          |
| Heap           | O(n)   | O(n)   | O(log n)  | O(log n) | O(n)   |          |
| Graph          | O(n)   | O(n)   | O(1)      | O(1)     | O(1)   |          |
