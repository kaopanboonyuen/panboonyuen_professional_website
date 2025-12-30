---
title: CS101-LC03 — Python for Interviews
weight: 30
date: '2025-12-30'
type: book
---

<!--more-->

## 🎯 Why Python Matters in Interviews

Python is not just a language.  
It is a **thinking tool**.

Interviewers use Python to test:
- Clarity of thought
- Data structure mastery
- Algorithmic intuition
- Code readability

---

## 🧠 Core Python Philosophy

> Simple is better than complex.  
> Readability counts.

If your code is easy to read, it is easy to debug and scale.

---

## 🔁 Iteration Patterns (Fundamental)

### Looping Over Values

```python
for x in arr:
    print(x)
````

### Looping With Index

```python
for i, x in enumerate(arr):
    print(i, x)
```

### Looping in Reverse

```python
for x in reversed(arr):
    print(x)
```

---

## 🧺 Containers in Python

### List (Ordered, Mutable)

```python
nums = [1, 2, 3]
nums.append(4)
```

Use when:

* Order matters
* Frequent appends

---

### Tuple (Ordered, Immutable)

```python
point = (3, 4)
```

Use when:

* Data should not change
* Hashable keys

---

### Set (Unique Elements)

```python
seen = set()
seen.add(1)
```

Use when:

* Deduplication
* Fast membership test

⏱️ Average lookup: **O(1)**

---

### Dictionary (Key → Value)

```python
freq = {}
for x in arr:
    freq[x] = freq.get(x, 0) + 1
```

Use when:

* Counting
* Mapping
* Fast lookup

{{< spoiler text="Why dictionaries are powerful?" >}}
They use hash tables, giving **O(1)** average access time.
{{< /spoiler >}}

---

## 🔍 Searching Patterns

### Linear Search

```python
def linear_search(arr, target):
    for x in arr:
        if x == target:
            return True
    return False
```

⏱️ O(n)

---

### Binary Search (Sorted Array)

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

---

## 🧮 Vector Operations (AI Foundation)

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
* Similarity
* Attention

---

## 🧱 Matrix Basics (2D Lists)

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]
```

### Matrix Traversal

```python
for row in matrix:
    for val in row:
        print(val)
```

---

### Matrix Multiplication (Interview Classic)

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

## 🧠 Functions & Clean Design

```python
def square(x: int) -> int:
    return x * x
```

Why types help:

* Clarity
* Debugging
* Documentation

---

## 🧱 Classes & Objects (VERY IMPORTANT)

### Defining a Class

```python
class Vector:
    def __init__(self, values):
        self.values = values

    def dot(self, other):
        return sum(a*b for a, b in zip(self.values, other.values))
```

---

### Using the Class

```python
v1 = Vector([1, 2, 3])
v2 = Vector([4, 5, 6])
print(v1.dot(v2))
```

---

## 🧬 Inheritance (Interview Favorite)

```python
class Matrix(Vector):
    def shape(self):
        return (len(self.values), len(self.values[0]))
```

Why inheritance matters:

* Code reuse
* Abstraction
* Design thinking

---

## 🧠 Pythonic Tricks Interviewers Love

### List Comprehension

```python
squares = [x*x for x in range(10)]
```

---

### Dictionary Comprehension

```python
freq = {x: arr.count(x) for x in arr}
```

---

### Any / All

```python
any(x > 0 for x in arr)
all(x > 0 for x in arr)
```

---

## 🚨 Common Interview Mistakes

❌ Overcomplicating
❌ Ignoring edge cases
❌ Forgetting time complexity
❌ Writing unreadable code

---

## 🏁 Final Interview Advice

> Python interviews are not about syntax.
> They are about **how you think**.

If you master:

* Containers
* Loops
* Functions
* Classes
* Vectors & matrices

You are **interview-ready**.

---

## 🎉 Congratulations

This chapter alone covers:

* CS fundamentals
* LeetCode readiness
* AI mathematical intuition
* Clean software design

You’re officially dangerous now 😄🔥