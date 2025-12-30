---
title: LC-TEST-07 — Indexing & Containers Mastery
weight: 80
date: '2025-12-30'
type: book
---

<!--more-->

## 🎯 Why This Lesson Exists

When you watch strong developers solve LeetCode or interview problems, you’ll notice something:

> They don’t write long code.  
> They don’t explain much.  
> But their solution is **short, fast, and confident**.

The secret is **indexing** and **containers**.

They know:
- When to use **arrays vs lists**
- How to move pointers instead of copying data
- How to let **data structures do the hard work**

This lesson is about **thinking like them**.

---

## 🧠 What You Will Train Here

In this session, you will repeatedly practice:

- Index-based traversal (two pointers, ranges, windows)
- Containers: `list`, `dict`, `set`, `deque`
- Avoiding unnecessary loops
- Writing **contest-level, interview-ready code**

All problems here are **real LeetCode-style battlefield problems**.

---

## 🧩 Core Example — Text Justification

This problem looks long.
Many beginners panic.

Experienced devs see:
> “This is just indexing + container control.”

---

## 📘 Problem Statement — Text Justification

Given an array of strings `words` and an integer `maxWidth`, format the text so that:

- Each line has **exactly `maxWidth` characters**
- Text is **fully justified** (left and right)
- Extra spaces are distributed **as evenly as possible**
- If spaces do not divide evenly, **left gaps get more**
- The **last line** is left-justified

---

## 📥 Sample Input / 📤 Output

### Example

**Input**
```python
words = ["This", "is", "an", "example", "of", "text", "justification."]
maxWidth = 16
````

**Output**

```
[
  "This    is    an",
  "example  of text",
  "justification.  "
]
```

---

## 🧠 Interviewer Insight

> ❗ Interviewers are NOT testing formatting.
>
> They are testing:
>
> * Can you **group data using indices**?
> * Can you manage **ranges without slicing copies**?
> * Do you understand **greedy packing**?
> * Can you control spaces mathematically?

If you pass this problem cleanly,
they already trust your **data-structure instincts**.

---

## 🧩 Step 1 — Greedy Line Packing (Indexing)

### 💡 Idea

Use indexing to pack as many words as possible into one line.

We move a pointer `i` forward.
No recursion.
No backtracking.
No copying.

This is **pure index control**.

---

## 🧑‍💻 Core Packing Logic

```python
i = 0
n = len(words)

while i < n:
    line_len = len(words[i])
    j = i + 1

    while j < n and line_len + 1 + len(words[j]) <= maxWidth:
        line_len += 1 + len(words[j])
        j += 1
```

🟢 Notice:

* `i` and `j` define a **range**
* No new arrays are created
* This is how contest code stays fast

---

## 🧩 Step 2 — Space Distribution Using Containers

Once words `[i : j]` are fixed:

* Count total spaces needed
* Count gaps between words
* Distribute spaces using arithmetic

This avoids messy string operations.

---

## 🧑‍💻 Space Math (The Key Insight)

```python
num_words = j - i
total_spaces = maxWidth - sum(len(w) for w in words[i:j])
gaps = num_words - 1
```

Now we branch:

* **Last line OR single word** → left-justify
* Otherwise → fully justify

---

## 🧑‍💻 Full Justification Logic

```python
if j == n or gaps == 0:
    line = " ".join(words[i:j])
    line += " " * (maxWidth - len(line))
else:
    space, extra = divmod(total_spaces, gaps)
    line = ""

    for k in range(i, j - 1):
        line += words[k]
        line += " " * (space + (1 if extra > 0 else 0))
        extra -= 1

    line += words[j - 1]
```

🟢 This is where **containers + indexing shine**.

---

## ⏱️ Complexity Analysis

* **Time:** O(n)
* **Space:** O(1) extra (output excluded)

This is **optimal**.

---

## 🧠 Why This Problem Is Gold for Interviews

This single problem tests:

| Skill           | Tested |
| --------------- | ------ |
| Index traversal | ✅      |
| Greedy strategy | ✅      |
| Container usage | ✅      |
| Edge cases      | ✅      |
| Clean code      | ✅      |

If you solve this smoothly,
interviewers assume you can handle:

* Two pointers
* Sliding windows
* String manipulation
* Array partitioning

---

## 🔁 More Problems You Should Practice in This Style

To fully absorb indexing + containers, repeat this mindset on:

* Trapping Rain Water
* Container With Most Water
* Group Anagrams
* Minimum Window Substring
* Merge Intervals
* Rotate Image
* Spiral Matrix

Same idea.
Different skin.

---

## 🎯 Final Takeaway

> Strong developers don’t write clever code.
>
> They **let indices and containers think for them**.

If you master this lesson,
your LeetCode solutions will:

* Shrink in size
* Increase in clarity
* Feel *calm* under interview pressure

This is the level interviewers quietly hope for 🚀