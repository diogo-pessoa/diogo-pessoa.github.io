+++
draft = true
date = 2024-06-14
title = "Longest Palindromic Substrings - code exercises and Manacher algorithm"
description = ""
slug = "longest-palindromic-substrings"
authors = ["Diogo Pessoa"]
tags = ["python", "algorithms"]
categories = ["algorithms"]

+++

{{< toc >}}

## Summary

- [Conventions](https://diogo-pessoa.github.io/posts/conventions)
- [My solution](

## Big O and performance

In my solution I used the "expand around center approach". The Big O complexity is O(
n^2) because we have to check every character in the string and expand around it.

`(draft)`

## Tests

```python
Ran 3 tests in 0.002s

OK
Running test: test_find_longest_palindromic_substring
find_longest_palindromic_substring took 0.000027 seconds to execute
Running test: test_find_longest_palindromic_substring_bb
find_longest_palindromic_substring took 0.000016 seconds to execute
Running test: test_find_longest_palindromic_substring_with_manacher_approach
longest_palindromic_substring took 0.000042 seconds to execute

```

### what is the time complexity of the solution?

## The Manacher algorithm

https://www.baeldung.com/cs/manachers-algorithm
