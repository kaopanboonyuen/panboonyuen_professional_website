---
title: LC-TEST-09 — Sliding Window Like a Pro
weight: 80
date: '2025-12-30'
type: book
---

<!--more-->

## 🎯 Why Sliding Window Is a Game Changer

Sliding Window is what happens when:

> Two pointers learn to **cooperate**.

This technique is everywhere:

* Subarrays
* Substrings
* Streaming data
* Real-time analytics

Interviewers **love** this topic.

---

## 🧠 What You Will Learn

This lesson trains you to:

* Expand and shrink windows deliberately
* Track state using containers (`dict`, `set`)
* Replace nested loops with **one clean pass**
* Write code that looks **effortlessly smart**

---

## 🧩 Core Example — Minimum Window Substring

### Problem Statement

Given strings `s` and `t`, return the **minimum window in `s`**
that contains all characters of `t`.

If no such window exists, return `""`.

---

## 📥 Sample Input / 📤 Output

| s               | t     | Output |
| --------------- | ----- | ------ |
| "ADOBECODEBANC" | "ABC" | "BANC" |

---

## 🧠 Interviewer Insight

> ❗ This problem tests:
>
> * Can you **track frequencies**
> * Do you know when a window becomes valid
> * Can you shrink without breaking correctness

If you brute force substrings → instant fail.

---

## 🧩 Sliding Window Strategy

### 💡 Mental Model

* Right pointer **expands** the window
* Left pointer **shrinks** it
* A container tracks validity

Never reset.
Never restart loops.

---

## 🧑‍💻 Sliding Window Solution

```python
from collections import Counter

def minWindow(s, t):
    need = Counter(t)
    missing = len(t)
    left = start = end = 0

    for right, ch in enumerate(s, 1):
        if need[ch] > 0:
            missing -= 1
        need[ch] -= 1

        if missing == 0:
            while left < right and need[s[left]] < 0:
                need[s[left]] += 1
                left += 1

            if end == 0 or right - left < end - start:
                start, end = left, right

            need[s[left]] += 1
            missing += 1
            left += 1

    return s[start:end]
```

---

## ⏱️ Complexity

* **Time:** O(n)
* **Space:** O(k) (character set)

This is **optimal and interview-approved**.

---

## 🧠 Sliding Window Patterns

| Pattern          | Example                  |
| ---------------- | ------------------------ |
| Fixed window     | Max sum subarray         |
| Variable window  | Min window substring     |
| Frequency window | Anagrams                 |
| Set-based window | Longest unique substring |

---

## 🧩 Beginner vs Pro Thinking

**Beginner:**

> “Let me try all substrings.”

**Pro:**

> “I expand until valid, then shrink carefully.”

That mindset shift is what interviews test.

---

## 🎯 Final Takeaway

> Sliding Window is not hard.
>
> Restarting loops is.

If your window **never resets**,
your solution is probably correct.

---

## 🏁 Practice Targets

* Longest Substring Without Repeating Characters
* Permutation in String
* Max Consecutive Ones III
* Subarray Sum Equals K
* Find All Anagrams in a String

Master these → you officially **think like a LeetCode veteran** 🚀