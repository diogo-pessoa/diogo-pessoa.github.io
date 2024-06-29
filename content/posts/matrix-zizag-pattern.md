+++
draft = true
date = 2024-06-18
title = "Matrix - ZigZag Pattern"
description = ""
slug = "ZigZag-Pattern-matrix"
authors = ["Diogo Pessoa"]
tags = ["python", "data-structures", "algorithms", "Matrix"]
categories = ["algorithms", "data-structures", "Matrix"]
+++

{{<toc>}}

## Summary

- [Conventions](https://diogo-pessoa.github.io/posts/conventions)
- **My implementation:**
    - [Matrix - ZigZagConversion](https://github.com/diogo-pessoa/coding-exercises/tree/main/leetCode/zigzagconversion)
    - [LeetCode Problem](https://leetcode.com/problems/zigzag-conversion/)

### Understanding the Zigzag Pattern

When a string is written in a zigzag pattern across \( y \) rows:

- A complete cycle consists of moving down \( y \) rows and then moving diagonally up \(
  y-2 \) rows.
- The total number of characters in one cycle is \( 2y - 2 \).

### Derivation of the Number of Columns

Given:

- \( n \): the length of the string.
- \( y \): the number of rows.

1. **Calculate the Length of One Cycle:**
    - Each cycle covers \( 2y - 2 \) characters.

2. **Calculate the Number of Complete Cycles:**
    - The total number of complete cycles needed is \( \left\lceil \frac{n}{2y - 2}
      \right\rceil \), where \( \left\lceil \cdot \right\rceil \) denotes the ceiling
      function, which rounds up to the nearest integer.

3. **Calculate the Number of Columns per Cycle:**
    - Each cycle requires \( y-1 \) columns: \( y \) columns for the downward movement
      and \( y-1 \) columns for the diagonal upward movement.

4. **Total Number of Columns:**
    - The total number of columns is the number of complete cycles multiplied by the
      number of columns per cycle:
      \[
      \text{num\_cols} = \left\lceil \frac{n}{2y - 2} \right\rceil \times (y - 1)
      \]

### Example Calculation

Let's apply this to an example string with length \( n = 14 \) and \( y = 3 \) rows:

1. **Length of One Cycle:**
   \[
   2y - 2 = 2 \times 3 - 2 = 4
   \]

2. **Number of Complete Cycles:**
   \[
   \left\lceil \frac{14}{4} \right\rceil = \left\lceil 3.5 \right\rceil = 4
   \]

3. **Number of Columns per Cycle:**
   \[
   y - 1 = 3 - 1 = 2
   \]

4. **Total Number of Columns:**
   \[
   \text{num\_cols} = 4 \times 2 = 8
   \]

So, for a string of length 14 with 3 rows, the number of columns is 8.

### General Formula

For a string of length \( n \) and \( y \) rows:

1. Calculate the length of one cycle: \( 2y - 2 \).
2. Calculate the number of complete cycles: \( \left\lceil \frac{n}{2y - 2}
   \right\rceil \).
3. Calculate the number of columns per cycle: \( y - 1 \).
4. The total number of columns:
   \[
   \text{num\_cols} = \left\lceil \frac{n}{2y - 2} \right\rceil \times (y - 1)
   \]

This formula can be used to determine the number of columns required for any string
length \( n \) and any number of rows \( y \).
