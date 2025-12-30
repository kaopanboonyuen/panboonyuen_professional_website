---
title: LC-TEST-02 — Prime Number Check
weight: 50
date: '2025-12-30'
type: book
---

<!--more-->

## Problem Statement

Given an integer `n`, determine whether it is a prime number.

## Sample Input / Output

| Input | Output |
|------|--------|
| 2 | True |
| 3 | True |
| 4 | False |
| 17 | True |
| 1 | False |

## Python Solution

```python
def is_prime(n):
    """
    Check whether n is a prime number.
    """
    if n <= 1:
        return False

    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True
```

## Complexity Analysis

- Time Complexity: **O(√n)**
- Space Complexity: **O(1)**
