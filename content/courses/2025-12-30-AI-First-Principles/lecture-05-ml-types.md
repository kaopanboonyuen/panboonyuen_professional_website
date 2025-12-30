---
title: "Lecture 05 — Types of Machine Learning"
date: "2025-12-30"
type: book
weight: 50
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~3 hours (core AI taxonomy lecture)

---

## 🧠 Big Picture (Read This First)

> **Machine Learning = systems that improve performance by learning from experience.**

But here is the secret:

> Not all experience teaches the same way.

Different problems → different learning paradigms.

If you choose the *wrong type*, even the best model will fail.

---

## 🧭 A Simple Mental Map

Think of learning like school:

| Learning Type | Analogy |
|--------------|--------|
| Supervised | Teacher gives answers |
| Unsupervised | Student explores alone |
| Semi-supervised | Few answers, many questions |
| Self-supervised | Student creates own homework |
| Reinforcement | Learning by reward & punishment |

---

# 1️⃣ Supervised Learning  
**“Learning with a teacher”**

---

## 📘 Definition

Learning from **labeled data**:

```

(input → correct output)

````

Examples:
- image → label (cat / dog)
- email → spam / not spam
- house features → price

---

## 🧠 Intuition (Human Version)

A teacher says:
> “This is a cat.”  
> “This is NOT a cat.”

The student adjusts until mistakes are small.

---

## 🧪 Classic Problems

### 🔹 Classification
- spam detection
- medical diagnosis
- fraud detection

### 🔹 Regression
- house price prediction
- temperature forecasting

---

## 💻 Mini Project (Beginner-Friendly)

### 🎯 Project: Email Spam Classifier

**Steps:**
1. Collect labeled emails
2. Convert text → numbers
3. Train a classifier
4. Evaluate accuracy

```python
from sklearn.linear_model import LogisticRegression
from sklearn.feature_extraction.text import CountVectorizer

texts = ["free money", "meeting tomorrow"]
labels = [1, 0]  # 1=spam, 0=not spam

vec = CountVectorizer()
X = vec.fit_transform(texts)

model = LogisticRegression()
model.fit(X, labels)
````

👉 This is **real AI**, not magic.

---

## ❓ Quiz

{{< spoiler text="Why does supervised learning need labels?" >}}
Because the loss function compares predictions with ground truth.
{{< /spoiler >}}

---

# 2️⃣ Unsupervised Learning

**“Learning without answers”**

---

## 📘 Definition

Learning **patterns without labels**.

The system asks:

> “What structure exists here?”

---

## 😄 Funny Example

You walk into a party with strangers.

No name tags.

Your brain automatically groups people:

* similar clothes
* similar behavior
* similar interests

That’s **clustering**.

---

## 🧪 Common Techniques

* K-means clustering
* PCA (dimensionality reduction)
* Topic modeling

---

## 💻 Mini Project

### 🎯 Project: Customer Segmentation

```python
from sklearn.cluster import KMeans

X = [[20, 500], [25, 700], [45, 2000]]  # age, spending
kmeans = KMeans(n_clusters=2)
kmeans.fit(X)

print(kmeans.labels_)
```

Used in:

* marketing
* recommendation systems
* anomaly detection

---

## ❓ Quiz

{{< spoiler text="Is unsupervised learning useful without labels?" >}}
Yes — it discovers structure and representations.
{{< /spoiler >}}

---

# 3️⃣ Semi-Supervised Learning

**“A few answers, many questions”**

---

## 📘 Definition

Small labeled dataset
+
Large unlabeled dataset

---

## 🧠 Why This Exists

Labeling costs:

* money 💰
* time ⏳
* experts 🧠

But raw data is everywhere.

---

## 🧪 Real-World Uses

* medical images
* legal documents
* speech recognition

---

## 💻 Mini Project Idea

Label:

* 100 images by hand

Let the model:

* infer the rest

This is how **real-world AI systems survive**.

---

## ❓ Quiz

{{< spoiler text="Why is semi-supervised learning practical?" >}}
Labels are expensive; data is cheap.
{{< /spoiler >}}

---

# 4️⃣ Self-Supervised Learning

**“The AI creates its own teacher”**

---

## 📘 Definition

Labels are **automatically generated from data itself**.

---

## 🤯 Why This Changed AI Forever

Instead of humans saying:

> “This is the answer”

The system asks:

> “What part of the data is missing?”

---

## 🧪 Famous Examples

### 🔹 NLP

* Masked word prediction (BERT)

### 🔹 Vision

* Predict image rotation
* Contrastive learning (CLIP)

---

## 💻 Mini Project (Conceptual)

```text
Input: "AI is ____"
Target: "powerful"
```

This simple idea trained **LLMs**.

---

## ❓ Quiz

{{< spoiler text="Why is self-supervised learning powerful?" >}}
It scales with data, not human labeling.
{{< /spoiler >}}

---

# 5️⃣ Reinforcement Learning (RL)

**“Learning by doing”**

---

## 📘 Definition

Learning from **reward signals**, not correct answers.

---

## 🕹️ Intuition

You train a dog 🐕:

* Good behavior → treat
* Bad behavior → no treat

No explicit instructions.

---

## 🧪 Key Components

| Term        | Meaning  |
| ----------- | -------- |
| Agent       | Learner  |
| Environment | World    |
| Action      | Choice   |
| Reward      | Feedback |

---

## 💻 Tiny RL Example (Concept)

```python
if reward > 0:
    increase_probability(action)
else:
    decrease_probability(action)
```

Used in:

* AlphaGo
* robotics
* recommendation systems
* game AI

---

## ❓ Quiz

{{< spoiler text="What is the exploration–exploitation tradeoff?" >}}
Balancing trying new actions vs using known good ones.
{{< /spoiler >}}

---

## 🧠 How These Power Modern AI

| System       | Learning Type                |
| ------------ | ---------------------------- |
| ChatGPT      | Self-supervised + RLHF       |
| Image AI     | Self-supervised + supervised |
| Robots       | Reinforcement learning       |
| Recommenders | Supervised + RL              |

---

## 🎓 Final Big Insight

> There is no “best” learning type.
> There is only **the right tool for the problem**.

Great AI engineers choose wisely.

---

## 🌱 Final Reflection

{{< spoiler text="If you had unlimited data but no labels, which learning paradigm would you choose?" >}}
Self-supervised learning.
{{< /spoiler >}}