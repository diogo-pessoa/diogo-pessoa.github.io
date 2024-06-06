+++
draft = true
date = "2024-06-01"
title = "Using Map, Filter and Reduce in Python"
description = ""
slug = "Python-map-filter-reduce"
authors = ["Diogo Pessoa"]
tags = ["python", "map-filter-reduce"]
categories = ["python"]
+++

# Summary

Python map, filter, and reduce functions are built-in functions that are used to process iterables.
These three built-in functions are said to facilitate a functional approach to programming in Python.

In this note I'm going over some of the common usages as a later reference.

{{<toc>}}

## Map

```python
from functools import reduce

# Map to print the number round down to the nearest integer.
my_floats = [4.35, 6.09, 3.25, 9.77, 2.16, 8.88, 4.59]

mapping_floats = map(lambda x: math.floor(x), my_floats)

print(type(mapping_floats))
>>> <class 'map'>

print(list(mapping_floats))
>>> [4, 6, 3, 9, 2, 8, 4]

```

## References

1. Map: Built-in Functions (no date) Python documentation. Available at: https://docs.python.org/3/library/functions.html (Accessed: 1 June 2024).



