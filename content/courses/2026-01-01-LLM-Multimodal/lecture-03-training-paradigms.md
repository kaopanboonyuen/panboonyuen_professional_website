---
title: "Lecture 03 — Training Paradigms: Pretraining, Fine-tuning, and Training from Scratch"
date: "2026-01-01"
type: book
weight: 30
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~3–4 hours (core learning lecture)

---

## 🌍 Why This Lecture Matters

Every modern AI system answers **one critical question**:

> **How was this intelligence created?**

Understanding *training paradigms* means understanding:
- capability
- limitation
- cost
- risk
- ethics

This lecture teaches you **how intelligence is shaped**, not just deployed.

---

## 🧠 The Three Ways Machines Learn

All modern multimodal systems are trained using **one (or more)** of these paradigms:

1. 🧱 Training from Scratch  
2. 🔧 Fine-tuning  
3. 🧠 Pretraining (Foundation Models)

---

## 🧩 Big Picture Comparison

| Paradigm | Data Size | Cost | Flexibility | Risk |
|-------|----------|------|------------|------|
| Scratch | Massive | 💰💰💰💰 | High | Very High |
| Pretraining | Huge | 💰💰💰 | Medium | Medium |
| Fine-tuning | Small–Medium | 💰 | Low–Medium | Low |

> **Most real systems use pretrained + fine-tuned models.**

---

## 🧱 Paradigm 1 — Training From Scratch

### What It Means

Training **all weights from random initialization**.

No prior knowledge.
No shortcuts.

---

### When It Makes Sense (Rare)

- New modality (e.g., brain signals)
- Fundamental research
- Extreme domain shift
- National-scale infrastructure

---

### Why It’s Dangerous

- Requires massive data
- Requires massive compute
- High chance of bias
- Easy to fail silently

> **Training from scratch is not bravery — it’s responsibility.**

---

## 🧪 Knowledge Check — Scratch Training

### Q1 (True / False)
Training from scratch is the best choice for most applications.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

### Q2 (Objective)
Name one valid reason to train from scratch.

{{< spoiler text="Answer" >}}
When no pretrained model exists for the modality or domain.
{{< /spoiler >}}

---

## 🧠 Paradigm 2 — Pretraining (Foundation Models)

### What Is Pretraining?

Learning **general-purpose representations** from massive unlabeled or weakly labeled data.

Examples:
- GPT (text)
- CLIP (image–text)
- Whisper (audio)

---

### Why Pretraining Works

Because the world is:
- repetitive
- structured
- statistically learnable

> Pretraining captures **world regularities**.

---

### Multimodal Pretraining

Typical objective:
```

(Image, Text) → Predict missing modality

```

This creates **cross-modal alignment**.

---

## 🧪 Knowledge Check — Pretraining

### Q3 (MCQ)
What is the main goal of pretraining?

A) Task accuracy  
B) Memorization  
C) General representation learning  
D) Deployment speed  

{{< spoiler text="Correct Answer" >}}
C) General representation learning
{{< /spoiler >}}

---

## 🔧 Paradigm 3 — Fine-tuning

### What Is Fine-tuning?

Adapting a pretrained model to:
- a specific task
- a specific domain
- a specific behavior

---

### Types of Fine-tuning

| Type | Description |
|----|------------|
| Full fine-tuning | Update all weights |
| Partial | Update some layers |
| PEFT | LoRA, adapters |
| Instruction tuning | Align behavior |

---

### Why Fine-tuning Is Powerful

- Low data requirement
- Low compute
- Fast iteration
- Safer behavior

> Fine-tuning is **how most intelligence is specialized**.

---

## 🧪 Knowledge Check — Fine-tuning

### Q4 (True / False)
Fine-tuning always requires large datasets.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

### Q5 (Objective)
Why is PEFT (e.g., LoRA) popular?

{{< spoiler text="Answer" >}}
It reduces memory and compute while preserving performance.
{{< /spoiler >}}

---

## 🧠 Pretraining vs Fine-tuning (Mental Model)

Think of a human:

- Pretraining = education
- Fine-tuning = job training
- Scratch = growing up alone on an island

---

## 🧠 Multimodal-Specific Considerations

### What Can Be Fine-tuned?

- Encoders
- Projection layers
- LLM
- Output heads

---

### Common Strategy (Best Practice)

| Component | Strategy |
|--------|--------|
| Encoder | Freeze |
| Projection | Train |
| LLM | PEFT |
| Head | Train |

> **Alignment layers are usually the sweet spot.**

---

## 🧪 Knowledge Check — Multimodal Strategy

### Q6 (MCQ)
Which component is most commonly fine-tuned first?

A) Tokenizer  
B) Vision encoder  
C) Projection layer  
D) Dataset  

{{< spoiler text="Correct Answer" >}}
C) Projection layer
{{< /spoiler >}}

---

## ⚠️ Overfitting & Catastrophic Forgetting

Fine-tuning risks:
- forgetting general knowledge
- over-specialization
- bias amplification

Mitigations:
- low learning rate
- freezing layers
- mixed data

---

## 🧠 Paradigm Comparison by Task

| Task | Best Paradigm |
|----|----|
| Image captioning | Pretrained + light FT |
| Medical QA | FT + HITL |
| New sensor modality | Scratch |
| Internal company data | RAG or FT |

---

## 🧪 Knowledge Check — Decision Making

### Q7 (Objective)
Why might RAG be preferred over fine-tuning?

{{< spoiler text="Answer" >}}
When knowledge changes frequently or data cannot be embedded in weights.
{{< /spoiler >}}

---

## 🧠 Training Is Not Just Optimization

Training choices encode:
- values
- assumptions
- power

> **Who chooses the data chooses the behavior.**

---

## 🌱 Ethical Considerations

- Pretraining data bias
- Fine-tuning reinforcement of norms
- Scratch training without safeguards

Ethics begins **before training starts**.

---

## 🧪 Knowledge Check — Ethics

### Q8 (True / False)
Bias can only be fixed during deployment.

{{< spoiler text="Answer" >}}
False — bias enters during data and training.
{{< /spoiler >}}

---

## 🧠 Architect’s Decision Tree (Practical)

Ask:

1. Is there a pretrained model?
2. Is the domain stable?
3. Is data private?
4. Is behavior critical?

Then choose:
- RAG
- Fine-tuning
- Scratch (rare)

---

## ✅ Final Takeaways

- Training defines intelligence
- Pretraining builds foundations
- Fine-tuning specializes behavior
- Scratch training is exceptional
- Ethics is embedded in data

---

## 🌍 Final Reflection

{{< spoiler text="If a model learns from biased data, who is accountable?" >}}
The humans who selected, curated, and approved the data.
{{< /spoiler >}}

---