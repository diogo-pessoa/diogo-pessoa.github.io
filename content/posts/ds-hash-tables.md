+++
draft = false
date = 2024-06-07
title = "Hash Tables in python"
description = ""
slug = "hash-tables-in-python"
authors = ["Diogo Pessoa"]
tags = ["python", "data-structures", "hash-tables", ]
categories = ["Data Structures"]
+++

{{< toc >}}

## Conventions used in my notes


- [My basic implementation of a hash table in python](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/dataStructures/hash_table)

## Hash Tables

A hash table is a data structure that stores key-value pairs. It uses a hash function to
compute an index into an array of buckets or slots, from which the desired value can be
found.

### collisions

A collision occurs when two keys hash to the same index.

#### resolving collisions

##### separate chaining - Each slot in the hash table stores a linked list of key-value

pairs.

* big O: O(1) for lookup, insert, and delete operations.

#### Open Addressing -

When a collision occurs, the algorithm searches for the next open slot.

##### Linear Probing

The algorithm searches for the next open slot.

* big O: O(n) for lookup, insert, and delete operations.

##### Quadratic Probing

The algorithm searches for the next open slot by using a quadratic function.

* big O: O(n) for lookup, insert, and delete operations.

##### Double Hashing

The algorithm uses a second hash function to determine the next open slot.

* big O: O(n) for lookup, insert, and delete operations.

#### Using a prime number as the size of the hash table

There's a benefit to using a prime number as the size of the hash table.
It reduces collisions (increasing randomness) that occur when using a hash function.

Turns out somebody else was just as puzzled to read the statement above without a full
explanation. quickmathintuitions.org, Stefano Ottolenghi explains [1](#references). :
smile:

A few keys points from his explanation:

> _"I believe that it just has to do with the fact that computers work with in base 2.
Just think at how the same thing works for base 10."_

> 8 % 10 = 8

> 18 % 10 = 8

> 87865378 % 10 = 8

> 2387762348 % 10 = 8"

> _"Picking a big enough, non-power-of-two number will make sure the hash function
really is a function of all the input bits, rather than a subset of them."_

> _"`We don’t really need a prime number, just having a big non-power of two is enough`.
Having a prime number, obviously, is just a guaranteed way of satisfying those
conditions."_
>
Still worth reading the full explanation on his
website, [why-hash-tables-should-use-prime-number-size](https://quickmathintuitions.org/why-hash-tables-should-use-prime-number-size/) [1](#references).

### Big O table

| Operation      | time complexity | space complexity |
|----------------|-----------------|------------------|
| lookup (key)   | O(1)            | `O(n)`           |
| lookup (value) | `O(n)`          | `O(n)`           |
| insert         | O(1)            | `O(n)`           |
| delete         | O(1)            | `O(n)`           |

## References

1. Ottolenghi, S. (
    2017) [Why hash tables should use a prime-number size](https://quickmathintuitions.org/why-hash-tables-should-use-prime-number-size/),
          Quick Math Intuitions. (Accessed: 9 June 2024).

