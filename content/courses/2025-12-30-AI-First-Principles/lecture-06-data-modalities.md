---
title: "Lecture 06 — Data Types & Modalities"
date: "2025-12-30"
type: book
weight: 60
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~2–2.5 hours (core data understanding lecture)

---

## 🌍 Big Idea (Read This First)

> **AI does not see the world like humans.  
It sees data representations.**

Understanding data modalities is understanding:
- what AI can learn
- what AI cannot learn
- why some problems are harder than others

---

## 📦 Data Is Everything (But Not Equal)

AI performance is often limited by:
- data quality
- data quantity
- data structure

> Better model + bad data = bad AI  
> Simple model + good data = strong AI

---

## 🧠 What Is a Modality?

A **modality** is:
> A way information is represented.

Humans:
- see 👀
- hear 👂
- read 📖

AI:
- processes numbers

All modalities become **numbers** eventually.

---

## 🔢 1️⃣ Tabular Data (The Quiet Workhorse)

### 📘 What it is
Rows & columns:
- Excel
- CSV
- databases

### 🧠 Why it matters
Most real-world AI is still tabular.

Used in:
- finance (credit scoring)
- healthcare (risk prediction)
- business (forecasting)

---

### 💻 Mini Project

```python
import pandas as pd

df = pd.DataFrame({
    "age": [25, 40, 60],
    "income": [30000, 70000, 120000]
})

df["income"].mean()
````

Tabular data loves:

* statistics
* classical ML
* interpretability

---

## 📚 2️⃣ Text Data (Language as Data)

### 📘 What it is

* sentences
* documents
* code
* chat logs

### 🧠 Challenge

Text has:

* order
* meaning
* ambiguity

Machines see:

* tokens
* embeddings

---

### 💻 Mini Example

```text
"AI is powerful"
→ ["AI", "is", "powerful"]
→ vectors
```

Used in:

* NLP
* LLMs
* search engines

---

## 🖼️ 3️⃣ Image Data (Vision)

### 📘 What it is

* pixels
* grids of numbers

### 🧠 AI does NOT see objects.

It sees:

* edges
* textures
* patterns

---

### 💻 Mini Example

```python
import numpy as np

image = np.zeros((224, 224, 3))
```

Used in:

* medical imaging
* self-driving
* facial recognition

---

## 🎧 4️⃣ Audio Data (Sound as Waves)

### 📘 What it is

* waveforms
* frequencies

AI learns:

* pitch
* rhythm
* patterns

---

### 💻 Mini Example

```text
Audio → waveform → spectrogram → model
```

Used in:

* speech recognition
* music generation
* voice assistants

---

## 🎥 5️⃣ Video Data (The Hardest Modality)

### 📘 What it is

Images + time + audio

Challenges:

* massive data size
* temporal reasoning
* motion understanding

Used in:

* action recognition
* surveillance
* robotics

---

## 🔀 6️⃣ Multimodal Data (Modern AI)

### 📘 What it is

Multiple modalities together:

* text + image
* image + audio
* text + video

---

### 🤖 Why Multimodal AI Matters

Humans understand the world multimodally.

Modern AI tries to:

* align modalities
* share representations

Examples:

* CLIP
* GPT-4V
* Gemini

---

### 💻 Mini Concept Example

```text
Image of cat + "A cat sitting on a sofa"
→ same embedding space
```

---

## 🤯 Why Multimodal AI Is Hard

| Problem   | Reason                    |
| --------- | ------------------------- |
| Alignment | Different data structures |
| Scale     | Massive datasets          |
| Noise     | Cross-modal ambiguity     |
| Bias      | Uneven modality quality   |

---

## 🧠 Data Complexity vs Model Complexity

Rule of thumb:

* Simple data → simple models
* Complex data → deep models

Wrong pairing = failure.

---

## 🧭 Choosing the Right Modality

Ask:

1. What signal matters most?
2. What data is available?
3. What errors are acceptable?

Good AI starts with **data choice**.

---

## 🌍 Real-World Mapping

| System           | Modalities             |
| ---------------- | ---------------------- |
| ChatGPT          | Text                   |
| GPT-4V           | Text + Image           |
| Self-driving car | Image + Video + Sensor |
| Voice assistant  | Audio + Text           |

---

## 🧠 Final Big Insight

> **The world is rich.
> Data is a simplified shadow of it.**

Great AI engineers understand the gap.

---

## 🌱 Final Reflection

{{< spoiler text="If you had unlimited compute but poor data, would AI succeed?" >}}
No — data quality dominates.
{{< /spoiler >}}