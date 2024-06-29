+++
draft = true
date = 2024-06-11
title = "Quick Sort"
description = ""
slug = "quick-sort"
authors = ["Diogo Pessoa"]
tags = ["algorithms", "sorting"]
categories = ["algorithms"]

+++

{{<toc>}}

## Summary

Quick sort is a divide-and-conquer algorithm that works by selecting a pivot element
from the array and partitioning the other elements into two sub-arrays according to
whether they are less than or greater than the pivot. The sub-arrays are then sorted
recursively.


- [My implementation](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/algorithms/quicksort)

### How it works

1. Pick an element:

- How to pick a pivot element?
    - **first element**
        - simple but can be slow
        - **implications**: if the array is already sorted, it will be the worst case
          scenario (O(n^2))
    - **last element**
        - simple but can be slow
        - **implications**: if the array is already sorted, it will be the worst case
          scenario (O(n^2))
    - **random element**
        - better chance to avoid worst case scenario
        - **implications**: ?
    - **median of threes**
    - `(My implementation uses this approach)`
    - for all threes the _worst case_ is `O(n^2)`
    - pick the median of the first, middle and last element
    - why do this?
        - short-answer: `(and obivious)` to improve performance
        - Why and does it improve performance on sorted,reverse sorted and random?
            - `sorted` array:
                - **BigO** `O(n log n)`
                - The median of three (first, middle, last) in a sorted array will
                  **_always choose the middle element_**, resulting in a balanced
                  partition.
            - `reverse` sorted array:
                - **BigO** `O(n log n)`
                - The median of three (first, middle, last) in a reverse sorted array
                  will **_always choose the middle element_**, resulting in a balanced
                  partition.
            - `random` array:
            - **Big O** `O(n log n)`
                - Randomly picking a pivot could result in a bad choice, leading to
                  unbalanced partitions.
                - The median of three improves the chances of selecting a good pivot.
    - **Median of Medians**
    - A complex approach that guarantees the pivot is the median of the array
    - **implications**:
        - guarantees the pivot is the median of the array `(better performance)`
        - more complex to implement, and computationally expensive

### My test results


* both tests are using the same list: `[10, 7, 8, 9, 1, 5]`.

To be fair this list is close to the worst case scenario for the first element pivot.

After the first pass the pivot_index was: `5` which was the last
element `[5, 7, 8, 9, 1, 10]` :confounded:

Having said that, it proves the point on using the median of threes.

I have
a [@timeit_decorator](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/helpers/TimeItDecorator.py)
I use it to measure the time it takes to execute a function. Now, the cool unplanned
effect
of the decorator, is that it showed how many recursive calls were made.

* `quick_sort_first_el` made 6 recursive calls
    * `quick_sort_medians_of_threes` made 2 recursive calls
* sure, the initial run on the quick_sort_medias_of_threes, access the list 3 times
  to get the median of threes, but it's still faster than the first element pivot.
    * Big O to access an element in a list is `O(1)`, so it's not a big
      deal. `(at all)` :rocket:

```python
  first_element = list_to_sort[left_index]
  middle_element = list_to_sort[(left_index + right_index) // 2]
  last_element = list_to_sort[right_index]
  pivot = sorted([first_element, middle_element, last_element])[1]
```

* Then, create the lists for the left and right partitions, and sort them
  recursively.

```python
    lesser_partition = [value for value in list_to_sort if value < pivot]
    greater_partition = [value for value in list_to_sort if value > pivot]
    equal_partition = [value for value in list_to_sort if value == pivot]
```

* Finally, returning the three sorted partitions.

![sorted_partitions.png](/images/sorted_partitions.png)

#### Recursions counts, and execution time for the first element pivot

- test for pivot by first
  element [test_QuickSort.py#test__quick_sort_by_first_element](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/algorithms/quicksort/test_QuickSort.py#L12)

```python

Running test: test__quick_sort_by_first_element
quick_sort_first_el took 0.000001 seconds to execute
quick_sort_first_el took 0.000001 seconds to execute
quick_sort_first_el took 0.000001 seconds to execute
quick_sort_first_el took 0.000216 seconds to execute
quick_sort_first_el took 0.000774 seconds to execute
quick_sort_first_el took 0.000001 seconds to execute
quick_sort_first_el took 0.000955 seconds to execute
```

#### Recursions counts, and for the medians of threes

- test for pivot by medians of
  threes [test_QuickSort.py#test__quick_sort_by_median_of_three](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/algorithms/quicksort/test_QuickSort.py#L17)

```python

Running test: test__quick_sort_by_median_of_three
quick_sort_medians_of_threes took 0.000001 seconds to execute
quick_sort_medians_of_threes took 0.000001 seconds to execute

```




