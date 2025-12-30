---
title: LC-TEST-06 — Probability for Machine Learning
weight: 80
type: book
---

<!--more-->

## 🎯 Why Probability Matters

Probability is everywhere in AI:
- Model uncertainty
- Classification confidence
- Loss functions
- Bayesian thinking

Interviewers want **intuition**, not formulas only.

---

## 🧮 Basic Definitions

### Probability

Example:
```python
P(head) = 1 / 2
````

---

## 🎲 Conditional Probability

Example:

> Given it rains, what’s the chance traffic is heavy?

---

## 🔁 Independence

Two events are independent if:
[
P(A \cap B) = P(A)P(B)
]

Interview trick question ⚠️
👉 Independence ≠ no correlation always

---

## 🧠 Bayes’ Theorem (VERY IMPORTANT)

Used in:

* Spam detection
* Medical diagnosis
* Bayesian ML

---

## 🧪 Interview Question

> Why Naive Bayes works despite false independence assumptions?

✅ Because it reduces variance and scales well.

---

## 🏁 Takeaway

> Probability gives AI **confidence**, not just predictions.

---

# 📘 Gradient Descent (Interview Intuition)

## 🎯 Problem

How do machines **learn**?

By minimizing a loss function.

---

## 📉 Loss Function

---

## 🧠 Gradient Descent Idea

> Walk downhill in the direction of **steepest descent**

---

## 🧑‍💻 Python Example

```python
def gradient_descent(w, x, y, lr=0.01):
    grad = -2 * x * (y - w * x)
    return w - lr * grad
````

---

## ⏱️ Variants Interviewers Love

| Type       | Idea         |
| ---------- | ------------ |
| Batch GD   | Use all data |
| SGD        | One sample   |
| Mini-batch | Best of both |

---

## 🚨 Interview Trap

> Why not use a large learning rate?

❌ Overshooting
❌ Divergence

---

## 🏁 Takeaway

> Optimization is the **engine** of AI.

---

# 📘 NumPy for Coding Interviews

## 🎯 Why NumPy?

Interviewers expect:
- Vectorized thinking
- Clean math code
- Speed awareness

---

## 🧮 Arrays vs Lists

```python
import numpy as np

a = np.array([1, 2, 3])
````

Why better?

* Faster
* Cleaner
* Mathematical

---

## ➕ Vector Operations

```python
a + b        # element-wise
a * b
np.dot(a,b) # dot product
```

---

## 🧱 Matrix Multiplication

```python
A @ B
```

Equivalent to:

```python
np.matmul(A, B)
```

---

## 📏 Broadcasting (Interview Favorite)

```python
A + 1
```

Adds 1 to every element.

---

## 🏁 Takeaway

> NumPy replaces **loops with math**.

````

---

# Time vs Space Trade-offs

## 🎯 Interview Core Concept

You can optimize:
- Time
- Space

Rarely both.

---

## 🧩 Example: Duplicate Detection

### Less Space, More Time

```python
for i in range(n):
    for j in range(i+1, n):
        if nums[i] == nums[j]:
            return True
````

⏱️ O(n²), 💾 O(1)

---

### More Space, Less Time

```python
seen = set()
for v in nums:
    if v in seen:
        return True
    seen.add(v)
```

⏱️ O(n), 💾 O(n)

---

## 🧠 Interview Question

> Which would you choose?

Correct answer:

> Depends on constraints.

---

## 🏁 Takeaway

> Strong engineers trade **resources intentionally**.