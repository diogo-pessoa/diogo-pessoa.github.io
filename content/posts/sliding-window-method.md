+++
draft = false
date = 2024-06-06
title = "iterating over a list using the sliding window method"
description = ""
slug = "sliding-window-method"
authors = ["Diogo Pessoa"]
tags = ["python", "algorithms"]
categories = [ "algorithms"]
url = "iterating-over-a-list-using-the-sliding-window-method"
+++

{{< toc >}}

# Summary

The sliding window method is a technique used to iterate over a list by moving a window
of a fixed size across the list. This method is commonly used in algorithms that require
iterating over a list while maintaining a window of elements to perform some operation.

## How it works

The sliding window method works by defining a window of a fixed size that moves across
the list.
At each step, the window is shifted by one element, and the operation is performed on
the elements within the window.

- time complexity: O(n) - the time complexity is O(n) because we need to iterate over
  each element in the list. It's really O(2n), but we drop the constant factor.
- space complexity: O(m) - The space complexity is O(m) because we need to store the
  elements found within the characters_list. where m is the size of the character and
  its count.

## Example

While doing the Longest Substring Without Repeating Characters problem from Leet code, I
came across the sliding window method. The problem requires finding the length of the
longest substring without repeating characters in a given string.

### my self explaining of concept

#### moving the right pointer

We set two pointers, left and right, to the start of the list.

the first while will move the right point until the end of the list,

```python
while right < len(char_list):
  r_value = char_list[right]
  chars_counter[r_value] += 1 # indexing character by value, and incrementing
  ... (left while loop)
  right += 1
```

#### moving the left pointer

Within this while loop, we increment the count of the character in the Counter()
collection.

After incrementing the character count. We move the left pointer of the
sliding window.

This happens when a character is repeated in the substring.

The chars_counter is a Counter() collection that
keeps track of the frequency of each character in the current window (substring).

* The loop triggers when right value is repeated in the current window
* Inside the loop, the character at the left pointer (l_value) is
  identified, and its count in the chars_counter is decremented by 1
* left pointer is about to move one step to the right, leaving behind l_value, so its
  count should be reduced
* Finally, the left pointer is moved one step to the right (left += 1). Shrinking the
  window from the left
* The loop continues until the count of r_value in the
  chars_counter is not more than 1, which means there are no more repetitions of this
  character in the current window.

```python
  while chars_counter[r_value] > 1:
    l_value = char_list[left]
    chars_counter[l_value] -= 1
    left += 1
```

#### Calculating the longest_substring

The max function is used to compare the current `length of the longest substring` (
longest_substring) with the `length of the current window (right - left + 1)`.

* The +1 is necessary because both right and left are zero-based
  indices.
* Unless the current window is `greate than` the current longest substring the max
  function will return the current longest substring unchanged.
* This line of code is crucial for the algorithm to return the correct result.

```python
  longest_substring = max(longest_substring, right - left + 1) # update
```

### My Implementation of the sliding window method in Python (after reviewing other solutions and videos):

* [Sliding Window Method](https://github.com/diogo-pessoa/coding-exercises-for-interviews/blob/main/leetCode/longestsubstrings/LongestSubStrings.py)

```python
      from collections import Counter
      def longest_substring_without_repeating_characters():
        char_list = "abcabcbb"
        chars_counter = Counter() # could manually build a dict() - using counter instead.
        longest_substring = 0
        left = 0
        right = 0
        while right < len(char_list):
            r_value = char_list[right]
            chars_counter[r_value] += 1 # indexing character by value, and incrementing

            while chars_counter[r_value] > 1:
                l_value = char_list[left]
                chars_counter[l_value] -= 1
                left += 1

            longest_substring = max(longest_substring, right - left + 1) # update
            right += 1
        return longest_substring

```
