---
title: "Lecture 02 — Python: The Language of AI"
date: "2025-12-30"
type: book
weight: 20
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~2–3 hours (core recap lecture)

---

## 🐍 Why Python?

Python is the **language of thinking** for AI and algorithms.

It is used in:
- 🤖 Artificial Intelligence
- 📊 Data Science
- 🧠 Research & prototyping
- 🧩 Coding interviews (LeetCode, Google, Meta)

> If you know Python well, you can think clearly.

---

## 🧠 Mental Model (IMPORTANT)

Before syntax, remember this:

> **Python executes line by line, top to bottom.**  
> Variables point to objects.  
> Everything is an object.

This mental model helps you avoid 80% of bugs.

---

## 1️⃣ Variables & Data Types

### 📦 Variables

```python
x = 10
name = "AI"
pi = 3.14
is_active = True
````

Python is **dynamically typed**:

```python
x = 10
x = "now a string"
```

### 🔢 Core Data Types

| Type  | Example         |
| ----- | --------------- |
| int   | `10`            |
| float | `3.14`          |
| str   | `"hello"`       |
| bool  | `True`, `False` |
| None  | `None`          |

### ❓ Quiz

{{< spoiler text="Is Python statically typed?" >}}
No. Python is dynamically typed.
{{< /spoiler >}}

---

## 2️⃣ Control Flow (if / else)

```python
x = 5

if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

### 🧠 Interview Tip

Indentation **is logic** in Python.

### ❓ Quiz

{{< spoiler text="What happens if indentation is wrong?" >}}
The program raises an IndentationError or behaves incorrectly.
{{< /spoiler >}}

---

## 3️⃣ Loops (for / while)

### 🔁 for-loop (most common)

```python
for i in range(5):
    print(i)
```

### 🔄 while-loop

```python
count = 0
while count < 3:
    print(count)
    count += 1
```

### 🧠 Interview Tip

Use `for` unless you *must* use `while`.

### ❓ Quiz

{{< spoiler text="When is while-loop dangerous?" >}}
When the stopping condition is incorrect → infinite loop.
{{< /spoiler >}}

---

## 4️⃣ Lists (Most Important for LeetCode)

```python
nums = [1, 2, 3, 4]
```

### Common operations

```python
nums.append(5)
nums.pop()
nums[0]
nums[-1]
len(nums)
```

### Looping over list

```python
for n in nums:
    print(n)
```

### With index

```python
for i, n in enumerate(nums):
    print(i, n)
```

### ❓ Quiz

{{< spoiler text="What is the time complexity of list append?" >}}
Amortized O(1)
{{< /spoiler >}}

---

## 5️⃣ Strings (Text = Sequence)

```python
s = "machine"
```

Strings behave like lists:

```python
s[0]        # 'm'
s[-1]       # 'e'
s[1:4]      # 'ach'
```

### Useful methods

```python
s.lower()
s.upper()
s.split()
```

### ❓ Quiz

{{< spoiler text="Are strings mutable?" >}}
No. Strings are immutable.
{{< /spoiler >}}

---

## 6️⃣ Dictionaries (Key–Value Thinking)

```python
student = {
    "name": "Kao",
    "age": 25,
    "major": "AI"
}
```

### Access

```python
student["name"]
student.get("age")
```

### Loop

```python
for key, value in student.items():
    print(key, value)
```

### 🧠 Interview Tip

Dictionaries give **O(1)** average lookup.

### ❓ Quiz

{{< spoiler text="Why are dictionaries powerful?" >}}
Fast lookup using hashing.
{{< /spoiler >}}

---

## 7️⃣ Sets (Uniqueness)

```python
nums = [1, 2, 2, 3]
unique = set(nums)
```

### Use cases

* Remove duplicates
* Fast membership check

```python
if 3 in unique:
    print("Found")
```

### ❓ Quiz

{{< spoiler text="Does a set preserve order?" >}}
No.
{{< /spoiler >}}

---

## 8️⃣ Functions (Reusable Thinking)

```python
def add(a, b):
    return a + b
```

### Default arguments

```python
def greet(name="AI"):
    print("Hello", name)
```

### ❓ Quiz

{{< spoiler text="Why use functions?" >}}
Abstraction, reuse, clarity.
{{< /spoiler >}}

---

## 9️⃣ Common Built-ins (LeetCode Gold)

```python
len()
sum()
min()
max()
sorted()
range()
```

Example:

```python
nums = [3, 1, 2]
sorted(nums)
```

---

## 🔟 Time Complexity Awareness (VERY IMPORTANT)

| Operation   | Typical Cost |
| ----------- | ------------ |
| List access | O(1)         |
| Dict lookup | O(1)         |
| List search | O(n)         |
| Sorting     | O(n log n)   |

> Python coding interviews are **algorithm interviews**, not syntax tests.

---

## 🧠 Python for AI Mindset

Python is:

* 🧩 How we express logic
* 🧠 How we describe algorithms
* 🤖 How we talk to machines

> Clean Python = Clear Thinking

---