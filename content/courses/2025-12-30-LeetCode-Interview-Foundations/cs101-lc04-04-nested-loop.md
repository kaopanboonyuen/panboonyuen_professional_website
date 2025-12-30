---
title: LC-TEST-04 — Nested Loops (Thinking Beyond O(n²))
weight: 70
type: book
---

<!--more-->

## 🧩 Problem Statement

Given an integer array `nums`, determine whether the array contains **any duplicate elements**.

Return `True` if **any value appears at least twice**, otherwise return `False`.

This problem intentionally encourages a **nested-loop solution first**, and then tests whether you understand:

- How nested loops scale
- When they become inefficient
- How to optimize them

---

## 📥 Sample Input / 📤 Output

| nums | Output |
|------|--------|
| [1, 2, 3, 1] | True |
| [1, 2, 3, 4] | False |
| [] | False |
| [5] | False |
| [2, 2, 2] | True |

---

## 🧠 Interviewer Insight

> ❗ Interviewers **expect** you to start with a nested loop.  
> What they really care about is:
>
> - Can you analyze the complexity?
> - Do you recognize inefficiency?
> - Can you improve it?

Let’s start from the **baseline**.

---

## 🧩 Approach 1 — Brute Force Nested Loop

### 💡 Idea

Compare **every pair of elements**.

If any two elements are equal → duplicate found.

### 🧑‍💻 Code

```python
def contains_duplicate(nums):
    n = len(nums)

    # Compare every pair (i, j)
    for i in range(n):
        for j in range(i + 1, n):
            if nums[i] == nums[j]:
                return True

    return False
````

### ⏱️ Complexity

* **Time:** O(n²)
* **Space:** O(1)

🟡 Correct but **does not scale** for large input.

---

## 🔍 Why Nested Loops Are Expensive

If:

* n = 1,000 → 1,000,000 comparisons
* n = 10,000 → 100,000,000 comparisons

> 🚨 This is why interviewers worry about nested loops.

---

## 🧩 Approach 2 — Early Exit Optimization

### 💡 Idea

Still use nested loops, but **short-circuit early** when a duplicate is found.

### 🧑‍💻 Code

```python
def contains_duplicate_early_exit(nums):
    n = len(nums)

    for i in range(n):
        for j in range(i + 1, n):
            if nums[i] == nums[j]:
                # Exit immediately once duplicate is found
                return True

    return False
```

### ⏱️ Complexity

* **Time:** O(n²) worst case
* **Space:** O(1)

🟡 Slight improvement, but still quadratic.

---

## 🧩 Approach 3 — Nested Loop with Sorting

### 💡 Idea

If we **sort first**, duplicates become adjacent.

Then we only need **one loop**.

### 🧑‍💻 Code

```python
def contains_duplicate_sort(nums):
    nums.sort()

    for i in range(1, len(nums)):
        if nums[i] == nums[i - 1]:
            return True

    return False
```

### ⏱️ Complexity

* **Time:** O(n log n)
* **Space:** O(1) (ignoring sort internals)

🟢 Great improvement — shows algorithmic thinking.

---

## 🧩 Approach 4 — Hash Set (Optimal)

### 💡 Idea

Use a set to **remember what we've seen**.

Avoid nested loops entirely.

### 🧑‍💻 Code

```python
def contains_duplicate_hash(nums):
    seen = set()

    for v in nums:
        if v in seen:
            return True
        seen.add(v)

    return False
```

### ⏱️ Complexity

* **Time:** O(n)
* **Space:** O(n)

🟢 This is the **best practical solution**.

---

## 🧠 Nested Loop Pattern (General Form)

Most nested-loop problems follow this shape:

```python
for i in range(n):
    for j in range(i + 1, n):
        # Compare or combine nums[i] and nums[j]
```

Typical problems:

* Pair comparison
* Duplicate detection
* Brute-force two-sum
* Matrix traversal

---

## 🎯 When Nested Loops Are ACCEPTABLE

| Scenario             | Acceptable? |
| -------------------- | ----------- |
| n ≤ 1,000            | ✅ Yes       |
| One-time computation | ✅ Yes       |
| Teaching logic       | ✅ Yes       |
| Large datasets       | ❌ No        |
| Performance-critical | ❌ No        |

---

## 🧠 Interview-Level Takeaway

> ❗ Nested loops are not “bad”.
> They are **a starting point**.

What impresses interviewers is when you say:

> “This works, but it’s O(n²). We can do better.”

---

## 🏁 Final Advice

If you master nested loops:

* You understand **brute force**
* You understand **optimization paths**
* You understand **why better algorithms exist**

That’s the mindset of a **strong programmer**, not just a coder 🚀