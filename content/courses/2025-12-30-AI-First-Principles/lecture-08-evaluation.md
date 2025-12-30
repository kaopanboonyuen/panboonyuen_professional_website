---
title: "Lecture 08 — Evaluation Metrics"
date: "2025-12-30"
type: book
weight: 80
math: true
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~3 hours (core evaluation & reasoning lecture)

---

## 📏 Why Evaluation Metrics Matter (Truth First)

A dangerous myth:

> “If accuracy is high, the model is good.”

Reality:

> **Wrong metric = wrong conclusion = real-world harm**

Evaluation metrics define:
- what “success” means
- what the model optimizes for
- how humans trust AI

---

## 🧠 One Sentence That Explains Metrics

> **Metrics are how humans translate values into numbers.**

Different problems → different values → different metrics.

---

## 🧪 A Running Example (Very Important)

Imagine a **disease detection system** 🏥

- Disease rate: 1%
- Healthy people: 99%

This will destroy naive accuracy.

---

# 🔹 PART I — Classification Metrics

---

## 🧩 Confusion Matrix (The Foundation)

Everything starts here.

|                | Predicted Positive | Predicted Negative |
|----------------|-------------------|-------------------|
| **Actual Positive** | TP (True Positive) | FN (False Negative) |
| **Actual Negative** | FP (False Positive) | TN (True Negative) |

👉 Every metric is built from these four numbers.

---

## 🎯 Accuracy (The Most Misused Metric)

### 📐 Formula

$$
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
$$

### 😄 Example

Out of 1000 people:
- 990 healthy
- 10 sick

Model predicts **everyone healthy**.

Accuracy:
$$
= \frac{990}{1000} = 99\%
$$

🎉 Looks amazing  
💀 Completely useless

---

## ❌ Why Accuracy Fails

- ignores class imbalance
- ignores cost of mistakes
- rewards lazy models

---

## 🎯 Precision (How Careful Are You?)

### 📐 Formula

$$
Precision = \frac{TP}{TP + FP}
$$

### 🧠 Meaning

> When the model says “positive”, how often is it correct?

---

### 😄 Example (Spam Filter)

- Marked 10 emails as spam
- 8 were actually spam

$$
Precision = \frac{8}{10} = 0.8
$$

High precision = few false alarms 📩🚫

---

## 🎯 Recall (How Much Did You Catch?)

### 📐 Formula

$$
Recall = \frac{TP}{TP + FN}
$$

### 🧠 Meaning

> Of all real positives, how many did we find?

---

### 😄 Example (Medical Test)

- 10 sick patients
- Found 7

$$
Recall = \frac{7}{10} = 0.7
$$

Low recall = missed patients 😬

---

## ⚖️ Precision vs Recall (Classic Tradeoff)

| Metric | Focus |
|------|------|
| Precision | Avoid false positives |
| Recall | Avoid false negatives |

Medical diagnosis → high recall  
Spam filter → high precision

---

## 🎯 F1 Score (The Balance)

### 📐 Formula

$$
F1 = 2 \cdot \frac{Precision \cdot Recall}{Precision + Recall}
$$

### 🧠 Meaning

> One number that balances both.

---

### 😄 Example

Precision = 0.8  
Recall = 0.6  

$$
F1 = 2 \cdot \frac{0.8 \cdot 0.6}{1.4} \approx 0.69
$$

Used when:
- classes are imbalanced
- both errors matter

---

# 🔹 PART II — Regression Metrics

---

## 🎯 Mean Absolute Error (MAE)

### 📐 Formula

$$
MAE = \frac{1}{n} \sum |y - \hat{y}|
$$

### 🧠 Meaning

> Average absolute mistake.

---

### 😄 Example

True prices: `[100, 200]`  
Predicted: `[90, 210]`

Errors:
- |100−90| = 10
- |200−210| = 10

$$
MAE = \frac{20}{2} = 10
$$

Easy to understand 👍

---

## 🎯 Mean Squared Error (MSE)

### 📐 Formula

$$
MSE = \frac{1}{n} \sum (y - \hat{y})^2
$$

### 🧠 Meaning

> Punishes large mistakes more.

---

### 😄 Example

Errors: `[10, 10]`  
Squares: `[100, 100]`

$$
MSE = 100
$$

Used when big errors are very bad.

---

## 🎯 Root Mean Squared Error (RMSE)

### 📐 Formula

$$
RMSE = \sqrt{MSE}
$$

### 🧠 Meaning

Same unit as target variable.

If RMSE = 10 → “average error ≈ 10 units”

---

# 🔹 PART III — NLP Metrics (Language Is Hard)

---

## 🧠 Why NLP Metrics Are Tricky

Language has:
- multiple correct answers
- style differences
- synonyms

Exact matching fails.

---

## ✍️ BLEU Score (Translation)

Measures:
> Overlap of n-grams between prediction and reference.

### 📐 Simplified Idea

More shared phrases → higher BLEU.

---

### 😄 Example

Reference:
> “AI changes the world”

Prediction:
> “AI transforms the world”

High BLEU (similar meaning).

---

## 📄 ROUGE (Summarization)

Measures:
- overlap of words
- overlap of phrases

Used in:
- summarization
- report generation

---

## ⚠️ Important Truth About NLP Metrics

High BLEU/ROUGE ≠ good answer.

Human evaluation still matters.

ChatGPT is trained with:
- cross-entropy (math)
- human feedback (values)

---

# 🔹 PART IV — Metrics in the Real World

---

## 🏥 Medical AI
- prioritize recall
- false negatives are dangerous

## 📩 Spam Detection
- prioritize precision
- false positives annoy users

## 🚗 Self-Driving
- safety-critical metrics
- worst-case analysis

## 🤖 ChatGPT
- fluency
- helpfulness
- harmlessness
- alignment (human judgment)

---

## 🧠 Choosing the Right Metric (Golden Rule)

Ask:
1. What mistake hurts more?
2. Who pays the cost?
3. Is data balanced?

Metrics encode **ethics**.

---

## 🌍 Final Big Insight

> **AI does not know what is “good.”  
Metrics tell it what to care about.**

Choose wisely.

---

## ❓ Final Reflection

{{< spoiler text="If you optimize the wrong metric, can AI become dangerous?" >}}
Yes — optimization without wisdom is risk.
{{< /spoiler >}}