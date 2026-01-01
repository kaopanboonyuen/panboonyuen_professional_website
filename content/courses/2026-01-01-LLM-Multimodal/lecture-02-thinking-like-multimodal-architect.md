---
title: "Lecture 02 — How to Think Like a Multimodal System Designer"
date: "2026-01-01"
type: book
weight: 20
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~3–4 hours (core system-design lecture)

---

## 🌍 Why This Lecture Matters

Most people learn:
- 📦 APIs
- 🧩 libraries
- ⚙️ frameworks

Very few learn:
> **How to design an intelligent system from first principles.**

This lecture transforms you from:
> *model user* → **multimodal system architect**

---

## 🧠 The Architect’s Mindset

A multimodal architect does **not** ask first:

❌ “Which model should I use?”  

They ask:

✅ What problem am I solving?  
✅ What information is available?  
✅ What modality carries the signal?  
✅ What errors are acceptable?

---

## 🏗️ First Principle #1: Start From the Task, Not the Model

Every intelligent system begins with a **task definition**.

### Ask These Questions (Always)

1. What is the **input**?
2. What is the **output**?
3. What transformation is required?
4. What failure is unacceptable?

---

### Example

**Task:** Medical image diagnosis  

| Aspect | Decision |
|-----|-----|
| Input | Image + text report |
| Output | Text explanation |
| Risk | False negative |
| Requirement | Human-in-the-loop |

---

## 🧪 Knowledge Check — Task Thinking

### Q1 (Objective)
Why should task definition come before model selection?

{{< spoiler text="Answer" >}}
Because architecture depends on constraints, risk, and signal — not tools.
{{< /spoiler >}}

---

## 🧠 First Principle #2: Modalities Are Information Channels

Each modality has **strengths and weaknesses**.

| Modality | Strength | Weakness |
|-------|--------|--------|
| Text | Reasoning | No raw perception |
| Image | Spatial | No abstraction |
| Audio | Emotion, tone | Noise |
| Video | Time | Cost & complexity |

> **Good design uses the minimum modality required.**

---

## ❌ Over-Engineering Trap (Very Common)

Many beginners think:
> “More modalities = smarter AI”

Reality:
> **More modalities = more noise, cost, and failure modes**

---

## 🧪 Knowledge Check — Modalities

### Q2 (MCQ)
Which modality is the most expensive to annotate?

A) Text  
B) Image  
C) Audio  
D) Video  

{{< spoiler text="Correct Answer" >}}
D) Video
{{< /spoiler >}}

---

## 🧠 First Principle #3: Separate Perception from Reasoning

One of the **most important design rules**.

### Correct Separation

```

Perception → Representation → Reasoning → Action

```

- Perception = encoders
- Reasoning = LLM
- Action = output or tool use

---

### Why This Matters

If you mix everything:
- debugging becomes impossible
- errors propagate
- evaluation is unclear

> **Clean boundaries create reliable systems.**

---

## 🧪 Knowledge Check — Architecture

### Q3 (True / False)
Vision models should handle logical reasoning.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

## 🧠 First Principle #4: Alignment Is the Bottleneck

Alignment answers:
> **How does non-language data become “thinkable”?**

Bad alignment →
- hallucinations
- irrelevant answers
- false confidence

Good alignment →
- reasoning
- grounding
- generalization

---

## 🧩 Alignment Design Choices

| Method | When to Use |
|-----|-----|
| Linear projection | Simple tasks |
| MLP | Moderate complexity |
| Cross-attention | High alignment need |
| Q-Former | Vision-language fusion |

---

## 🧪 Knowledge Check — Alignment

### Q4 (MCQ)
Which component most directly affects hallucination?

A) Tokenizer  
B) Alignment layer  
C) GPU size  
D) Dataset size  

{{< spoiler text="Correct Answer" >}}
B) Alignment layer
{{< /spoiler >}}

---

## 🧠 First Principle #5: Think in Pipelines, Not Models

Architects think in **pipelines**.

### Example: Image Question Answering

```

Image → Vision Encoder
Question → Text Encoder
↓
Alignment
↓
LLM
↓
Answer

```

Each box is:
- replaceable
- testable
- improvable

---

## 🧪 Knowledge Check — Pipeline Thinking

### Q5 (Objective)
Why should components be modular?

{{< spoiler text="Answer" >}}
To allow debugging, replacement, and independent improvement.
{{< /spoiler >}}

---

## 🧠 Beginner → Advanced Design Levels

| Level | Focus |
|----|----|
| Beginner | Single modality |
| Intermediate | Multimodal fusion |
| Advanced | RAG + tools |
| Expert | Agents + feedback loops |

You **do not** jump levels.

---

## 🧠 Case Study 1 — Image Captioning

### Design Decision

| Choice | Reason |
|----|----|
| Frozen vision encoder | Stability |
| Small projection | Efficiency |
| Pretrained LLM | Reasoning |

> This works because **task complexity is low**.

---

## 🧠 Case Study 2 — Medical VQA (High Risk)

Changes:
- HITL required
- Conservative decoding
- Explanation mandatory

> **Risk changes architecture.**

---

## 🧪 Knowledge Check — Risk Awareness

### Q6 (True / False)
The same architecture fits both chatbots and medical diagnosis.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

## 🧠 First Principle #6: Evaluation Shapes Design

If you can’t measure it:
> **You can’t trust it.**

Evaluation informs:
- architecture choice
- data needs
- alignment method

(We go deep in Lecture 09.)

---

## 🧠 Thinking Beyond Accuracy

Architects evaluate:
- robustness
- calibration
- failure modes
- ethical impact

---

## 🧪 Knowledge Check — Evaluation Thinking

### Q7 (Objective)
Why is accuracy alone insufficient?

{{< spoiler text="Answer" >}}
Because it hides bias, uncertainty, and rare failures.
{{< /spoiler >}}

---

## 🧠 Architect’s Checklist (Very Practical)

Before coding, ask:

- [ ] Is this modality necessary?
- [ ] Is language the reasoning layer?
- [ ] Is alignment explicit?
- [ ] Are risks identified?
- [ ] Can humans intervene?

---

## 🌱 Human-Centered Design (Core Philosophy)

Multimodal AI should:
- assist humans
- explain decisions
- accept correction

> **Architects design for humility, not dominance.**

---

## 🧪 Final Knowledge Check — Reflection

{{< spoiler text="What separates an AI architect from a model user?" >}}
System-level thinking, responsibility, and first-principle design.
{{< /spoiler >}}

---

## ✅ Final Takeaways

- Architects start from tasks
- Modalities are information channels
- Alignment is critical
- Pipelines beat monoliths
- Ethics influence architecture

---

## 🌍 Final Reflection

{{< spoiler text="If AI systems fail, who is responsible?" >}}
The humans who designed them.
{{< /spoiler >}}

---