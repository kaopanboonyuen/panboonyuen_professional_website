---
title: LC-TEST-03 — Linear Search
weight: 60
date: '2025-12-30'
type: book
---

<!--more-->

## 🧩 Problem Statement

Given an array `nums` and a target value `x`, return `True` if `x` exists in the array, otherwise return `False`.

This problem evaluates:

- Your understanding of **search strategies**
- Whether you know **when sorted data matters**
- Your ability to trade **speed vs constraints**

---

## 📥 Sample Input / 📤 Output

| nums | x | Output |
|------|---|--------|
| [1, 2, 3] | 2 | True |
| [1, 2, 3] | 4 | False |
| [] | 1 | False |
| [5] | 5 | True |
| [2, 4, 6] | 3 | False |

---

## 🧠 Interviewer Insight

> ❗ Interviewers are not checking if you can scan an array.  
> They want to know:
>
> - Is the array **sorted**?
> - Is random access allowed?
> - How large is the data?
> - Can preprocessing help?

Below are **all major searching techniques**.

---

## ✅ Approach 1 — Linear Search (Baseline)

### 💡 Idea

Check every element **one by one** until the target is found.

Works on **any array**.

### 🧑‍💻 Code

```python
def linear_search(nums, x):
    for v in nums:
        if v == x:
            return True
    return False
````

### ⏱️ Complexity

* **Time:** O(n)
* **Space:** O(1)

🟢 Use when the array is **unsorted or very small**.

---

## 🧩 Approach 2 — Binary Search (Sorted Array Required)

### 💡 Idea

Repeatedly divide the search space in half.

Requires **sorted input**.

### 🧑‍💻 Code

```python
def binary_search(nums, x):
    left, right = 0, len(nums) - 1

    while left <= right:
        mid = (left + right) // 2

        if nums[mid] == x:
            return True
        elif nums[mid] < x:
            left = mid + 1
        else:
            right = mid - 1

    return False
```

### ⏱️ Complexity

* **Time:** O(log n)
* **Space:** O(1)

🟢 One of the **most important interview algorithms**.

---

## 🧩 Approach 3 — Binary Search (Recursive)

### 💡 Idea

Same logic as iterative binary search, implemented recursively.

### 🧑‍💻 Code

```python
def binary_search_recursive(nums, x, left, right):
    if left > right:
        return False

    mid = (left + right) // 2

    if nums[mid] == x:
        return True
    elif nums[mid] < x:
        return binary_search_recursive(nums, x, mid + 1, right)
    else:
        return binary_search_recursive(nums, x, left, mid - 1)
```

### ⏱️ Complexity

* **Time:** O(log n)
* **Space:** O(log n) (recursion stack)

🟡 Use only if recursion is preferred.

---

## 🧩 Approach 4 — Jump Search (Sorted Array)

### 💡 Idea

Jump ahead by fixed steps (√n) instead of checking every element.

Useful when **random access is costly**.

### 🧑‍💻 Code

```python
import math

def jump_search(nums, x):
    n = len(nums)
    step = int(math.sqrt(n))
    prev = 0

    while prev < n and nums[min(step, n) - 1] < x:
        prev = step
        step += int(math.sqrt(n))
        if prev >= n:
            return False

    for i in range(prev, min(step, n)):
        if nums[i] == x:
            return True

    return False
```

### ⏱️ Complexity

* **Time:** O(√n)
* **Space:** O(1)

🟡 Rare, but good for algorithm discussions.

---

## 🧩 Approach 5 — Exponential Search

### 💡 Idea

* Find range where target may exist
* Apply binary search inside that range

Efficient for **unbounded or infinite arrays**.

### 🧑‍💻 Code

```python
def exponential_search(nums, x):
    if not nums:
        return False

    if nums[0] == x:
        return True

    i = 1
    while i < len(nums) and nums[i] <= x:
        i *= 2

    return binary_search(nums[:i], x)
```

### ⏱️ Complexity

* **Time:** O(log n)
* **Space:** O(1)

🟢 Common in system-level interviews.

---

## 🧩 Approach 6 — Hash Set Search (Fast Lookup)

### 💡 Idea

Convert the array into a set for **O(1) average lookup**.

### 🧑‍💻 Code

```python
def hash_search(nums, x):
    lookup = set(nums)
    return x in lookup
```

### ⏱️ Complexity

* **Time:** O(n) preprocessing, O(1) lookup
* **Space:** O(n)

🟢 Excellent when **many searches** are needed.

---

## 🎯 Choosing the Right Search Algorithm

| Scenario              | Best Choice          |
| --------------------- | -------------------- |
| Unsorted array        | Linear Search        |
| Sorted array          | Binary Search        |
| Many queries          | Hash Set             |
| Very large data       | Binary / Exponential |
| Teaching fundamentals | Linear / Binary      |

---

## 🧠 Final Interview Tip

> Always ask:
>
> * Is the data sorted?
> * How many queries?
> * Is extra memory allowed?

Answering these **before coding** is what impresses interviewers.

---

## 🏁 Takeaway

Searching is not about speed alone.
It’s about **choosing the right strategy under constraints**.

If you master these, **binary search variations will feel easy** 🚀