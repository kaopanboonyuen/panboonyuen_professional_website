---
title: LC-TEST-05 — Two Sum (Brute Force → Hash Map)
weight: 80
date: '2025-12-30'
type: book
---

<!--more-->

## 🧩 Problem Statement

Given an integer array `nums` and an integer `target`, return the **indices of two numbers** such that they add up to `target`.

You may assume that **exactly one solution exists**, and you may not use the same element twice.

---

## 📥 Sample Input / 📤 Output

| nums | target | Output |
|------|--------|--------|
| [2,7,11,15] | 9 | [0,1] |
| [3,2,4] | 6 | [1,2] |
| [3,3] | 6 | [0,1] |
| [1,5,1,5] | 10 | [1,3] |
| [-1,-2,-3,-4] | -6 | [1,3] |

---

## 🧠 Interviewer Expectation

This problem tests:
- Nested loop thinking
- Optimization awareness
- Hash map mastery

---

## 🧩 Approach 1 — Brute Force (Nested Loop)

```python
def two_sum_bruteforce(nums, target):
    n = len(nums)

    for i in range(n):
        for j in range(i + 1, n):
            if nums[i] + nums[j] == target:
                return [i, j]
````

### ⏱️ Complexity

* Time: **O(n²)**
* Space: **O(1)**

🟡 Correct but inefficient.

---

## 🧩 Approach 2 — Hash Map (Optimal)

### 💡 Idea

Store numbers we have seen and check if `target - current` exists.

```python
def two_sum(nums, target):
    seen = {}

    for i, v in enumerate(nums):
        complement = target - v

        if complement in seen:
            return [seen[complement], i]

        seen[v] = i
```

### ⏱️ Complexity

* Time: **O(n)**
* Space: **O(n)**

🟢 Interview-ready solution.

---

## 🏁 Takeaway

> “Use brute force to understand the problem.
> Use hash maps to solve it like a professional.”

---

# 📘 Matrix Traversal Patterns

## 🧩 Problem Statement

Given a 2D matrix, traverse it in different patterns:
- Row-wise
- Column-wise
- Diagonal
- Spiral

---

## 📥 Sample Matrix

```text
1  2  3
4  5  6
7  8  9
````

---

## 🧩 Row-wise Traversal

```python
for row in matrix:
    for value in row:
        print(value)
```

---

## 🧩 Column-wise Traversal

```python
rows, cols = len(matrix), len(matrix[0])

for c in range(cols):
    for r in range(rows):
        print(matrix[r][c])
```

---

## 🧩 Diagonal Traversal

```python
n = len(matrix)

for i in range(n):
    print(matrix[i][i])
```

---

## 🧩 Spiral Traversal (Interview Favorite)

```python
def spiral(matrix):
    res = []
    top, bottom = 0, len(matrix)-1
    left, right = 0, len(matrix[0])-1

    while top <= bottom and left <= right:
        for c in range(left, right+1):
            res.append(matrix[top][c])
        top += 1

        for r in range(top, bottom+1):
            res.append(matrix[r][right])
        right -= 1

        if top <= bottom:
            for c in range(right, left-1, -1):
                res.append(matrix[bottom][c])
            bottom -= 1

        if left <= right:
            for r in range(bottom, top-1, -1):
                res.append(matrix[r][left])
            left += 1

    return res
```

---

## ⏱️ Complexity

* Time: **O(m × n)**
* Space: **O(1)** (excluding output)

---

## 🏁 Takeaway

Matrix traversal shows **index control mastery**, critical for vision and AI tasks.

---

# 📘 Prefix Sum (Killing Nested Loops)

## 🧩 Problem Statement

Given an array `nums`, answer multiple range sum queries efficiently.

---

## 📥 Example

nums = `[1, 2, 3, 4, 5]`  
Query sum of range `[1,3]` → `2 + 3 + 4 = 9`

---

## 🧩 Brute Force

```python
def range_sum(nums, l, r):
    total = 0
    for i in range(l, r+1):
        total += nums[i]
    return total
````

⏱️ **O(n)** per query ❌

---

## 🧩 Prefix Sum Optimization

### 💡 Idea

Precompute cumulative sums once.

```python
def build_prefix(nums):
    prefix = [0]
    for v in nums:
        prefix.append(prefix[-1] + v)
    return prefix

def range_sum(prefix, l, r):
    return prefix[r+1] - prefix[l]
```

---

## ⏱️ Complexity

* Preprocessing: **O(n)**
* Query: **O(1)**

🟢 Essential for AI data pipelines.

---

## 🏁 Takeaway

Prefix sums turn **nested loops into math**.

---

# 📘 Sliding Window

## 🧩 Problem Statement

Given an array `nums` and integer `k`, find the **maximum sum of any subarray of size k**.

---

## 📥 Example

nums = `[2,1,5,1,3,2]`, k = 3  
Output → `9` (`[5,1,3]`)

---

## 🧩 Brute Force

```python
def max_sum(nums, k):
    max_sum = 0
    for i in range(len(nums) - k + 1):
        max_sum = max(max_sum, sum(nums[i:i+k]))
    return max_sum
````

⏱️ **O(nk)** ❌

---

## 🧩 Sliding Window Optimization

```python
def max_sum(nums, k):
    window_sum = sum(nums[:k])
    max_sum = window_sum

    for i in range(k, len(nums)):
        window_sum += nums[i]
        window_sum -= nums[i-k]
        max_sum = max(max_sum, window_sum)

    return max_sum
```

---

## ⏱️ Complexity

* Time: **O(n)**
* Space: **O(1)**

---

## 🏁 Takeaway

Sliding window is **mandatory knowledge** for interviews.

---

# 📘 Linear Algebra for AI (Vectors & Matrices)

## 🎯 Why Linear Algebra Matters

Linear algebra is the **language of AI**:
- Neural networks
- Embeddings
- Transformers
- Computer vision

---

## 🧮 Vectors

A vector represents **features**.

```python
x = [1, 2, 3]
````

---

## ➕ Vector Addition

```python
def add(a, b):
    return [a[i] + b[i] for i in range(len(a))]
```

⏱️ O(n)

---

## ✖️ Dot Product (Core of Neural Networks)

```python
def dot(a, b):
    return sum(a[i] * b[i] for i in range(len(a)))
```

---

## 🧱 Matrices

```python
A = [
    [1, 2],
    [3, 4]
]
```

---

## ✖️ Matrix Multiplication

```python
def matmul(A, B):
    res = [[0]*len(B[0]) for _ in range(len(A))]

    for i in range(len(A)):
        for j in range(len(B[0])):
            for k in range(len(B)):
                res[i][j] += A[i][k] * B[k][j]

    return res
```

⏱️ **O(n³)**

---

## 🧠 AI Interpretation

| Math        | AI Meaning        |
| ----------- | ----------------- |
| Vector      | Feature embedding |
| Dot product | Similarity        |
| Matrix      | Layer weights     |
| MatMul      | Forward pass      |

---

## 🏁 Final Thought

> If algorithms are **logic**,
> linear algebra is **meaning** in AI.