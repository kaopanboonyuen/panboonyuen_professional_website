---
title: LC-TEST-01 — Sorting an Array
weight: 40
type: book
---

<!--more-->

## 🧩 Problem Statement

Given an integer array `nums`, return the array sorted in **ascending order**.

This problem looks simple, but interviewers often use it to evaluate:

- Your understanding of **algorithmic trade-offs**
- Your knowledge of **time vs space complexity**
- Whether you know **when NOT to use built-in functions**

---

## 📥 Sample Input / 📤 Output

| Input | Output |
|------|--------|
| [3, 1, 2] | [1, 2, 3] |
| [5, 4, 3, 2, 1] | [1, 2, 3, 4, 5] |
| [1] | [1] |
| [] | [] |
| [2, 2, 1] | [1, 2, 2] |

---

## 🧠 Interviewer Insight (Read This First)

> ❗ **Important:**  
> In real interviews, the question is **not** “Can you sort an array?”  
> It is:
>
> - Which sorting algorithm do you choose?
> - Why is it optimal **for this scenario**?
> - What are the time & space trade-offs?

Below we show **all major sorting algorithms** with **clear intuition**.

---

## ✅ Approach 1 — Python Built-in Sort (Recommended in Practice)

### 💡 Idea

Python uses **Timsort**, a hybrid of:
- Merge Sort
- Insertion Sort

It is:
- Stable
- Extremely fast in real-world data
- Optimized for partially sorted arrays

### 🧑‍💻 Code

```python
def sort_array(nums):
    # Python's built-in sort uses Timsort
    return sorted(nums)
````

### ⏱️ Complexity

* **Time:** O(n log n)
* **Space:** O(n)

🟢 **Use this in interviews unless explicitly forbidden.**

---

## 🧩 Approach 2 — Bubble Sort (Educational Only)

### 💡 Idea

Repeatedly swap adjacent elements if they are in the wrong order.

Think of large numbers **“bubbling up”** to the end.

### 🧑‍💻 Code

```python
def bubble_sort(nums):
    n = len(nums)
    for i in range(n):
        for j in range(0, n - i - 1):
            if nums[j] > nums[j + 1]:
                nums[j], nums[j + 1] = nums[j + 1], nums[j]
    return nums
```

### ⏱️ Complexity

* **Time:** O(n²)
* **Space:** O(1)

🔴 Rarely used in practice, but good for teaching basics.

---

## 🧩 Approach 3 — Selection Sort

### 💡 Idea

Repeatedly find the **minimum element** and move it to the front.

### 🧑‍💻 Code

```python
def selection_sort(nums):
    n = len(nums)
    for i in range(n):
        min_idx = i
        for j in range(i + 1, n):
            if nums[j] < nums[min_idx]:
                min_idx = j
        nums[i], nums[min_idx] = nums[min_idx], nums[i]
    return nums
```

### ⏱️ Complexity

* **Time:** O(n²)
* **Space:** O(1)

🟡 Simple but inefficient for large data.

---

## 🧩 Approach 4 — Insertion Sort

### 💡 Idea

Build the sorted array **one element at a time**, similar to sorting playing cards.

Very efficient for **nearly sorted arrays**.

### 🧑‍💻 Code

```python
def insertion_sort(nums):
    for i in range(1, len(nums)):
        key = nums[i]
        j = i - 1
        while j >= 0 and nums[j] > key:
            nums[j + 1] = nums[j]
            j -= 1
        nums[j + 1] = key
    return nums
```

### ⏱️ Complexity

* **Time:** O(n²) worst case, **O(n)** best case
* **Space:** O(1)

🟢 Excellent when data is almost sorted.

---

## 🧩 Approach 5 — Merge Sort (Divide & Conquer)

### 💡 Idea

* Divide the array into halves
* Sort each half
* Merge them back together

### 🧑‍💻 Code

```python
def merge_sort(nums):
    if len(nums) <= 1:
        return nums

    mid = len(nums) // 2
    left = merge_sort(nums[:mid])
    right = merge_sort(nums[mid:])

    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])
    return result
```

### ⏱️ Complexity

* **Time:** O(n log n)
* **Space:** O(n)

🟢 Very popular in interviews.

---

## 🧩 Approach 6 — Quick Sort (Average Fastest)

### 💡 Idea

* Pick a pivot
* Partition elements into smaller & larger
* Recursively sort

### 🧑‍💻 Code

```python
def quick_sort(nums):
    if len(nums) <= 1:
        return nums

    pivot = nums[len(nums) // 2]
    left = [x for x in nums if x < pivot]
    middle = [x for x in nums if x == pivot]
    right = [x for x in nums if x > pivot]

    return quick_sort(left) + middle + quick_sort(right)
```

### ⏱️ Complexity

* **Time:** O(n log n) average, O(n²) worst
* **Space:** O(n)

🟢 Very fast in practice, but discuss worst case.

---

## 🎯 Final Interview Advice

| Situation              | Best Choice        |
| ---------------------- | ------------------ |
| Real-world code        | `sorted()`         |
| Teaching / basics      | Bubble / Selection |
| Nearly sorted data     | Insertion Sort     |
| Guaranteed performance | Merge Sort         |
| Average fastest        | Quick Sort         |

> 💬 **Interview Tip:**
> Always say *why* you choose an algorithm, not just *how*.

---

## 🧠 Takeaway

Sorting is not about memorizing code.
It’s about **choosing the right tool for the problem**.

This single question can separate:

* Junior developers
* From **strong algorithmic thinkers** 🚀