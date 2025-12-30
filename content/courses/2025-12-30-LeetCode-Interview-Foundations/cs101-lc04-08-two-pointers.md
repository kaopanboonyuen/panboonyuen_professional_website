---
title: LC-TEST-08 — Two Pointers in the Wild
weight: 80
date: '2025-12-30'
type: book
---

<!--more-->

## 🎯 Why Two Pointers Matter

Two pointers is not a trick.  
It is a **way of thinking**.

Strong developers see:
> “I don’t need extra memory.  
> I can let indices move and converge.”

This technique appears everywhere:
- Arrays
- Strings
- Sorted data
- Geometry problems
- Optimization tasks

If you master this, **your code gets shorter immediately**.

---

## 🧠 What You Will Learn

In this lesson, you will train to:

- Use **left / right pointers confidently**
- Decide **who moves and why**
- Avoid nested loops
- Reduce O(n²) → O(n)

This is **interview-critical muscle memory**.

---

## 🧩 Core Example — Container With Most Water

### Problem Statement

Given `n` non-negative integers representing vertical lines,
find two lines that together with the x-axis form a container
that holds the **most water**.

---

## 📥 Sample Input / 📤 Output

| height | Output |
|------|------|
| [1,8,6,2,5,4,8,3,7] | 49 |

---

## 🧠 Interviewer Insight

> ❗ Interviewers want to see:
>
> - Do you understand **why one pointer moves**
> - Can you explain **why brute force is wasteful**
> - Do you trust a greedy decision?

If you randomly move pointers, you fail.
If you **justify movement**, you pass.

---

## 🧩 Brute Force (What NOT To Do)

```python
max_area = 0
for i in range(len(height)):
    for j in range(i + 1, len(height)):
        max_area = max(
            max_area,
            min(height[i], height[j]) * (j - i)
        )
````

⛔ O(n²)
⛔ Interview red flag

---

## 🧩 Two Pointer Strategy (Correct)

### 💡 Core Insight

The **shorter line** limits the area.

So:

* Move the pointer pointing to the **shorter height**
* Because moving the taller one **cannot increase area**

This is the entire trick.

---

## 🧑‍💻 Two Pointer Solution

```python
def maxArea(height):
    left, right = 0, len(height) - 1
    best = 0

    while left < right:
        width = right - left
        area = min(height[left], height[right]) * width
        best = max(best, area)

        if height[left] < height[right]:
            left += 1
        else:
            right -= 1

    return best
```

---

## ⏱️ Complexity

* **Time:** O(n)
* **Space:** O(1)

Optimal.

---

## 🧠 Two Pointer Patterns You Must Recognize

| Pattern          | Example               |
| ---------------- | --------------------- |
| Opposite ends    | Container, Palindrome |
| Same direction   | Remove duplicates     |
| Meet in middle   | Pair sum              |
| Shrinking window | Valid palindrome      |

---

## 🎯 Final Takeaway

> Two pointers is about **controlled movement**, not guessing.

If you can explain **why** a pointer moves,
interviewers assume you understand **algorithmic reasoning**.

---

## 🏁 Practice Targets

* Valid Palindrome
* Two Sum II (sorted)
* Remove Duplicates
* 3Sum
* Squares of a Sorted Array

Master these → you look *dangerous* in interviews 😈