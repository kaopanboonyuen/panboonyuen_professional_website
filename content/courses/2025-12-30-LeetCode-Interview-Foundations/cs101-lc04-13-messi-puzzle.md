---
title: LC-TEST-13 — Messi Puzzle
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Document Exists

This is **not** a LeetCode cheat list.

This is a **thinking gym**.

You will train:
- 🧠 Logic
- 🔁 Loop mastery
- 📦 Containers
- 🔢 Indexing (start / stop / step)
- ⚙️ Functions, recursion, decorators, classes
- 🚦 Complex conditions (and / or / nested)

All wrapped in **fun football stories** — because learning should feel alive.

---

# 🥇 Python Logic Olympics (20 Puzzles)

Difficulty increases **gradually**.
Try each puzzle **before opening the solution**.

---

## 🟢 Puzzle 1 — Messi’s Goal Counter (Warm-Up)

Messi scored goals in matches:
```python
goals = [1, 0, 2, 1, 3, 0]
````

**Task:** Count total goals using a loop (no `sum()`).

<details>
<summary>✅ Solution</summary>

```python
total = 0
for g in goals:
    total += g
print(total)
```

</details>

---

## 🟢 Puzzle 2 — Prime Jersey Numbers

Messi wore jerseys from `1` to `n`.

**Task:** Return **all prime numbers < n**.

<details>
<summary>✅ Solution</summary>

```python
def is_prime(x):
    if x < 2:
        return False
    i = 2
    while i * i <= x:
        if x % i == 0:
            return False
        i += 1
    return True

def primes_less_than(n):
    return [i for i in range(n) if is_prime(i)]
```

</details>

---

## 🟢 Puzzle 3 — Skipping Injured Matches (continue)

Messi missed matches marked as `"injured"`.

```python
matches = ["goal", "goal", "injured", "goal"]
```

**Task:** Count goals, skip injured matches.

<details>
<summary>✅ Solution</summary>

```python
count = 0
for m in matches:
    if m == "injured":
        continue
    count += 1
```

</details>

---

## 🟡 Puzzle 4 — Stop at Red Card (break)

Stop counting goals once Messi gets a `"red"` card.

<details>
<summary>✅ Solution</summary>

```python
events = ["goal", "goal", "red", "goal"]
count = 0
for e in events:
    if e == "red":
        break
    if e == "goal":
        count += 1
```

</details>

---

## 🟡 Puzzle 5 — Indexing Like a Pro

Get **every second match** Messi played.

```python
matches = ["A", "B", "C", "D", "E"]
```

<details>
<summary>✅ Solution</summary>

```python
print(matches[::2])
```

</details>

---

## 🟡 Puzzle 6 — Goals in First Half Only

First half = first `len(matches)//2`.

<details>
<summary>✅ Solution</summary>

```python
half = len(matches) // 2
print(matches[:half])
```

</details>

---

## 🟡 Puzzle 7 — Yellow + Red Logic (AND / OR)

Messi is suspended if:

* red card
* OR 2+ yellow cards

```python
yellow = 2
red = False
```

<details>
<summary>✅ Solution</summary>

```python
suspended = red or yellow >= 2
```

</details>

---

## 🟠 Puzzle 8 — Recursive Goal Sum

Sum goals using **recursion only**.

<details>
<summary>✅ Solution</summary>

```python
def recursive_sum(arr):
    if not arr:
        return 0
    return arr[0] + recursive_sum(arr[1:])
```

</details>

---

## 🟠 Puzzle 9 — Assist + Goal Filter

Count matches where Messi had **goal AND assist**.

```python
stats = [(1,1), (1,0), (0,1), (1,1)]
```

<details>
<summary>✅ Solution</summary>

```python
count = 0
for g, a in stats:
    if g == 1 and a == 1:
        count += 1
```

</details>

---

## 🟠 Puzzle 10 — Dictionary Aggregation

Track total goals per season.

<details>
<summary>✅ Solution</summary>

```python
seasons = {"2019": 30, "2020": 25}
total = sum(seasons.values())
```

</details>

---

## 🔵 Puzzle 11 — Decorator: Match Logger

Log before and after Messi plays.

<details>
<summary>✅ Solution</summary>

```python
def logger(fn):
    def wrapper():
        print("Match start")
        fn()
        print("Match end")
    return wrapper

@logger
def play():
    print("Messi scores!")
```

</details>

---

## 🔵 Puzzle 12 — Class: Player Card System

<details>
<summary>✅ Solution</summary>

```python
class Player:
    def __init__(self):
        self.yellow = 0
        self.red = False

    def foul(self):
        self.yellow += 1
        if self.yellow >= 2:
            self.red = True
```

</details>

---

## 🔵 Puzzle 13 — While Loop Simulator

Simulate Messi scoring until stamina hits zero.

<details>
<summary>✅ Solution</summary>

```python
stamina = 5
goals = 0
while stamina > 0:
    goals += 1
    stamina -= 1
```

</details>

---

## 🔴 Puzzle 14 — Nested Containers

Count goals from nested tournament data.

<details>
<summary>✅ Solution</summary>

```python
tournament = [[1,2],[0,1],[3]]
total = sum(sum(match) for match in tournament)
```

</details>

---

## 🔴 Puzzle 15 — Sliding Window (Advanced Indexing)

Max goals in **2 consecutive matches**.

<details>
<summary>✅ Solution</summary>

```python
goals = [1,2,0,3]
max_sum = 0
for i in range(len(goals)-1):
    max_sum = max(max_sum, goals[i] + goals[i+1])
```

</details>

---

## 🔴 Puzzle 16 — Complex Conditions

Valid match if:

* goals ≥ 1
* assists ≥ 1
* no red card

<details>
<summary>✅ Solution</summary>

```python
valid = goals >= 1 and assists >= 1 and not red
```

</details>

---

## 🔴 Puzzle 17 — Recursive Match Tree

Traverse knockout tree recursively.

<details>
<summary>✅ Solution</summary>

```python
def traverse(node):
    if not node:
        return 0
    return node["goals"] + traverse(node.get("next"))
```

</details>

---

## 🟣 Puzzle 18 — State Machine Logic

Messi state: `"play" → "yellow" → "red"`

<details>
<summary>✅ Solution</summary>

```python
state = "play"
if foul:
    state = "yellow" if state == "play" else "red"
```

</details>

---

## 🟣 Puzzle 19 — Full Match Engine

Combine:

* loops
* conditions
* classes
* break/continue

<details>
<summary>✅ Solution</summary>

```python
for minute in range(90):
    if red:
        break
    if injured:
        continue
```

</details>

---

## 🏆 Puzzle 20 — FINAL BOSS (Everything)

Simulate Messi’s season:

* goals
* assists
* yellow/red cards
* suspension logic
* class + function + loop + recursion

<details>
<summary>✅ Solution (Condensed)</summary>

```python
class Messi:
    def __init__(self):
        self.goals = 0
        self.yellow = 0
        self.red = False

    def play_match(self, g, a, y):
        if self.red:
            return
        self.goals += g
        self.yellow += y
        if self.yellow >= 2:
            self.red = True
```

</details>

---

## 🧠 Final Message

If you understand **this entire document**:

You don’t just “know Python”.

You **think like a software engineer**.

⚽🐐 Messi would approve.

---