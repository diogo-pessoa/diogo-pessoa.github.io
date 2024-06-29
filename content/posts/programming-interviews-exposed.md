+++
title = 'Programming Interviews Exposed'
description = "Notes from the book Programming Interviews Exposed"
date = 2024-06-07
draft = true
slug = "programming-interviews-exposed"
authors = ["Diogo Pessoa"]
tags = ["book-summaries", "coding"]
categories = ["summary"]

+++

{{< toc >}}

## Summary

- **Book:** Programming Interviews Exposed: Secrets to Landing Your Next Job
- **Authors:** John Mongan, Noah Suojanen, and Eric Giguère

The Programming interview Exposed covers the essential topics for preparing for a
technical interview (in software development). I'm trying to capture the essence of the
proposal and structure into steps. Then, I can structure my thought and preparation for
preparing and sitting through an interview.

### Conventions Used in all my notes



## Notes from book

### From Chapter 3: Approach to Programming Problems

`That's right! I skipped a bunch of pages` :grimacing:

#### Basics

1. _Make sure you understand the Problem_

2. _Once you understand the problem, try an example._

> `note to self`: Once you understand the problem (go back to step 1, you're
> probably
> rushing). If this is the second-time you're reading this. What worked for me
> before to
> fully understand the problem was to write down the brute-force solution.

* As I wrote the brute-force solution. The problem became clearer. I elaborated
  questions, and most importantly, I proved my initial assumptions wrong.
* Keep in mind this could take some of your interview time(it's worth it).

3. _Focus on the algorithm you will use to solve the
   problem_ `(Once your have the brute-force solution, you already solved the problem,
   it's crap,
   but solved)`.
    * It now a refactoring problem. It's much easier to solve smaller problem.
    * Review the constraints, they may be useful restructure the code.
        * for Example: In a problem in counting characters (a-z,A-Z,0-9) where space is
          a constraint.
            * you can use
              a [Counter()](https://docs.python.org/3/library/collections.html#collections.Counter)
              collection (not talking about the tech solution, if you curious follow the
              link).
            * That helps, because the constraint tells you only alphanumeric characters
              are allowed. there's a limited set of those characters in the ascii.
            * The constraint is now part of your solution.

> `note to self:`For step 3 I noticed the book and other sources recommend, writing in a
> paper and
> going
> over the algorithm before start writing. During practice that didn't work for me. I
> needed to write bad code first, then refactor.

I also generally write the code on my own IDE (when possible), with the test case
calling the function.

**Big Words Warning:** `Feedback loop` - I need to see the code running (often not
running),
to understand the path I'm taking.

* _While you code it's important to explain what you're doing_

4. **_Ask questions when necessary_.** "_You generally won’t be penalized for asking factual questions that you might otherwise look up in a reference._"

## References

* Jhu.edu. Available
  at: http://taltos.pha.jhu.edu/~gupchup/tmp/app/material/programming-interviews-exposed.pdf (
  Accessed: 7 June 2024).
* The emojis are from [Hugo emojis page](https://gohugo.io/quick-reference/emojis/)

## Glossary of terms

* `(If this is empty, either I was super clear, or I'm super lazy. I'll let me decide.)`
