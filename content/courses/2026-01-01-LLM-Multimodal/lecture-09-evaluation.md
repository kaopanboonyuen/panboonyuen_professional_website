---
title: "Lecture 09 — Evaluation of Multimodal & Agentic AI Systems"
date: "2026-01-01"
type: book
weight: 90
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~4–6 hours (advanced, critical thinking lecture)

---

## 🧠 Why Evaluation Is the Hardest Problem in AI

> **If you cannot evaluate it, you do not understand it.**

Modern AI systems:
- Generate free-form text
- Reason over images, videos, documents
- Use tools
- Act autonomously

❓ So how do we measure *correctness*, *reasoning*, *safety*, and *usefulness*?

> **Evaluation is harder than training.**

---

## ⚠️ The Evaluation Crisis

Common mistakes:
- Using only BLEU / ROUGE
- Evaluating language but not reasoning
- Ignoring hallucination
- No human evaluation
- No failure analysis

> **High benchmark scores ≠ trustworthy intelligence**

---

## 🧩 What Are We Actually Evaluating?

Evaluation must answer **what kind of intelligence** we care about.

| Dimension | Question |
|----|----|
| Accuracy | Is the answer correct? |
| Grounding | Is it supported by evidence? |
| Reasoning | Are the steps valid? |
| Robustness | Does it fail gracefully? |
| Safety | Is it harmful or biased? |
| Usefulness | Does it help a human? |

---

## 🧠 Evaluation by Task Type

### 📝 Text-only LLMs
- Fluency
- Factuality
- Reasoning
- Consistency

### 🖼 Image–Text
- Visual grounding
- Hallucination
- Spatial correctness

### 🎥 Video–Text
- Temporal reasoning
- Event ordering
- Causal understanding

### 📄 DocQA
- Exact match
- Numerical accuracy
- Layout grounding

### 🤖 Agents
- Task success
- Tool correctness
- Efficiency
- Safety

---

## 📏 Automatic Metrics (Know Their Limits)

### Text Metrics

| Metric | Measures | Limitation |
|----|----|----|
| BLEU | N-gram overlap | Bad for reasoning |
| ROUGE | Recall | Shallow |
| METEOR | Semantic match | Still surface-level |
| Perplexity | Fluency | Not correctness |

> **Text similarity ≠ truth**

---

## 📏 Vision-Language Metrics

| Metric | Task |
|----|----|
| Accuracy | VQA |
| CIDEr | Captioning |
| IoU | Grounding |
| Recall@K | Retrieval |

Problems:
- Sensitive to wording
- Miss reasoning errors
- Encourage shortcut learning

---

## 🧠 Faithfulness & Grounding Evaluation

Key question:
> *Did the model use the provided evidence?*

Techniques:
- Attribution checks
- Citation verification
- Evidence overlap
- Counterfactual prompts

---

## 🧪 Hallucination Evaluation (CRITICAL)

Hallucination types:
- Factual hallucination
- Visual hallucination
- Temporal hallucination
- Tool hallucination

Detection:
- Human labeling
- Rule-based checks
- Retrieval consistency
- Self-verification prompts

---

## 👥 Human Evaluation (Gold Standard)

Humans evaluate:
- Correctness
- Clarity
- Trustworthiness
- Helpfulness
- Harm

Best practices:
- Multiple annotators
- Clear rubrics
- Inter-annotator agreement
- Blind comparison

> **Humans evaluate meaning, not tokens.**

---

## 🧠 Evaluation of Reasoning

Bad evaluation:
> “Is the final answer correct?”

Good evaluation:
- Are intermediate steps valid?
- Are assumptions reasonable?
- Is reasoning grounded?

Techniques:
- Chain-of-thought review
- Step-by-step scoring
- Error categorization

---

## 🤖 Evaluating Agents Is Different

Agents are:
- Non-deterministic
- Multi-step
- Tool-dependent

Metrics:
- Task completion rate
- Number of steps
- Cost
- Error recovery
- Safety violations

---

## 🐍 Python: Simple Evaluation Loop

```python
results = []

for example in dataset:
    prediction = model(example.input)
    score = evaluate(prediction, example.answer)
    results.append(score)

print(sum(results) / len(results))
````

> **Simple code, deep thinking required.**

---

## 🧠 Benchmark vs Reality

Benchmarks:

* Controlled
* Clean
* Known distribution

Reality:

* Messy
* Ambiguous
* Adversarial
* High stakes

> **Always test on your own data.**

---

## ⚠️ Overfitting to Benchmarks

Symptoms:

* SOTA on paper
* Poor real-world behavior
* Fragile prompts
* Dataset leakage

Cure:

* Diverse evaluation
* Stress testing
* Out-of-distribution tests

---

## 🧠 Research Insight

> The future of evaluation is **interactive, human-centered, and continuous**.

Trends:

* LLM-as-judge (with caution)
* Hybrid human–AI evaluation
* Online evaluation in deployment
* Value-aligned metrics

---

## 🧪 Student Knowledge Check (Hidden)

### Q1 — Objective

Why are BLEU/ROUGE insufficient for modern AI?

{{< spoiler text="Answer" >}}
They measure surface similarity, not reasoning or truth.
{{< /spoiler >}}

---

### Q2 — MCQ

Which is the gold standard for evaluation?

A. Automatic metrics
B. Benchmarks
C. Human evaluation
D. Leaderboards

{{< spoiler text="Answer" >}}
C. Human evaluation
{{< /spoiler >}}

---

### Q3 — MCQ

Which is most important for DocQA?

A. Fluency
B. Creativity
C. Exact Match
D. Perplexity

{{< spoiler text="Answer" >}}
C. Exact Match
{{< /spoiler >}}

---

### Q4 — Objective

What is hallucination?

{{< spoiler text="Answer" >}}
Producing confident but unsupported or false information.
{{< /spoiler >}}

---

### Q5 — Objective

Why is agent evaluation harder?

{{< spoiler text="Answer" >}}
Because agents are multi-step, non-deterministic, and tool-dependent.
{{< /spoiler >}}

---

## 🌱 Final Reflection

{{< spoiler text="If an AI scores high but harms people, is it a good model?" >}}
No — evaluation must include human values and impact.
{{< /spoiler >}}

---

## ✅ Key Takeaways

* Evaluation defines intelligence
* Automatic metrics are tools, not truth
* Grounding matters more than fluency
* Human judgment is essential
* Ethics begins at evaluation

---