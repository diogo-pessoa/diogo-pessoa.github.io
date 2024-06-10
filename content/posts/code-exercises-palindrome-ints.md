+++
draft = false
date = 2024-06-10
title = "Checking if an integers is a palindrome"
description = "Challenge: don't convert the integer to a string."
slug = "code-exercise-palindrome-ints"
authors = ["Diogo Pessoa"]
tags = ["code-exercise", "python", "algorithms"]
categories = ["algorithms"]

+++

{{< toc >}}

## Summary

- [Conventions]({{< ref "posts/conventions-used-in-notes" >}} "conventions-used")
- [My solution](https://github.com/diogo-pessoa/coding-exercises-for-interviews/tree/main/leetCode/palindromeints)
- [LeetCode problem](https://leetcode.com/problems/palindrome-number/)

## Big O and performance

I tried the int approach as a mental exercise. After reviewing the problem and other
solutions it seems that the best approach is to convert the number to a string. The
faster results used string conversion.

* now String operations in Python seem pretty darn fast, apparently faster than integer
  operations. Maybe something to do with the underlying C implementation.
* The int() solution has multiple divisions operations, which are slower than
  immediately converting to a string and comparing against the reversed.


### Added timeit_decorator results


* For really large numbers:

you can see the actual difference in performance between the three approaches.

declaring the variable x, and converting to str(x) pays off with larger values. 
Considering we have to convert it twice in the return statement, if we weren't declaring the variable.


```python
Running test: test_palindrome_large_ints
int to check: 865737833338737568
is_palindrome_int took 0.000017 seconds to execute
is_palindrome_str took 0.000009 seconds to execute
is_palindrome_x_declared took 0.000002 seconds to execute
```

* Smaller random numbers:

`(For smaller integers String is still faster, but the difference is negligible)`

```python

Running test: test_palindrome_small_ints
int to check: 725527
725527
is_palindrome_int took 0.000005 seconds to execute
is_palindrome_str took 0.000003 seconds to execute
is_palindrome_x_declared took 0.000003 seconds to execute

```


## review of problem and solution

Initial checks

* I'm tempted to check for invalid inputs. Since I'm working with int(), I could check
  for type?
    * I didn't add to the solution, yet. Normally the problem will state if there are
      any constraints on the input.

```python
if not type(x) == int:
    return False
```

* If negative, the minus sign breaks palindrome property

```python
if x < 0:  
    return False
```

* If the last digit is 0, the first digit must be 0 (only the number 0 satisfies this
  condition)

```python
if x % 10 == 0 and x != 0:
    return False
```

The part I want to focus on:

```python
while x > reversed_num:
    reversed_num = reversed_num * 10 + x % 10
    x = x // 10

# The number is a palindrome if it is equal to its reverse or 
# if the reverse without the last digit (in the case of odd number of digits) is equal to the original number divided by 10
return x == reversed_num or x == reversed_num // 10
```

* How do we know when to stop:
    * The reversed number is larger than the original number. This means we have reached
      the
      middle of the number.
      `while x > reversed_num:`


* **_% (modulo)_** returns the remainder of the division. In this case, it returns the
  last
  digit of the number.
  `reversed_num = (reversed_num * 10) + (x % 10)` `(The parenthesis i not needed, just added as reference to what operations are done first)`
    * The reversed number is multiplied by 10 to make room for the new digit.
    * The last digit of the number is added to the reversed number (modulo).
* **_// (floor division)_** returns the integer division of the number. In this case, it
    * `x = x // 10` - returns the number without the last digit.
    * The last digit is removed from the number.
* `return x == revertedNumber or x == revertedNumber // 10`
    * The number is a palindrome if it is equal to its reverse or if the reverse without
      the
      last digit (in the case of odd number of digits) is equal to the original number
      divided by 10.

### Points that never crossed my mind :P

* The reversed number is larger than int.MAX `int.MAX`, hitting integer overflow
  problems.
* since the middle digit doesn't matter in palidrome(it will always equal to itself), we
  can simply get rid of it.
* When the length is an odd number, we can get rid of the middle digit:
    * `revertedNumber//10`
    * For example when the input is 12321, at the end of the while loop we get x = 12,
      revertedNumber = 123,

