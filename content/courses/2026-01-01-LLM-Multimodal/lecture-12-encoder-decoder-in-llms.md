---
title: "Lecture 12 — Encoder, Decoder, and the Truth About How LLMs Are Trained"
date: "2026-01-01"
type: book
weight: 120
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~4–5 hours (core understanding lecture)

---

## 🧠 Why This Lecture Exists

> **Almost everyone uses LLMs.  
Very few understand how they are actually built.**

Common confusion:
- “Is ChatGPT encoder–decoder?”
- “Why only decoder?”
- “What does freezing weights really mean?”
- “How does multimodal fit into this?”
- “What exactly am I training when I fine-tune?”

This lecture answers **all of that — clearly, from first principles**.

---

## 🧩 The Original Transformer (2017)

The original Transformer had **two parts**:

```

Encoder  →  Decoder

```

### Encoder
- Reads the input
- Understands meaning
- Produces representations

### Decoder
- Generates output tokens
- Uses attention + autoregression

This was designed for:
- Machine Translation
- Summarization
- Seq2Seq tasks

---

## 🧠 Encoder: What Is It Really Doing?

Encoder properties:
- Sees the **entire input at once**
- Bidirectional attention
- Builds rich representations
- Does **not generate text**

Examples:
- BERT
- RoBERTa
- ViT (vision encoder)
- Audio encoders

> **Encoders understand. They don’t speak.**

---

## 🧠 Decoder: What Is It Really Doing?

Decoder properties:
- Generates tokens **one by one**
- Causal (masked) attention
- Autoregressive
- Can reason, plan, and explain

Examples:
- GPT
- LLaMA
- Mistral
- Qwen

> **Decoders speak, reason, and act.**

---

## ❓ Why ChatGPT Is Decoder-Only

Key insight:

> **If you want open-ended generation, you only need a decoder.**

Reasons:
- Decoder can read context (prompt)
- Decoder can generate indefinitely
- Encoder is not required for generation
- Simpler architecture
- Scales better

So ChatGPT is:

```

Text → Decoder → Next Token → Next Token → ...

````

---

## 🧠 Decoder-Only Training (GPT Style)

Training objective:

> **Predict the next token**

```text
"I love deep" → predict "learning"
````

This single objective leads to:

* Language understanding
* Reasoning
* Code generation
* Planning

> **Understanding emerges from generation.**

---

## 🧩 Encoder–Decoder Models (Still Important!)

Encoder–decoder models are still used when:

* Input ≠ output
* Strong alignment is required
* Input is very long or structured

Examples:

* T5
* FLAN-T5
* Whisper (audio → text)
* Translation systems

---

## 🧠 Multimodal LLMs: The Hybrid Truth

Most multimodal LLMs are:

```
Encoder (image/audio/video)
        ↓
Projection / Adapter
        ↓
Decoder-only LLM
```

Examples:

* CLIP → LLaMA
* ViT → GPT
* Audio encoder → LLM

> **Multimodal models are encoder–decoder systems,
> but the decoder is still the brain.**

---

## 🔗 Why Encoders Are Usually Frozen

Encoders:

* Pretrained on massive data
* Expensive to retrain
* General-purpose

So we often:

* ❄️ Freeze encoder
* 🔧 Train adapter / projector
* 🧠 Fine-tune decoder lightly

This saves:

* Compute
* Data
* Stability

---

## 🧠 What Is Actually Trained? (Very Important)

### Pretraining

* Train **all weights**
* Massive data
* Extremely expensive

### Fine-tuning

* Train **some weights**
* Task-specific data

### Instruction tuning

* Train decoder to follow instructions
* Often freezes most layers

---

## 🧩 Freezing Strategies

| Strategy       | What Moves          |
| -------------- | ------------------- |
| Full fine-tune | Everything          |
| Freeze encoder | Decoder only        |
| LoRA           | Small rank matrices |
| Adapters       | Tiny modules        |
| Prompt tuning  | No weights          |

> **Most real-world systems do NOT full fine-tune.**

---

## 🐍 Example: Freezing Encoder

```python
for param in vision_encoder.parameters():
    param.requires_grad = False
```

Then train:

* Projection layer
* LLM LoRA weights

---

## 🧠 LoRA Explained Simply

LoRA:

* Injects low-rank matrices
* Keeps original weights frozen
* Learns task-specific behavior

Benefits:

* Cheap
* Stable
* Shareable
* Reversible

> **LoRA is how the world fine-tunes LLMs today.**

---

## ❓ Why Not Encoder-Only LLMs?

Encoder-only models:

* Cannot generate freely
* Need a decoder for output
* Not conversational

That’s why:

* BERT ≠ ChatGPT
* ViT ≠ multimodal assistant

---

## 🧠 Mental Model (Remember This Forever)

| Role       | Model Type      |
| ---------- | --------------- |
| Understand | Encoder         |
| Reason     | Decoder         |
| Speak      | Decoder         |
| Act        | Decoder + Tools |
| See        | Vision Encoder  |
| Hear       | Audio Encoder   |

---

## 🧪 Student Knowledge Check (Hidden)

### Q1 — Objective

Why can ChatGPT work without an encoder?

{{< spoiler text="Answer" >}}
Because a decoder can read context and generate text autoregressively.
{{< /spoiler >}}

---

### Q2 — MCQ

Which model is encoder-only?

A. GPT
B. LLaMA
C. BERT
D. ChatGPT

{{< spoiler text="Answer" >}}
C. BERT
{{< /spoiler >}}

---

### Q3 — MCQ

What is usually frozen in multimodal LLMs?

A. Decoder
B. Encoder
C. Tokenizer
D. Loss function

{{< spoiler text="Answer" >}}
B. Encoder
{{< /spoiler >}}

---

### Q4 — Objective

Why use LoRA instead of full fine-tuning?

{{< spoiler text="Answer" >}}
To reduce cost, preserve knowledge, and improve stability.
{{< /spoiler >}}

---

### Q5 — Objective

Who is the “brain” of a multimodal LLM?

{{< spoiler text="Answer" >}}
The decoder-only LLM.
{{< /spoiler >}}

---

## 🌱 Final Reflection

{{< spoiler text="If intelligence emerges from predicting the next token, what does that say about human thinking?" >}}
That reasoning may emerge from sequence prediction guided by experience.
{{< /spoiler >}}

---

## ✅ Final Takeaways (Burn This In)

* ChatGPT is **decoder-only**
* Encoders understand, decoders generate
* Multimodal = encoders + decoder brain
* Freezing is strategy, not weakness
* Fine-tuning is about *what to move*

---