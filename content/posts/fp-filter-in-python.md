+++
draft = true
date = 2024-06-29
title = "Playing with built-ins: filter()"
description = "The benefits of using filter()"
slug = "python-filter-in-python"
authors = ["Diogo Pessoa"]
tags = ["python", "map-filter-reduce", "functional-programming"]
categories = ["functional-programming", "algorithms"]

+++

{{<toc>}}

## Filter

> filter(function or None, iterable) --> filter object
> Return an iterator yielding those items of iterable for which function(item)
> is true. If function is None, return the items that are true.

## The power of combining both

A map can call a filter to apply a transformation on a reduced set of values.

```python
    def test_mapping_filtering(self):
        numbers = [1, 2, 3, 4]
        squared = map(lambda x: x ** 2, filter(lambda x: x % 2 == 0, numbers))
        print(list(squared))
```

```python
    

<class 'filter'>
filtered evens: [2, 4]
resulting map:  [4, 16] # squared of the filtered evens

filter(function or None, iterable) --> filter object
   Return an iterator yielding those items of iterable for which function(item)
   is true. If function is None, return the items that are true.
```

## Reduce

Apply function of two arguments cumulatively to the items of iterable, from left to right, to reduce
the iterable to a
single value.

## References

1. Lambda-expressions. Available
   at: https://docs.python.org/3/tutorial/controlflow.html#lambda-expressions (Accessed:
   19 June 2024).
2. functools.reduce — Higher-order functions and operations on callable objects (no
   date) Python documentation. Available
   at: https://docs.python.org/3/library/functools.html#functools.reduce (
   Accessed: 19
   June 2024).
