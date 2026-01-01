---
title: LC-TEST-11 — Messi & Barcelona Career Analytics (Indexing Mastery)
weight: 100
date: '2026-01-01'
type: book
---

<!--more-->

## ⚽ Why This Problem Exists

This is **not** a toy problem.

This problem is designed to simulate:

> 📊 Real-world analytics  
> 🧠 Algorithmic thinking  
> 🧪 Data slicing & indexing mastery  

If you can solve **this single problem** cleanly:

✔ You understand Python deeply  
✔ You can read & manipulate structured data  
✔ You think like a strong backend / ML / data engineer  

---

## 🧠 What You Will Learn

This problem forces you to use:

* `for` loops with **range(start, stop, step)**
* Heavy **indexing & slicing**
* Containers: `list`, `dict`, `tuple`
* String parsing
* Nested functions
* Multi-pass logic (but no brute force)
* Clean abstraction & reusability

---

## 🧩 Problem Statement — Messi at Barcelona

You are given **Messi's season-by-season record at FC Barcelona**  
as a single encoded string.

Each season is encoded as:

```

"SEASON:GOALS|ASSISTS|MATCHES"

````

All seasons are joined by commas.

### 📥 Input

```text
career_data = (
  "2004:1|0|9,"
  "2005:8|3|25,"
  "2006:17|3|36,"
  "2007:16|13|40,"
  "2008:38|17|51,"
  "2009:47|11|53,"
  "2010:53|24|55,"
  "2011:73|29|60,"
  "2012:60|16|50,"
  "2013:41|14|46,"
  "2014:58|27|57,"
  "2015:41|23|49,"
  "2016:54|16|52,"
  "2017:45|18|54,"
  "2018:51|19|50,"
  "2019:31|25|44,"
  "2020:30|9|47"
)
````

---

## 🎯 Tasks (All Must Be Solved)

Write a function `analyze_messi_career(career_data)` that returns a dictionary with:

### 1️⃣ Peak Season (Goals)

* Season with **maximum goals**
* Return `(season, goals)`

---

### 2️⃣ Most Efficient Season

Efficiency = `goals / matches`

* Use **float division**
* Return `(season, efficiency)` rounded to **2 decimals**

---

### 3️⃣ Best 3-Year Goal Window (Sliding Window)

Find **3 consecutive seasons** with:

* Maximum total goals
* Return:

  ```
  {
    "seasons": [season1, season2, season3],
    "total_goals": X
  }
  ```

⚠️ You **must** use indexing (`range(start, stop)`),
not hardcoded seasons.

---

### 4️⃣ Playmaker Index

Define:

```
playmaker_score = assists / matches
```

Return **all seasons** where:

```
playmaker_score >= career_average
```

Return list of seasons.

---

### 5️⃣ Career Summary String

Return a formatted string:

```
"Messi played X seasons at Barcelona, scoring Y goals with Z assists."
```

---

## 🧠 Interviewer Insight

This problem tests:

> ❗ Can you parse structured strings
> ❗ Can you index and slice correctly
> ❗ Can you reuse logic via nested functions
> ❗ Can you avoid brute force

This is **Olympiad-level logic with real-world flavor**.

---

## 🧑‍💻 Full Python Solution

```python
def analyze_messi_career(career_data):

    # ---------- Helper: Parse Career ----------
    def parse_career(data):
        seasons = []
        records = data.split(",")

        for record in records:
            year, stats = record.split(":")
            goals, assists, matches = map(int, stats.split("|"))
            seasons.append({
                "season": int(year),
                "goals": goals,
                "assists": assists,
                "matches": matches
            })
        return seasons

    seasons = parse_career(career_data)

    # ---------- 1️⃣ Peak Goal Season ----------
    peak = max(seasons, key=lambda x: x["goals"])
    peak_season = (peak["season"], peak["goals"])

    # ---------- 2️⃣ Most Efficient Season ----------
    def efficiency(season):
        return season["goals"] / season["matches"]

    best_eff = max(seasons, key=efficiency)
    best_eff_season = (
        best_eff["season"],
        round(efficiency(best_eff), 2)
    )

    # ---------- 3️⃣ Best 3-Year Goal Window ----------
    max_goals = 0
    best_window = []

    for i in range(0, len(seasons) - 2):
        window = seasons[i:i+3]              # slicing
        total = sum(s["goals"] for s in window)

        if total > max_goals:
            max_goals = total
            best_window = [s["season"] for s in window]

    best_3_year_window = {
        "seasons": best_window,
        "total_goals": max_goals
    }

    # ---------- 4️⃣ Playmaker Index ----------
    total_assists = sum(s["assists"] for s in seasons)
    total_matches = sum(s["matches"] for s in seasons)
    career_avg = total_assists / total_matches

    playmaker_seasons = [
        s["season"]
        for s in seasons
        if (s["assists"] / s["matches"]) >= career_avg
    ]

    # ---------- 5️⃣ Career Summary ----------
    summary = (
        f"Messi played {len(seasons)} seasons at Barcelona, "
        f"scoring {sum(s['goals'] for s in seasons)} goals "
        f"with {sum(s['assists'] for s in seasons)} assists."
    )

    return {
        "peak_season": peak_season,
        "most_efficient": best_eff_season,
        "best_3_year_window": best_3_year_window,
        "playmaker_seasons": playmaker_seasons,
        "summary": summary
    }
```

---

## ⏱️ Complexity Analysis

* **Time:** O(n)
* **Space:** O(n)

Every pass has a purpose.
No brute force. No wasted loops.

---

## 🧠 Beginner vs Elite Thinking

**Beginner:**

> “I’ll manually check seasons.”

**Elite Python Engineer:**

> “Index windows, abstract logic, reuse functions.”

---

## 🏁 Final Takeaway

> If you can write this code **cleanly and confidently**:
>
> ✅ LeetCode Hard is realistic
> ✅ System design data logic feels natural
> ✅ Real-life analytics problems become easy

This is **not practice** —
this is **graduation** 🎓🐐⚽

---