+++
draft = false
date = 2024-06-04
title = "Big O for Python lists"
description = ""
slug = "Python-lists-BigO"
url = "posts/Python-lists-BigO"
authors = ["Diogo Pessoa"]
tags = ["interview-prep", "big-o", "algorithms", "python", "lists"]
categories = ["interview-prep", "algorithms", "coding", "python"]
externalLink = ""
series = []
+++

{{<toc>}}

# Summary

Big O of python list operations.

## Operations

### append() an element to the end of a list O(1).

Constant time complexity because the operation does not depend on the size of the list.

```python
    arr = [1, 2, 3, 4, 5]
    arr.append(6)
    print(arr) # [1, 2, 3, 4, 5, 6]
```

### pop() an element from the end of a list O(1).

Constant time complexity because the operation does not depend on the size of the list.

```python
    arr = [1, 2, 3, 4, 5]
    arr.pop()
    print(arr) # [1, 2, 3, 4]
```

### pop() an element from a specific index O(n).

Linear time complexity because the operation depends on the size of the list.

```python
    arr = [1, 2, 3, 4, 5]
    arr.pop(2)
    print(arr) # [1, 2, 4, 5]
```

### Insert() an element at a specific index O(n).

Linear time complexity because the operation depends on the size of the list.

even if we insert in the middle of the list, the operation will take O(n) time because
we need to shift all the elements to the right.

and the notation is `O(n)` because the half is a constant and we drop constants in Big O
notation.

```python
    arr = [1, 2, 3, 4, 5]
    arr.insert(2, 10)
    print(arr) # [1, 2, 10, 3, 4, 5]
```

### search for an element by value in a list O(n).

Linear time complexity because the operation depends on the size of the list. We don't
know where the value is.

```python
    arr = [1, 2, 3, 4, 5]
    print(arr.index(3)) # 2
```

### search for an element by index in a list O(1).

Constant time complexity because the operation does not depend on the size of the list.
We go straight to the index.

```python
    arr = [1, 2, 3, 4, 5]
    print(arr[2]) # 3
```

