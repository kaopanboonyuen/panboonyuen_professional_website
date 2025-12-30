---
title: DE101-PD03 — Data Cleaning & Transformation (Production Mindset)
weight: 30
type: book
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~60 minutes

## 🎯 Why Data Cleaning Is the Real Job

In the real world:
- 70–80% of data work = cleaning & transformation
- Models fail more often due to **bad data**, not bad algorithms

At companies like **Google, Meta, OpenAI**:
> *If your data is wrong, your model is wrong.*

---

## 🧠 What Is Data Cleaning?

Data cleaning means:
- Making data **usable**
- Making assumptions **explicit**
- Removing ambiguity
- Preventing silent bugs

---

## 🧹 Common Real-World Data Problems

| Problem | Example |
|------|--------|
| Missing values | NaN age, null clicks |
| Wrong data type | "30" instead of 30 |
| Inconsistent labels | "USA", "U.S.", "United States" |
| Duplicate rows | Same user logged twice |
| Outliers | Age = 999 |

---

## 📊 Example Dataset (User Analytics)

```python
import pandas as pd
import numpy as np

data = {
    "user_id": [1, 2, 3, 3],
    "age": [25, None, "30", 30],
    "country": ["US", "USA", "us", "USA"],
    "clicks": [10, np.nan, 5, 5]
}

df = pd.DataFrame(data)
df
````

---

## 🔍 Step 1: Inspect Before Cleaning (Critical)

Never clean blindly.

```python
df.info()
df.describe(include="all")
df.isna().sum()
```

This answers:

* Which columns are broken?
* How many missing values?
* Are types correct?

---

## 🗑️ Removing Missing Data (`dropna`)

```python
df.dropna()
```

⚠️ Dangerous in production:

* You may delete important users
* Always know **why** you drop

Better:

```python
df.dropna(subset=["age"])
```

---

## 🩹 Filling Missing Data (`fillna`)

```python
df["clicks"] = df["clicks"].fillna(0)
```

Common strategies:

* Mean / median (numeric)
* Mode (categorical)
* Zero (counts)
* Forward fill (time series)

---

## 🔢 Fixing Data Types (`astype`)

```python
df["age"] = df["age"].astype(int)
```

This often fails → must clean first:

```python
df["age"] = pd.to_numeric(df["age"], errors="coerce")
```

Engineers always expect type issues.

---

## 🏷️ Renaming for Clarity

```python
df.rename(columns={"clicks": "num_clicks"})
```

Why this matters:

* Self-documenting code
* Fewer misunderstandings
* Cleaner downstream pipelines

---

## 🧠 Deduplication (Very Common)

```python
df.drop_duplicates(subset=["user_id"])
```

Used for:

* User logs
* Event streams
* Experiment tracking

---

## 🌍 Normalizing Categorical Data

```python
df["country"] = (
    df["country"]
    .str.lower()
    .replace({"us": "usa"})
)
```

Small inconsistency → huge analytics bug.

---

## 🔄 Feature Transformation

Create new features from old ones:

```python
df["is_active"] = df["num_clicks"] > 0
```

This is **feature engineering**.

---

## 🧪 Outlier Handling

```python
df = df[df["age"] < 100]
```

Outliers:

* Break averages
* Break models
* Must be justified, not guessed

---

## 🧩 `.assign()` — Functional Style

```python
df = df.assign(
    age_next_year=lambda x: x["age"] + 1,
    clicks_per_age=lambda x: x["num_clicks"] / x["age"]
)
```

No mutation. Clear logic.

---

## 🔗 Method Chaining (Professional Style)

```python
df = (
    df
    .drop_duplicates("user_id")
    .assign(
        age=lambda x: pd.to_numeric(x["age"], errors="coerce"),
        country=lambda x: x["country"].str.lower()
    )
    .dropna(subset=["age"])
    .query("age < 100")
)
```

This is how **production Pandas code looks**.

{{< spoiler text="Why method chaining is preferred in real projects?" >}}
Readable, debuggable, testable, reproducible
{{< /spoiler >}}

---

## 🧠 Pipeline Thinking (Interview Gold)

Engineers think in pipelines:

1. Load data
2. Inspect
3. Clean
4. Transform
5. Validate
6. Export

Each step should be:

* Explicit
* Reproducible
* Testable

---

## 🧪 Validation Checks (Often Missed)

```python
assert df["age"].min() > 0
assert df["user_id"].is_unique
```

These prevent silent failures.

---

## 🏢 Real-World Case (Meta / OpenAI)

Before training models:

* Pandas pipeline cleans data
* Validates assumptions
* Logs anomalies
* Produces clean tables

Only then → Spark / TensorFlow / PyTorch.

---

## ⚠️ Common Beginner Mistakes

❌ Overusing `dropna()`
❌ Ignoring data types
❌ Modifying DataFrame in-place blindly
❌ No validation checks

---

## 🏁 Summary

* Cleaning is the real job
* Inspect before modifying
* Be explicit, not clever
* Method chaining = professional style
* Pipelines prevent bugs

Good data → good decisions → good models.

---

## 🚀 Next Chapter

👉 **DE101-PD04 — GroupBy, Aggregation, and Business Analytics**

This is where insights are born.