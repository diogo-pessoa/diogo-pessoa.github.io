+++
draft = true
date = 2024-06-11
title = "Bubble Sort"
description = ""
slug = "bubble-sort"
authors = ["Diogo Pessoa"]
tags = ["algorithms", "sorting"]
categories = ["algorithms"]

+++


{{<toc>}}

## Summary

Bubble sort is a simple sorting algorithm that repeatedly steps through the list,
compares adjacent elements and swaps them if they are in the wrong order.


- [My implementation](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/algorithms/bubblesort)

## How it works

1. Start at the beginning of the list.
2. Compare each pair of adjacent elements.
3. If the first element is greater than the second, swap them.
4. Move to the next pair and repeat the process until the end of the list is reached.
5. Repeat the process for the entire list until no swaps are needed.

* Time Complexity:
    * Worst-case:
        * `𝑂(𝑛2)`
    * Best-case:
        * `O(n)` when the array is already sorted
    * Average-case:
        * `O(n2)`
* Space Complexity:
    * `O(1)` - As it’s an in-place sorting algorithm

### Test Results

```python
Running test: test_running_both_sorts
list len: 2706
sort_while took 0.425723 seconds to execute
sort_double_for took 0.383738 seconds to execute
Running test: test_sort_one_loop
Unsorted list len: 126
sort_while took 0.000700 seconds to execute
Running test: test_sort_two_loops
Unsorted list: 3580
```

### Observations
