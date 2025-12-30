---
title: DE101-PD06 — Finding Insights with Pandas (From Data to Decisions)
weight: 60
date: '2025-12-30'
type: book
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~120 minutes

## 🎯 Goal of This Chapter

This chapter teaches **how to think**, not just how to code.

You will learn:
- How to ask good questions
- How to extract insights from data
- How real companies analyze performance
- How to communicate findings clearly

---

## ⚽ Mock Dataset — FIFA World Cup Player Stats

We will use a simplified dataset inspired by **FIFA World Cup matches**,  
with focus on **Lionel Messi**.

```python
import pandas as pd

data = {
    "player": ["Messi", "Messi", "Messi", "Mbappe", "Mbappe", "Neymar", "Modric", "Messi"],
    "team": ["Argentina", "Argentina", "Argentina", "France", "France", "Brazil", "Croatia", "Argentina"],
    "match": [1, 2, 3, 1, 2, 1, 1, 4],
    "goals": [1, 2, 1, 2, 1, 1, 0, 1],
    "assists": [0, 1, 0, 0, 1, 0, 1, 0],
    "shots": [4, 6, 5, 7, 5, 4, 2, 3],
    "minutes": [90, 90, 90, 90, 90, 90, 90, 90],
    "position": ["FW", "FW", "FW", "FW", "FW", "FW", "MF", "FW"]
}

df = pd.DataFrame(data)
df
````

---

# 🧠 20 Insight Questions (with Answers)

---

## Q1️⃣ How many matches did each player play?

```python
df.groupby("player")["match"].count()
```

📌 Insight: Player usage & reliability.

---

## Q2️⃣ Total goals per player?

```python
df.groupby("player")["goals"].sum().sort_values(ascending=False)
```

📌 Insight: Who is the main scorer?

---

## Q3️⃣ Average goals per match?

```python
df.groupby("player")["goals"].mean()
```

📌 Insight: Consistency vs volume.

---

## Q4️⃣ Who contributed most (goals + assists)?

```python
df.assign(contribution=df["goals"] + df["assists"]) \
  .groupby("player")["contribution"].sum()
```

📌 Insight: True attacking impact.

---

## Q5️⃣ Messi’s total World Cup impact?

```python
df[df["player"] == "Messi"][["goals", "assists"]].sum()
```

📌 Insight: Player-specific deep dive.

---

## Q6️⃣ Shots-to-goals efficiency?

```python
df.assign(efficiency=df["goals"] / df["shots"]) \
  .groupby("player")["efficiency"].mean()
```

📌 Insight: Finishing quality.

---

## Q7️⃣ Which team scored the most goals?

```python
df.groupby("team")["goals"].sum()
```

📌 Insight: Team dominance.

---

## Q8️⃣ Messi’s share of Argentina goals?

```python
total_arg_goals = df[df["team"] == "Argentina"]["goals"].sum()
messi_goals = df[df["player"] == "Messi"]["goals"].sum()

messi_goals / total_arg_goals
```

📌 Insight: Team dependency on star player.

---

## Q9️⃣ Goals by position?

```python
df.groupby("position")["goals"].sum()
```

📌 Insight: Tactical contribution.

---

## Q1️⃣0️⃣ Average shots per match per player?

```python
df.groupby("player")["shots"].mean()
```

📌 Insight: Offensive involvement.

---

## Q1️⃣1️⃣ Which match had the most goals?

```python
df.groupby("match")["goals"].sum().sort_values(ascending=False)
```

📌 Insight: High-impact games.

---

## Q1️⃣2️⃣ Messi trend over matches?

```python
df[df["player"] == "Messi"].sort_values("match")[["match", "goals"]]
```

📌 Insight: Performance trajectory.

---

## Q1️⃣3️⃣ Player with best goals per 90 minutes?

```python
df.assign(goals_per_90=df["goals"] / df["minutes"] * 90) \
  .groupby("player")["goals_per_90"].mean()
```

📌 Insight: Fair comparison.

---

## Q1️⃣4️⃣ Assist leaders?

```python
df.groupby("player")["assists"].sum().sort_values(ascending=False)
```

📌 Insight: Playmaking ability.

---

## Q1️⃣5️⃣ Messi vs Mbappe comparison?

```python
df[df["player"].isin(["Messi", "Mbappe"])] \
  .groupby("player")[["goals", "assists", "shots"]].mean()
```

📌 Insight: Superstar comparison.

---

## Q1️⃣6️⃣ Which team relies most on one player?

```python
team_totals = df.groupby("team")["goals"].sum()
player_totals = df.groupby(["team", "player"])["goals"].sum()

(player_totals / team_totals).sort_values(ascending=False)
```

📌 Insight: Risk concentration.

---

## Q1️⃣7️⃣ Match-by-match contribution table?

```python
df.assign(contribution=df["goals"] + df["assists"]) \
  .pivot_table(
      index="match",
      columns="player",
      values="contribution",
      aggfunc="sum"
  )
```

📌 Insight: Game-level impact.

---

## Q1️⃣8️⃣ Who is most consistent scorer?

```python
df.groupby("player")["goals"].std()
```

📌 Insight: Low variance = consistency.

---

## Q1️⃣9️⃣ Identify underperformers (high shots, low goals)

```python
df.assign(conversion=df["goals"] / df["shots"]) \
  .sort_values("conversion")
```

📌 Insight: Optimization opportunity.

---

## Q2️⃣0️⃣ Executive Summary Table

```python
df.groupby("player").agg(
    matches=("match", "count"),
    goals=("goals", "sum"),
    assists=("assists", "sum"),
    shots=("shots", "sum")
)
```

📌 Insight: One-table decision view.

---

## 🧠 How Companies Use This

* **Google** → Experiment impact
* **Meta** → Creator performance
* **OpenAI** → Model evaluation metrics
* **Sports Analytics** → Strategy decisions

Same logic, different domain.

---

## 🏁 Final Lesson

Insight is not about charts.
Insight is about **asking the right questions**.

Pandas is your microscope.

---

## 🚀 Next Steps

* Add visualization
* Turn insights into dashboards
* Feed features into ML models

You now think like a **Data Engineer + Analyst + AI Researcher** 🧠🔥