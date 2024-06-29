+++
draft = true
date = 2024-06-04
title = "Big O Notation notes"
description = "Notes from my interview preparation on Big O Notation topic."
slug = "BigO-notation"
url = "posts/BigO-notation"
authors = ["Diogo Pessoa"]
tags = ["big-o", "algorithms"]
categories = ["Data Structures", "algorithms"]
+++

{{<toc>}}

# Summary

This is my summary on Big O Notation

Big O notation is usually use to measure time and space complexity of algorithms. It is
a way to describe how the runtime of an algorithm grows as the input grows.

Depending on the problem, we can favor time complexity, space complexity or a balance
between the two.

## Space complexity

Space complexity is the amount of memory an algorithm uses to run. It is usually. I'll
create a separate post for space complexity. Additionally, when covering Sorting
algorithms Space complexity will become more relevant.

from bigOcheatsheet.com, [sorting algorithms](https://www.bigocheatsheet.com/#sorting).

## Time complexity

### quick table of common time complexities in n = 100:

| O(1) | O(log n) | O(n) | O(n log n) | O(n^2) | O(2^n)   | O(n!)     |
|------|----------|------|------------|--------|----------|-----------|
| 1    | 7        | 100  | 464        | 10,000 | 1.27e+30 | 9.33e+157 |

### brain hacks for memorizing time complexities.

| algorithm          | time complexity | 
|--------------------|-----------------|
| a loop             | O(n)            |
| a nested loop      | O(n^2)          |
| divide and conquer | O(log n)        |
| constant           | O(1)            |

## Big O Worst case

O (Omicron) usually represents the worst case scenario. It is the upper bound of the
algorithm.
Generally, we are interested in the worst case scenario because it gives us a guarantee
that the algorithm will run in a certain time. Therefore we tend to evaluate the "best
Big O" for the worst case scenario.

### O(n) - Linear Time Complexity

The runtime grows linearly with the size of the input.

```python

    def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
```

### O(n^2) - Quadratic Time Complexity

The runtime grows quadratically with the size of the input.

It is usually found in nested loops. `O = n * n or O(n^2)`.

```python

    def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range(len(arr) - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
```

### O(1) - Constant Time Complexity

The runtime is constant, it does not depend on the size of the input. `O(1)` - Constant
time.

```python

    def print_first(arr):
    print(arr[0])
```

### O(log n) - Logarithmic Time Complexity

The runtime grows logarithmically with the size of the input.

In simpler terms: how many times would one need to half the target to reach 1. In
general, we aim to reach the target in log(n) steps in time complexity.

```python

    def binary_search(arr, target):
    left = 0
    right = len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

## Simplifying Big O notation

### Drop Constants in O(n).

When analyzing the time complexity of an algorithm, we can drop the constants.

O of 2n is the same as O of n.

```python

    def linear_search(arr, target):
    for i in range(len(arr)):
        print(arr[i])
    for i in range(len(arr)):
        print(arr[i])
```

### Drop Non-Dominant Terms

When analyzing the time complexity of an algorithm, we can drop the non-dominant terms.
Since the non-dominant is insignificant when the input is large we drop the
non-dominant.

`O(n + n^2) = O(n^2)`

```python
    # O(n + n^2) = O(n^2)
    def print_pairs(arr):
    for i in range(len(arr)):
        for j in range(len(arr)):
            print(arr[i], arr[j])
    for i in range(len(arr)):
        print(arr[i])
```

## Different terms for inputs.

### O(n + m) - example Linear Time Complexity

When we have two different inputs, we can represent them as `O(n + m)`.

```python

    def print_pairs(arr1, arr2):
    for i in range(len(arr1)):
        print(arr1[i])
    for i in range(len(arr2)):
        print(arr2[i])
```

### O(n * m) - example Quadratic Time Complexity

When we have two different inputs, we can represent them as `O(n * m)`.

```python

    def print_pairs(arr1, arr2):
    for i in range(len(arr1)):
        for j in range(len(arr2)):
            print(arr1[i], arr2[j])
```

references:

* Know Thy Complexities!. Available at: https://www.bigocheatsheet.com/ (Accessed: 4
  June 2024).
* Data-structures from bigOcheatsheet.com. Available at:
  https://www.bigocheatsheet.com/#data-structures (Accessed: 4 June 2024).
* Sorting algorithms from bigOcheatsheet.com. Available at:
  https://www.bigocheatsheet.com/#sorting (Accessed: 4 June 2024).
* Big O Notation Chart from bigOcheatsheet.com. Available at:
  https://www.bigocheatsheet.com/#chartTitle (Accessed: 4 June 2024).
