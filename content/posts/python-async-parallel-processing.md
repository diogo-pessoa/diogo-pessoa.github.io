+++
draft = true
date = 2024-06-13
title = "Python Concurrency vs Parallel processing"
description = ""
slug = "concurrency-vs-parallel-processing"
authors = ["Diogo Pessoa"]
tags = ["python", "async", "parallel", "concurrency"]
categories = ["python", "concurrency", "system-design"]

+++

{{<toc>}}

## Summary

The parallel and concurrency processing are common conversations when talking systems
design. I'll take the free
time to play with both and understand `(and really explore)` the differences and use
cases. While at it, I'll also explore Async IO in Python, as I fell it's as good time as
any.

- [Conventions]({{< ref "posts/conventions-used-in-notes" >}} "conventions-used")
- [My implementations](#)

## Definitions

### Parallelism

Parallel processing is a type of computation in which many calculations or processes are
carried out simultaneously. Large problems can often be divided into smaller ones, which
can then be solved at the same time.

### Concurrency

Concurrency involves managing multiple tasks at the same time. These tasks can start,
run, and complete in overlapping periods. Concurrency is about dealing with many tasks
at once and can be achieved through various means, such as threading, asyncio, or
multiprocessing.

### Asynchronous Processing

Asynchronous processing allows a program to handle multiple tasks at once without
waiting for one to finish before starting another. It uses a single thread to manage
multiple tasks, switching between them as needed.

## Concurrency and parallelism are not mutually exclusive?

Concurrency and parallelism are not mutually exclusive. A program can be concurrent and
parallel at the same time. For example, a program that uses `multiple threads` to handle
`multiple tasks simultaneously` is both concurrent and parallel.

- **A real world example:** of this is a web server that can handle multiple requests at
  once. Each request is processed in a separate thread, but the server waits for each
  request to finish before sending a response.

### How Async fits on both

- **Async IO:** is a form of concurrency that allows a program to handle multiple tasks
  at once without waiting for one to finish before starting another. It uses a single
  thread to manage multiple tasks, switching between them as needed.

- Cases:
    - **In parallelism context:** Async IO can be used to handle multiple tasks
      simultaneously, allowing a program to process tasks concurrently without waiting
      for one to finish before starting another.

      - **In concurrency context:** Async IO can be used to manage multiple tasks at once,
        allowing a program to handle tasks concurrently without waiting for one to finish
        before starting another.

### Observations and my thoughts on the Use Cases

- **Asynchronous Processing:**
    - **Use Cases:**
        - **I/O Bound tasks:** Tasks that spend most of their time waiting for I/O
          operations to complete. `(e.g., network requests, file reads/writes)`
        - **Non-blocking tasks:** Tasks that can be started and stopped without
          affecting other tasks. `(e.g., user input, GUI events)`
        - **Tasks that can be paused and resumed:** Tasks that can be paused and
          resumed at any time without losing progress. `(e.g., video streaming, game
          loops)`
    - **Pros:**
        - **Efficient use of resources:** Asynchronous processing allows a program to
          handle multiple tasks with a single thread, reducing the overhead of
          creating and managing multiple threads.
        - **Improved responsiveness:** Asynchronous processing allows a program to
          respond to events as they occur, rather than waiting for one task to finish
          before starting another.
        - **Scalability:** Asynchronous processing allows a program to handle more
          tasks without increasing the number of threads, making it easier to scale
          the program as needed.
    - **Cons:**
        - **Complexity:** Asynchronous processing can be more complex than synchronous
          processing, as it requires managing multiple tasks and handling
          synchronization between them.
        - **Debugging:** Asynchronous processing can make it harder to debug a program,
          as tasks can be started and stopped at any time, making it difficult to
          trace the flow of execution.
        - **Resource management:** Asynchronous processing can be more challenging to
          manage than synchronous processing, as tasks can run concurrently and
          compete for resources.
- **Parallel Processing:**
  - **Use Cases:**
      - **CPU Bound tasks:** Tasks that require a lot of processing power and can be
        divided into smaller subtasks that can be executed in parallel.
      - **Tasks that can be divided into smaller subtasks:** Tasks that can be divided
        into smaller subtasks that can be executed independently and combined to
        produce the final result.
      - **Tasks that can be executed concurrently:** Tasks that can be executed
        concurrently without affecting each other. `(e.g., image processing, video
        encoding)`

## References

1. Python asyncio Documentation
2. Python multiprocessing Documentation
3. Real Python: Async IO in Python: A Complete Walkthrough
4. Real Python: An Intro to Threading in Python
