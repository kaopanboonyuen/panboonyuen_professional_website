---
title: LC-TEST-15 — Algorithm Test (V2)
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Document Exists

This is **not** about memorizing tricks.

This is about learning how **real engineers think** at:
- Google
- AWS
- OpenAI
- Microsoft

You will practice:
- 🧠 Algorithmic thinking
- 🧱 Data structures
- ⚙️ Python internals
- 🚦 Edge cases
- 📊 Real-world constraints

---

# 🧠 Python Algorithm Thinking — 20 Real-World Puzzles

Difficulty increases gradually.  
**Do not open solutions too early.**

---

## 🟢 Puzzle 1 — API Request Counter

A server receives API calls per minute:

```python
requests = [120, 98, 135, 102, 87]
```

**Task:**  
Calculate the total number of requests **without using `sum()`**.

<details>
<summary>✅ Solution</summary>

```python
total = 0
for r in requests:
    total += r
print(total)
```

</details>

---

## 🟢 Puzzle 2 — Log Error Filter

System logs:

```python
logs = ["INFO", "ERROR", "INFO", "WARN", "ERROR"]
```

**Task:**  
Return how many `"ERROR"` logs exist.

<details>
<summary>✅ Solution</summary>

```python
count = 0
for log in logs:
    if log == "ERROR":
        count += 1
print(count)
```

</details>

---

## 🟢 Puzzle 3 — User ID Deduplication

User IDs arriving from multiple services:

```python
ids = [101, 102, 101, 103, 102, 104]
```

**Task:**  
Return **unique IDs** while preserving order.

<details>
<summary>✅ Solution</summary>

```python
seen = set()
result = []

for i in ids:
    if i not in seen:
        seen.add(i)
        result.append(i)

print(result)
```

</details>

---

## 🟢 Puzzle 4 — Rate Limit Trigger

Requests per second:

```python
traffic = [3, 5, 7, 12, 4, 15, 6]
```

**Task:**  
Return all values **above 10**.

<details>
<summary>✅ Solution</summary>

```python
result = []
for t in traffic:
    if t > 10:
        result.append(t)
print(result)
```

</details>

---

## 🟡 Puzzle 5 — First Non-Repeating Event

Event stream:

```python
events = ["A", "B", "A", "C", "B", "D"]
```

**Task:**  
Return the **first event that appears only once**.

<details>
<summary>✅ Solution</summary>

```python
from collections import Counter

counts = Counter(events)
for e in events:
    if counts[e] == 1:
        print(e)
        break
```

</details>

---

## 🟡 Puzzle 6 — Sliding Window CPU Average

CPU usage over time:

```python
cpu = [20, 30, 50, 40, 60, 70]
```

**Task:**  
Return the **maximum average of any window of size 3**.

<details>
<summary>✅ Solution</summary>

```python
max_avg = 0
for i in range(len(cpu) - 2):
    avg = (cpu[i] + cpu[i+1] + cpu[i+2]) / 3
    max_avg = max(max_avg, avg)

print(max_avg)
```

</details>

---

## 🟡 Puzzle 7 — Password Strength Validator

Rules:
- ≥ 8 chars
- at least 1 digit
- at least 1 uppercase

**Task:**  
Return `True / False` for a password.

<details>
<summary>✅ Solution</summary>

```python
def strong(p):
    return (
        len(p) >= 8 and
        any(c.isdigit() for c in p) and
        any(c.isupper() for c in p)
    )

print(strong("Pass1234"))
```

</details>

---

## 🟡 Puzzle 8 — API Retry Simulator

Retry delays:

```python
delays = [1, 2, 4, 8, 16]
```

**Task:**  
Return cumulative wait time.

<details>
<summary>✅ Solution</summary>

```python
total = 0
for d in delays:
    total += d
print(total)
```

</details>

---

## 🟡 Puzzle 9 — Time-Based Key Store

Operations:

```python
ops = [("set","a",1),("set","a",2),("get","a")]
```

**Task:**  
Return latest value for `"a"`.

<details>
<summary>✅ Solution</summary>

```python
store = {}
for op in ops:
    if op[0] == "set":
        store[op[1]] = op[2]

print(store["a"])
```

</details>

---

## 🔵 Puzzle 10 — Merge Sorted Logs

```python
a = [1,4,7]
b = [2,3,6]
```

**Task:**  
Merge into one sorted list.

<details>
<summary>✅ Solution</summary>

```python
i = j = 0
result = []

while i < len(a) and j < len(b):
    if a[i] < b[j]:
        result.append(a[i])
        i += 1
    else:
        result.append(b[j])
        j += 1

result.extend(a[i:])
result.extend(b[j:])
print(result)
```

</details>

---

## 🔵 Puzzle 11 — Detect Configuration Drift

```python
expected = {"cpu":4,"ram":16}
actual = {"cpu":8,"ram":16}
```

**Task:**  
Return keys that differ.

<details>
<summary>✅ Solution</summary>

```python
diff = []
for k in expected:
    if expected[k] != actual.get(k):
        diff.append(k)

print(diff)
```

</details>

---

## 🔵 Puzzle 12 — Circular Queue Overflow

Queue size = 3  
Operations:

```python
ops = ["push","push","push","push"]
```

**Task:**  
Detect overflow.

<details>
<summary>✅ Solution</summary>

```python
size = 3
count = 0

for op in ops:
    if op == "push":
        count += 1
        if count > size:
            print("Overflow")
            break
```

</details>

---

## 🔵 Puzzle 13 — Longest Stable Network Period

Latency data:

```python
latency = [20,22,21,50,51,20,21]
```

**Task:**  
Longest subarray where difference ≤ 2.

<details>
<summary>✅ Solution</summary>

```python
max_len = 1
start = 0

for end in range(len(latency)):
    if abs(latency[end] - latency[start]) > 2:
        start = end
    max_len = max(max_len, end - start + 1)

print(max_len)
```

</details>

---

## 🔴 Puzzle 14 — Deadlock Detection (Graph)

Edges:

```python
edges = {"A":["B"],"B":["C"],"C":["A"]}
```

**Task:**  
Detect cycle.

<details>
<summary>✅ Solution</summary>

```python
visited = set()
stack = set()

def dfs(n):
    if n in stack:
        return True
    if n in visited:
        return False
    visited.add(n)
    stack.add(n)
    for nei in edges.get(n,[]):
        if dfs(nei):
            return True
    stack.remove(n)
    return False

print(any(dfs(n) for n in edges))
```

</details>

---

## 🔴 Puzzle 15 — Token Bucket Rate Limiter

Capacity = 5  
Requests = 7

**Task:**  
Allow or reject.

<details>
<summary>✅ Solution</summary>

```python
tokens = 5
for i in range(7):
    if tokens > 0:
        tokens -= 1
        print("Allowed")
    else:
        print("Rejected")
```

</details>

---

## 🔴 Puzzle 16 — LRU Cache (Core Idea)

**Task:**  
Evict least recently used key.

<details>
<summary>✅ Solution</summary>

```python
from collections import OrderedDict

cache = OrderedDict()
cache["a"] = 1
cache["b"] = 2
cache.move_to_end("a")
cache.popitem(last=False)
print(cache)
```

</details>

---

## 🔴 Puzzle 17 — Distributed ID Generator

**Task:**  
Ensure uniqueness.

<details>
<summary>✅ Solution</summary>

```python
import time

def gen():
    return int(time.time() * 1000)

print(gen())
```

</details>

---

## 🔴 Puzzle 18 — Batch Job Scheduler

Jobs with durations:

```python
jobs = [3,1,2]
```

**Task:**  
Minimize total wait time.

<details>
<summary>✅ Solution</summary>

```python
jobs.sort()
time = 0
total = 0
for j in jobs:
    total += time
    time += j
print(total)
```

</details>

---

## 🔴 Puzzle 19 — Model Version Rollback

Versions:

```python
versions = [1,2,3,4,3,2]
```

**Task:**  
Detect rollback.

<details>
<summary>✅ Solution</summary>

```python
for i in range(1,len(versions)):
    if versions[i] < versions[i-1]:
        print("Rollback detected")
        break
```

</details>

---

## 🟣 Puzzle 20 — System Design Thinking

**Task:**  
Explain (no code):  
How would you design **a rate-limited, cached, fault-tolerant API**?

<details>
<summary>✅ Solution</summary>

Key ideas:
- Load balancer
- Rate limiter
- Cache (Redis)
- Retry + circuit breaker
- Monitoring

</details>

---

## 🏁 Final Thought

If you can **solve + explain** these,
you are thinking like a **real Python engineer** — not a tutorial follower.

Teach others.
Make the world better.

---