---
title: DE101-PD04 — GroupBy, Aggregation & Joins (Analytics & Interview Mastery)
weight: 40
date: '2025-12-30'
type: book
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~75–90 minutes

## 🎯 Why This Chapter Is Critical

If Pandas were a weapon:
- Cleaning = sharpening
- **GroupBy & Join = actual power**

Most real-world questions are:
- “Which group performs best?”
- “How do metrics change by segment?”
- “How do we combine datasets correctly?”

---

## 🧠 GroupBy Mental Model (Most Important Idea)

**GroupBy = Split → Apply → Combine**

1. Split data into groups
2. Apply aggregation or transformation
3. Combine results into a new table

This mindset works in:
- Pandas
- SQL
- Spark
- BigQuery

---

## 📊 Example Dataset (E-Commerce Analytics)

```python
import pandas as pd

data = {
    "user_id": [1, 2, 1, 3, 2, 3, 1],
    "country": ["US", "US", "US", "FR", "US", "FR", "US"],
    "revenue": [100, 200, 150, 80, 120, 60, 90],
    "device": ["mobile", "desktop", "mobile", "mobile", "mobile", "desktop", "desktop"]
}

df = pd.DataFrame(data)
df
````

---

## 📦 Basic GroupBy

```python
df.groupby("country")["revenue"].sum()
```

### Output

```
country
FR    140
US    660
```

This answers:

> “How much revenue comes from each country?”

---

## 🔢 Multiple Aggregations

```python
df.groupby("country")["revenue"].agg(["sum", "mean", "count"])
```

Used daily in:

* KPI dashboards
* Business reports
* Model evaluation

---

## 🧠 GroupBy Multiple Columns

```python
df.groupby(["country", "device"])["revenue"].sum()
```

Now you are thinking like an analyst.

---

## 🧮 Resetting Index (Very Common)

```python
df.groupby("country", as_index=False)["revenue"].sum()
```

Or:

```python
df.groupby("country")["revenue"].sum().reset_index()
```

This makes output usable for joins.

---

## 🧩 `.transform()` — Keep Original Shape

```python
df["country_avg_revenue"] = (
    df.groupby("country")["revenue"].transform("mean")
)
```

Use when:

* You need group stats per row
* Feature engineering for ML

---

## 🔁 `.apply()` — Flexible but Dangerous

```python
df.groupby("country").apply(lambda x: x["revenue"].max() - x["revenue"].min())
```

⚠️ Powerful but slower.
Use only when aggregation cannot express logic.

---

## 🧠 SQL vs Pandas GroupBy

| SQL      | Pandas    |
| -------- | --------- |
| GROUP BY | groupby() |
| SUM      | sum()     |
| AVG      | mean()    |
| COUNT    | count()   |

{{< spoiler text="SQL vs Pandas GroupBy?" >}}
Conceptually identical — only syntax differs
{{< /spoiler >}}

---

## 🔗 Why Joins Matter

Real-world data is **never in one table**.

You often have:

* users table
* orders table
* events table
* experiments table

Joins connect the story.

---

## 📊 Example Tables

### Users

```python
users = pd.DataFrame({
    "user_id": [1, 2, 3],
    "country": ["US", "US", "FR"]
})
```

### Orders

```python
orders = pd.DataFrame({
    "order_id": [101, 102, 103, 104],
    "user_id": [1, 2, 1, 4],
    "amount": [250, 300, 150, 500]
})
```

---

## 🔗 Inner Join

```python
pd.merge(users, orders, on="user_id", how="inner")
```

Keeps only matching rows.

---

## 🔗 Left Join (Most Common)

```python
pd.merge(users, orders, on="user_id", how="left")
```

Used when:

* Users are primary
* Orders may be missing

---

## 🔗 Right Join

```python
pd.merge(users, orders, on="user_id", how="right")
```

Less common but useful for audits.

---

## 🔗 Outer Join

```python
pd.merge(users, orders, on="user_id", how="outer")
```

Used for:

* Data reconciliation
* Finding missing relationships

---

## 🧠 Join on Different Column Names

```python
pd.merge(
    users,
    orders,
    left_on="user_id",
    right_on="user_id"
)
```

In real data, column names rarely match.

---

## ⚠️ Join Explosion (Critical Warning)

Many-to-many joins can **multiply rows**.

```python
users.merge(orders, on="user_id")
```

Always ask:

> “What is the cardinality?”

---

## 🧪 Validation After Join

```python
assert merged["user_id"].notna().all()
```

Production engineers always validate joins.

---

## 🧠 Real-World Case (Google / Meta / OpenAI)

Example:

* Join user metadata
* Join experiment assignment
* Aggregate metrics per variant
* Decide product direction

Bad join → wrong decision → $$$ lost

---

## 🧠 Interview Patterns

Interviewers test:

* GroupBy logic
* Correct join type
* Index reset
* Avoiding row explosion

---

## 🏁 Summary

* GroupBy = Split → Apply → Combine
* `.agg()` for metrics
* `.transform()` for ML features
* Joins connect reality
* Validate after join

If you master this chapter,
you can survive **most analytics interviews**.

---

## 🚀 Next Chapter

👉 **DE101-PD05 — Time Series & Window Operations**

This is where senior-level thinking begins.