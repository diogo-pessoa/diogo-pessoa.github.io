+++
draft = true
date = 2024-06-07
title = "Hash Tables in python"
description = ""
slug = "hash-tables-in-python"
authors = ["Diogo Pessoa"]
tags = ["python", "data-structures", "hash-tables", "coding"]
+++

{{< toc >}}

## Conventions used in my notes

- [Conventions]({{< ref "posts/conventions-used-in-notes" >}} "conventions-used")

## Hash Tables

A hash table is a data structure that stores key-value pairs. It uses a hash function to
compute an index into an array of buckets or slots, from which the desired value can be
found.

### collisions

A collision occurs when two keys hash to the same index.

#### resolving collisions

1. **Linear Probing**: When a collision occurs, the algorithm searches for the next open slot.
2. **Chaining**: Each slot in the hash table stores a linked list of key-value pairs.
2. **Open Addressing**: When a collision occurs, the algorithm searches for the next open slot.
3. **Robin Hood hashing**: When a collision occurs, the algorithm compares the distance from the original slot to the current slot. If the current slot is closer to the original slot than the current key, the algorithm swaps the keys.
4. **Cuckoo hashing**: When a collision occurs, the algorithm swaps the keys between the two slots.


##### Linear Probing




### Hash functions

### Big O table

| Operation | time complexity | space complexity |
|-----------|-----------------|------------------|
| lookup    | O(1)            | O(n)             |
| insert    | O(1)            | O(n)             |
| delete    | O(1)            | O(n)             |



