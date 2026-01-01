---
title: LC-TEST-11 — FIFA World Cup 2026 Ultimate Analytics
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Problem Is Brutal (In a Good Way)

This problem simulates:

> 📊 Sports analytics  
> 🧠 Tournament logic  
> ⚙️ Backend-grade data processing  

No trick.
No memorization.

Only **pure reasoning + Python mastery**.

---

## 🧠 What You Will Master

By solving this problem, you will practice:

* Deep string parsing
* Index-heavy iteration (`range(start, stop, step)`)
* Nested containers (`dict` → `list` → `tuple`)
* Sliding window over tournament stages
* Ranking with multiple tie-breakers
* Nested helper functions
* Writing production-level logic

---

## 🏆 Problem Statement — World Cup 2026

You are given **match-by-match data** from the FIFA World Cup 2026.

Each match is encoded as:

```

"STAGE|TEAM_A|GOALS_A|TEAM_B|GOALS_B"

````

All matches are concatenated into one long string.

---

## 📥 Input

```text
wc2026_data = (
  "GROUP|ARG|2|FRA|1,"
  "GROUP|BRA|3|GER|3,"
  "GROUP|ESP|1|ENG|0,"
  "GROUP|ARG|1|GER|1,"
  "GROUP|BRA|2|FRA|0,"
  "GROUP|ESP|2|ARG|2,"
  "GROUP|ENG|3|GER|1,"
  "GROUP|BRA|1|ESP|0,"
  "ROUND16|ARG|3|ENG|1,"
  "ROUND16|BRA|2|GER|0,"
  "ROUND16|ESP|1|FRA|2,"
  "ROUND16|USA|0|NED|1,"
  "QF|ARG|2|BRA|1,"
  "QF|FRA|1|ENG|0,"
  "SF|ARG|1|FRA|1,"
  "SF|BRA|2|ESP|0,"
  "FINAL|ARG|3|BRA|2"
)
````

---

## 🎯 Your Tasks (All Required)

Implement:

```python
analyze_world_cup_2026(wc2026_data)
```

Return a dictionary with **all results below**.

---

## 1️⃣ Group Stage Standings

For **GROUP matches only**, compute for each team:

* Matches played
* Goals scored
* Goals conceded
* Goal difference
* Points (win=3, draw=1, loss=0)

Return:

```python
{
  "ARG": {"points": X, "gd": Y},
  ...
}
```

---

## 2️⃣ Top Attacking Teams

Across **all stages**, find **Top 3 teams** by:

1. Total goals
2. If tie → fewer matches
3. If tie → lexicographical order

Return:

```python
[("ARG", goals), ("BRA", goals), ("FRA", goals)]
```

---

## 3️⃣ Knockout Survival Path (Indexing Heavy)

For each knockout team:

* ROUND16 → QF → SF → FINAL

Compute the **longest consecutive survival streak**.

Return:

```python
{
  "ARG": 4,
  "BRA": 4,
  "ENG": 2,
  ...
}
```

⚠️ You MUST use indexing (`range`, slicing).
Hardcoding stages = ❌

---

## 4️⃣ Most Dramatic Match Window 🔥

Using a **sliding window of 3 consecutive matches**, find the window with:

```
maximum total goals
```

Return:

```python
{
  "matches": [match1, match2, match3],
  "total_goals": X
}
```

---

## 5️⃣ Champion Performance Summary

Return a formatted string:

```
"ARG won the World Cup 2026 with X goals scored and Y goals conceded."
```

---

## 🧠 Interviewer Insight

This problem checks:

> ❗ Can you aggregate correctly
> ❗ Can you rank with tie-breakers
> ❗ Can you reason across stages
> ❗ Can you slide windows without restarting

This is **real analytics logic**, not puzzles.

---

## 🧑‍💻 Full Python Solution

```python
def analyze_world_cup_2026(data):

    # ---------- Parse Matches ----------
    def parse_matches(data):
        matches = []
        for rec in data.split(","):
            stage, ta, ga, tb, gb = rec.split("|")
            matches.append({
                "stage": stage,
                "A": ta,
                "B": tb,
                "ga": int(ga),
                "gb": int(gb)
            })
        return matches

    matches = parse_matches(data)

    # ---------- 1️⃣ Group Standings ----------
    standings = {}

    def update(team, goals_for, goals_against):
        if team not in standings:
            standings[team] = {"points": 0, "gd": 0}
        standings[team]["gd"] += goals_for - goals_against

        if goals_for > goals_against:
            standings[team]["points"] += 3
        elif goals_for == goals_against:
            standings[team]["points"] += 1

    for m in matches:
        if m["stage"] == "GROUP":
            update(m["A"], m["ga"], m["gb"])
            update(m["B"], m["gb"], m["ga"])

    # ---------- 2️⃣ Top Attacking Teams ----------
    goals = {}
    games = {}

    for m in matches:
        for team, g in [(m["A"], m["ga"]), (m["B"], m["gb"])]:
            goals[team] = goals.get(team, 0) + g
            games[team] = games.get(team, 0) + 1

    top_attack = sorted(
        goals.items(),
        key=lambda x: (-x[1], games[x[0]], x[0])
    )[:3]

    # ---------- 3️⃣ Knockout Survival ----------
    stages = ["ROUND16", "QF", "SF", "FINAL"]
    survival = {}

    for team in goals:
        path = []
        for s in stages:
            played = any(
                m["stage"] == s and team in (m["A"], m["B"])
                for m in matches
            )
            path.append(played)

        max_run = curr = 0
        for i in range(len(path)):
            if path[i]:
                curr += 1
                max_run = max(max_run, curr)
            else:
                curr = 0

        survival[team] = max_run

    # ---------- 4️⃣ Most Dramatic Window ----------
    max_goals = 0
    best_window = []

    for i in range(len(matches) - 2):
        window = matches[i:i+3]
        total = sum(m["ga"] + m["gb"] for m in window)

        if total > max_goals:
            max_goals = total
            best_window = window

    # ---------- 5️⃣ Champion Summary ----------
    final = [m for m in matches if m["stage"] == "FINAL"][0]
    champ = final["A"] if final["ga"] > final["gb"] else final["B"]

    scored = conceded = 0
    for m in matches:
        if champ == m["A"]:
            scored += m["ga"]
            conceded += m["gb"]
        elif champ == m["B"]:
            scored += m["gb"]
            conceded += m["ga"]

    summary = (
        f"{champ} won the World Cup 2026 with "
        f"{scored} goals scored and {conceded} goals conceded."
    )

    return {
        "group_standings": standings,
        "top_attack": top_attack,
        "knockout_survival": survival,
        "most_dramatic_window": {
            "matches": best_window,
            "total_goals": max_goals
        },
        "champion_summary": summary
    }
```

---

## ⏱️ Complexity

* **Time:** O(n)
* **Space:** O(n)

Clean passes.
Zero brute force.
Interview-safe.

---

## 🧠 LC-TEST-11 vs LC-TEST-12

| Skill          | LC-11 | LC-12 |
| -------------- | ----- | ----- |
| Parsing        | ✅     | 🔥    |
| Indexing       | 🔥    | 🔥🔥  |
| Containers     | ✅     | 🔥🔥  |
| Sliding Window | ✅     | 🔥🔥  |
| Real Analytics | ⚠️    | 🐐    |

---

## 🏁 Final Verdict

> If you can implement **LC-TEST-12 from scratch**:
>
> 🧠 You think like a senior engineer
> ⚙️ You can handle real datasets
> 🏆 LeetCode Hard ≠ scary anymore

---