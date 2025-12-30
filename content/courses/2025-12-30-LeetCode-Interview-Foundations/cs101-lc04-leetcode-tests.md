---
title: CS101-LC04 — LeetCode Practice 🧪
weight: 40
type: book
---

<!--more-->

## 🧩 LC-TEST-01 Sorting

**Question**: Sort an integer array.

**Input**
```
[3,1,2]
```

**Output**
```
[1,2,3]
```

{{< spoiler text="Solution (Python)" >}}
```python
def sort_array(nums):
    return sorted(nums)  # Timsort: O(n log n)
```
{{< /spoiler >}}

---

## 🧮 LC-TEST-02 Prime Number

**Question**: Check if n is prime.

{{< spoiler text="Solution" >}}
```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
```
{{< /spoiler >}}

---

## 🍬 LC-TEST-03 Candy (Greedy)

{{< spoiler text="Idea" >}}
Use two passes (left → right, right → left)
{{< /spoiler >}}
