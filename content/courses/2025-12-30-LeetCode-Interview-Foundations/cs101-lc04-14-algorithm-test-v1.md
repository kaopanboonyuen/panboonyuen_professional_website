---
title: LC-TEST-14 — Algorithm Test (V1)
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Document Exists

This is **not** a LeetCode solution dump.

This is a **real-world algorithm thinking gym**.

You will train:
- 🧠 Problem decomposition
- 📊 Data processing at scale
- ⏱ Time & space complexity awareness
- 🔁 Iteration, recursion, sliding windows
- 🧮 Hash maps, sets, heaps, stacks
- 🧵 Real production-like constraints

Inspired by **Google, AWS, Microsoft, OpenAI interviews**.

---

# 🏆 Python Logic Olympics — Real World Edition (20 Problems)

Difficulty increases **gradually**.
**Do not open solutions too early.**

---

## 🟢 Problem 1 — Log Entry Counter (Warm-Up)

You receive API logs per minute:

```python
logs = [12, 0, 7, 3, 9, 0, 15]
````

Each number represents requests in that minute.

**Task:**
Count the **total number of requests** without using `sum()`.

<details>
<summary>✅ Solution</summary>

```python
total = 0
for x in logs:
    total += x
print(total)
```

</details>

---

## 🟢 Problem 2 — Healthy Server Detection

Each server sends a heartbeat signal:

```python
heartbeat = [True, True, False, True, True]
```

A server is **healthy** only if **no False exists**.

**Task:**
Return `True` if the system is healthy, else `False`.

<details>
<summary>✅ Solution</summary>

```python
healthy = True
for h in heartbeat:
    if not h:
        healthy = False
        break
print(healthy)
```

</details>

---

## 🟢 Problem 3 — Unique User IDs

User login stream:

```python
users = [101, 203, 101, 405, 203, 999]
```

**Task:**
Return the **number of unique users**.

<details>
<summary>✅ Solution</summary>

```python
unique = set()
for u in users:
    unique.add(u)
print(len(unique))
```

</details>

---

## 🟡 Problem 4 — First Repeated Transaction

Transactions arrive in order:

```python
tx = ["A12", "B33", "C90", "B33", "D10"]
```

**Task:**
Return the **first repeated transaction ID**.

<details>
<summary>✅ Solution</summary>

```python
seen = set()
for t in tx:
    if t in seen:
        print(t)
        break
    seen.add(t)
```

</details>

---

## 🟡 Problem 5 — Sliding Window CPU Alert

CPU usage per second:

```python
cpu = [40, 60, 80, 90, 30, 20, 85]
```

**Task:**
Detect if **any 3 consecutive seconds** exceed **200 total usage**.

<details>
<summary>✅ Solution</summary>

```python
for i in range(len(cpu) - 2):
    if cpu[i] + cpu[i+1] + cpu[i+2] > 200:
        print(True)
        break
else:
    print(False)
```

</details>

---

## 🟡 Problem 6 — Rate Limiter

Requests arrive with timestamps (seconds):

```python
requests = [1, 1, 1, 2, 2, 3, 10]
```

**Rule:** Max **3 requests per second**.

**Task:**
Return timestamps that violate the rule.

<details>
<summary>✅ Solution</summary>

```python
from collections import defaultdict

count = defaultdict(int)
violations = []

for r in requests:
    count[r] += 1
    if count[r] > 3:
        violations.append(r)

print(violations)
```

</details>

---

## 🟡 Problem 7 — Most Frequent Error Code

System errors:

```python
errors = [500, 404, 500, 403, 404, 500]
```

**Task:**
Return the **most frequent error code**.

<details>
<summary>✅ Solution</summary>

```python
freq = {}
for e in errors:
    freq[e] = freq.get(e, 0) + 1

print(max(freq, key=freq.get))
```

</details>

---

## 🟡 Problem 8 — Data Chunking

Large dataset needs batching:

```python
data = list(range(10))
batch_size = 3
```

**Task:**
Split data into batches of size `batch_size`.

<details>
<summary>✅ Solution</summary>

```python
batches = []
for i in range(0, len(data), batch_size):
    batches.append(data[i:i+batch_size])
print(batches)
```

</details>

---

## 🔵 Problem 9 — Valid JSON Brackets

Incoming JSON stream (simplified):

```python
s = "{[()()]}"
```

**Task:**
Check if brackets are valid.

<details>
<summary>✅ Solution</summary>

```python
stack = []
pairs = {')':'(', ']':'[', '}':'{'}

for c in s:
    if c in '([{':
        stack.append(c)
    else:
        if not stack or stack.pop() != pairs[c]:
            print(False)
            break
else:
    print(len(stack) == 0)
```

</details>

---

## 🔵 Problem 10 — Longest Continuous Uptime

Service status:

```python
status = [1,1,0,1,1,1,0,1]
```

`1 = up`, `0 = down`

**Task:**
Find longest continuous uptime.

<details>
<summary>✅ Solution</summary>

```python
max_up = cur = 0
for s in status:
    if s == 1:
        cur += 1
        max_up = max(max_up, cur)
    else:
        cur = 0
print(max_up)
```

</details>

---

## 🔵 Problem 11 — Merge Sorted Event Streams

```python
a = [1,3,5]
b = [2,4,6]
```

**Task:**
Merge into sorted order **without sort()**.

<details>
<summary>✅ Solution</summary>

```python
i = j = 0
res = []

while i < len(a) and j < len(b):
    if a[i] < b[j]:
        res.append(a[i]); i += 1
    else:
        res.append(b[j]); j += 1

res.extend(a[i:])
res.extend(b[j:])
print(res)
```

</details>

---

## 🔵 Problem 12 — Anomaly Score Detection

```python
scores = [10, 12, 11, 50, 13]
```

**Rule:**
An anomaly is > **2× average**.

<details>
<summary>✅ Solution</summary>

```python
avg = sum(scores) / len(scores)
print([x for x in scores if x > 2 * avg])
```

</details>

---

## 🔴 Problem 13 — LRU Cache Simulation

Capacity = 2
Access pattern:

```python
access = ["A","B","A","C","B"]
```

**Task:**
Simulate LRU eviction.

<details>
<summary>✅ Solution</summary>

```python
cache = []
cap = 2

for x in access:
    if x in cache:
        cache.remove(x)
    elif len(cache) == cap:
        cache.pop(0)
    cache.append(x)

print(cache)
```

</details>

---

## 🔴 Problem 14 — Top-K Frequent Events

```python
events = ["login","pay","login","logout","login","pay"]
k = 2
```

<details>
<summary>✅ Solution</summary>

```python
from collections import Counter
print([x for x,_ in Counter(events).most_common(k)])
```

</details>

---

## 🔴 Problem 15 — Shortest Error Window

```python
logs = ["OK","ERR","OK","ERR","ERR","OK"]
```

**Task:**
Smallest subarray containing **2 ERR**.

<details>
<summary>✅ Solution</summary>

```python
left = 0
err = 0
best = float("inf")

for right in range(len(logs)):
    if logs[right] == "ERR":
        err += 1
    while err >= 2:
        best = min(best, right - left + 1)
        if logs[left] == "ERR":
            err -= 1
        left += 1

print(best)
```

</details>

---

## 🔴 Problem 16 — Task Scheduling (Greedy)

Tasks with deadlines:

```python
tasks = [(3,10),(1,5),(2,7)]
```

(duration, deadline)

<details>
<summary>✅ Solution</summary>

```python
tasks.sort(key=lambda x: x[1])
time = 0

for d, dead in tasks:
    time += d
    if time > dead:
        print(False)
        break
else:
    print(True)
```

</details>

---

## 🔴 Problem 17 — Dependency Resolution (Graph)

```python
deps = {"A":["B"],"B":["C"],"C":[]}
```

Detect cycles.

<details>
<summary>✅ Solution</summary>

```python
vis = set()
path = set()

def dfs(n):
    if n in path: return True
    if n in vis: return False
    path.add(n)
    for nei in deps[n]:
        if dfs(nei): return True
    path.remove(n)
    vis.add(n)
    return False

print(any(dfs(x) for x in deps))
```

</details>

---

## 🔴 Problem 18 — API Burst Detection

Requests timestamps:

```python
t = [1,2,3,3,3,3,4]
```

Burst = 4 in same second.

<details>
<summary>✅ Solution</summary>

```python
from collections import Counter
print(any(v >= 4 for v in Counter(t).values()))
```

</details>

---

## 🔴 Problem 19 — Median of Data Stream

Stream:

```python
nums = [5,15,1,3]
```

<details>
<summary>✅ Solution</summary>

```python
import heapq
low, high = [], []

for n in nums:
    heapq.heappush(low, -n)
    heapq.heappush(high, -heapq.heappop(low))
    if len(high) > len(low):
        heapq.heappush(low, -heapq.heappop(high))

    if len(low) > len(high):
        print(-low[0])
    else:
        print((-low[0] + high[0]) / 2)
```

</details>

---

## 🔴 Problem 20 — Distributed Log Consistency

Multiple replicas send logs:

```python
replicas = [
  ["A","B","C"],
  ["A","C"],
  ["A","B","C","D"]
]
```

**Task:**
Find logs present in **all replicas**.

<details>
<summary>✅ Solution</summary>

```python
common = set(replicas[0])
for r in replicas[1:]:
    common &= set(r)
print(list(common))
```

</details>

---

## 🎯 Final Advice

If you can **explain these aloud**:

* You can pass **FAANG Python interviews**
* You understand **real engineering logic**
* You are no longer memorizing — you are **thinking**

---