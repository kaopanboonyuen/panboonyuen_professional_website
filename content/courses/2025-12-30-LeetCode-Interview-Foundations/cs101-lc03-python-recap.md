---
title: CS101-LC03 — Python for Interviews (From Zero to Thinking Like an Engineer)
weight: 30
date: '2025-12-30'
type: book
---

<!--more-->

## 🎯 Why Python Matters in Interviews (Real World Edition)

Python is not tested because it is easy.

Python is tested because:

> **It exposes how you think.**

Interviewers look for:
- Can you break a problem into steps?
- Do you choose the right container?
- Can you read your own code after 6 months?
- Do you understand cost (time & memory)?

Python is a **mirror of your thinking quality**.

---

## 🧠 How Strong Python Engineers Think

Before writing code, they ask:

1. What is the **input shape**?
2. What must I **track**?
3. What repeats? (loops)
4. What must be **fast lookup**? (set / dict)
5. What logic can become a function?

This chapter builds that instinct.

---

## 🔁 Absolute Basics (Interview Warm-Up)

These problems look easy, but **many candidates fail them**.

### 🔢 Problem 1 — Count Prime Numbers (Classic Warm-Up)

**Task:**  
Given `n`, count how many prime numbers are `< n`.

```python
def count_primes(n):
    def is_prime(x):
        if x < 2:
            return False
        for i in range(2, int(x**0.5) + 1):
            if x % i == 0:
                return False
        return True

    count = 0
    for i in range(n):
        if is_prime(i):
            count += 1
    return count
```

🧠 Why interviewers love this:

* Loop control
* Early break
* Math intuition
* Nested functions

---

### 🔢 Problem 2 — Frequency Counter (Real Life)

**Task:**
Count how many times each number appears.

```python
def frequency(arr):
    freq = {}
    for x in arr:
        freq[x] = freq.get(x, 0) + 1
    return freq
```

Used everywhere:

* Logs
* NLP tokens
* Event analytics
* ML preprocessing

---

## 🔁 Iteration Patterns (Fundamental Thinking)

### Looping Over Values

```python
for x in arr:
    print(x)
```

Use when:

* You don’t care about position
* Logic depends only on value

---

### Looping With Index (IMPORTANT)

```python
for i, x in enumerate(arr):
    print(i, x)
```

Use when:

* Position matters
* Sliding window
* Adjacent comparison

---

### Looping With Range (Indexing Power)

```python
for i in range(0, len(arr), 2):
    print(arr[i])
```

This is how **real indexing problems are solved**.

---

## 🧺 Containers (The Core of Python Power)

### List — Ordered, Mutable

```python
nums = [1, 2, 3]
nums.append(4)
```

Use when:

* Order matters
* Sequential access
* Sliding window

---

### Tuple — Fixed, Safe

```python
point = (3, 4)
```

Use when:

* Coordinates
* Keys in dict
* Immutable records

---

### Set — Fast Membership

```python
seen = set()
if x in seen:
    print("Duplicate")
```

⏱️ Average lookup: **O(1)**
Used in:

* Deduplication
* Cycle detection
* Graphs

---

### Dictionary — The Interview Weapon

```python
freq = {}
for x in arr:
    freq[x] = freq.get(x, 0) + 1
```

Used for:

* Counting
* Mapping
* Caching
* DP states

> If you master dictionaries, **half of LeetCode disappears**.

---

## 🔍 Searching Patterns

### Linear Search (Baseline)

```python
def linear_search(arr, target):
    for x in arr:
        if x == target:
            return True
    return False
```

⏱️ O(n)

---

### Binary Search (Mindset Shift)

```python
def binary_search(arr, target):
    l, r = 0, len(arr) - 1

    while l <= r:
        mid = (l + r) // 2
        if arr[mid] == target:
            return True
        elif arr[mid] < target:
            l = mid + 1
        else:
            r = mid - 1

    return False
```

⏱️ O(log n)

Interviewers care more about:

> **Why binary search works**, not syntax.

---

## 🧮 Vector Thinking (AI & Data Foundation)

### Vector Addition

```python
def add_vectors(a, b):
    return [a[i] + b[i] for i in range(len(a))]
```

---

### Dot Product

```python
def dot(a, b):
    return sum(a[i] * b[i] for i in range(len(a)))
```

Used in:

* Neural networks
* Similarity search
* Attention mechanisms

---

## 🧱 Matrix Thinking (2D Indexing)

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]
```

### Traversal

```python
for i in range(len(matrix)):
    for j in range(len(matrix[0])):
        print(matrix[i][j])
```

Index control = **engineering maturity**.

---

### Matrix Multiplication (Classic Filter)

```python
def matmul(A, B):
    result = [[0]*len(B[0]) for _ in range(len(A))]

    for i in range(len(A)):
        for j in range(len(B[0])):
            for k in range(len(B)):
                result[i][j] += A[i][k] * B[k][j]

    return result
```

⏱️ O(n³)

---

## 🧠 Functions = Thinking Units

```python
def square(x: int) -> int:
    return x * x
```

Good functions:

* Do one thing
* Have clear inputs/outputs
* Are testable

---

## 🧱 Classes (Engineer Level)

```python
class Vector:
    def __init__(self, values):
        self.values = values

    def dot(self, other):
        return sum(a*b for a, b in zip(self.values, other.values))
```

Why classes matter:

* Modeling real systems
* Clean APIs
* Interview design questions

---

## 🧬 Inheritance (Abstraction Skill)

```python
class Matrix(Vector):
    def shape(self):
        return (len(self.values), len(self.values[0]))
```

Used in:

* Frameworks
* ML pipelines
* Systems design

---

## 🧠 Pythonic Patterns Interviewers Love

### List Comprehension

```python
[x*x for x in range(10) if x % 2 == 0]
```

---

### Dictionary Comprehension

```python
{x: arr.count(x) for x in set(arr)}
```

---

### any / all

```python
any(x < 0 for x in arr)
all(x > 0 for x in arr)
```

---

## 🚨 Common Interview Mistakes

❌ Writing code before thinking
❌ Ignoring complexity
❌ Using wrong container
❌ Overengineering simple logic

---

## 🏁 Final Takeaway

> Python interviews are not about Python.
>
> They are about **structured thinking**.

If you can:

* Count primes
* Track frequencies
* Control indices
* Design functions
* Choose containers wisely

You are **ready for real interviews**.

---