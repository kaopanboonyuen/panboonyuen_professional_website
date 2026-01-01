---
title: "Lecture 05 — Image ↔ Text: Teaching Machines to See and Reason"
date: "2026-01-01"
type: book
weight: 50
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~5 hours (core multimodal lecture)

---

## 🌍 Why Image–Text Is So Important

Vision is the **dominant human sense**.

Images contain:
- spatial structure
- objects
- relationships
- context
- ambiguity

Teaching machines to **see and explain** is one of the hardest problems in AI.

> **Seeing is easy. Understanding is hard.**

---

## 🧠 What Is an Image–Text Multimodal System?

An **Image–Text-to-Text** system takes:
- 🖼 an image
- ✍️ optional text (question, instruction)
- 🧠 performs reasoning
- 🗣 produces text

Examples:
- Image captioning
- Visual Question Answering (VQA)
- Image-based reasoning
- Medical imaging reports
- Autonomous perception explanations

---

## 🧩 High-Level Architecture

```

Image
↓
Vision Encoder (ViT / CNN)
↓
Projection / Alignment
↓
LLM (Reasoning)
↓
Text Output

```

Key idea:
> **Vision models perceive. LLMs reason.**

---

## 🧠 Why Vision Alone Is Not Enough

Vision models are great at:
- detecting patterns
- recognizing objects
- learning spatial features

But they struggle with:
- logic
- explanation
- abstraction
- causality

> **Images do not reason. Language does.**

---

## 🧪 Knowledge Check — Fundamentals

### Q1 (True / False)
A vision model alone can perform logical reasoning.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

## 🧠 Core Image–Text Tasks

| Task | Input | Output |
|----|----|----|
| Image Captioning | Image | Text |
| VQA | Image + Question | Answer |
| Grounding | Image + Text | Region |
| Image QA | Image | Explanation |
| OCR + Reasoning | Image | Text + Answer |

This lecture focuses on **captioning + VQA**.

---

## 👁 Vision Encoders (The Eyes)

Popular encoders:
- ResNet (CNN-based)
- Vision Transformer (ViT)
- Swin Transformer
- ConvNeXt

They convert pixels → embeddings.

---

## 🧠 Vision Encoder Output

```

Image → Patch embeddings → Sequence of vectors

```

Each patch represents **local visual semantics**.

---

## 🧪 Knowledge Check — Vision

### Q2 (MCQ)
Which model introduced patch-based vision processing?

A) ResNet  
B) YOLO  
C) ViT  
D) AlexNet  

{{< spoiler text="Correct Answer" >}}
C) ViT
{{< /spoiler >}}

---

## 🧠 The Alignment Problem (CRITICAL)

Vision embeddings ≠ language embeddings.

Alignment answers:
> **How does a pixel become a word?**

---

## 🧩 Alignment Strategies

| Strategy | Description |
|----|----|
| Linear projection | Simple, efficient |
| MLP | Nonlinear mapping |
| Cross-attention | Deep fusion |
| Q-Former | Learned query alignment |

> **Most failures come from poor alignment.**

---

## 🧪 Knowledge Check — Alignment

### Q3 (Objective)
What is the purpose of the projection layer?

{{< spoiler text="Answer" >}}
To map vision embeddings into the language embedding space.
{{< /spoiler >}}

---

## 🧠 CLIP — A Foundational Breakthrough

CLIP learned:
```

Image ↔ Text similarity

````

By contrastive learning:
- match image with correct caption
- separate mismatched pairs

Result:
> **Shared semantic space**

---

## 🧪 Knowledge Check — CLIP

### Q4 (MCQ)
What learning paradigm does CLIP use?

A) Supervised classification  
B) Reinforcement learning  
C) Contrastive learning  
D) Autoencoding  

{{< spoiler text="Correct Answer" >}}
C) Contrastive learning
{{< /spoiler >}}

---

## 🐍 Python Lab 1 — Image Captioning with BLIP

### 📦 Install Dependencies

```bash
pip install transformers pillow torch torchvision
````

---

### 🧠 Load Model

```python
from transformers import BlipProcessor, BlipForConditionalGeneration
from PIL import Image

model_name = "Salesforce/blip-image-captioning-base"

processor = BlipProcessor.from_pretrained(model_name)
model = BlipForConditionalGeneration.from_pretrained(model_name)
```

---

### 🖼 Load Image

```python
image = Image.open("example.jpg").convert("RGB")
```

---

### ✍️ Generate Caption

```python
inputs = processor(image, return_tensors="pt")

out = model.generate(**inputs, max_new_tokens=50)

caption = processor.decode(out[0], skip_special_tokens=True)
print(caption)
```

> 🎉 You just taught a machine to describe what it sees.

---

## 🧪 Knowledge Check — Code

### Q5 (Objective)

What role does the processor play in BLIP?

{{< spoiler text="Answer" >}}
It preprocesses images and decodes generated tokens.
{{< /spoiler >}}

---

## 🧠 Adding Reasoning with an LLM

Captioning ≠ understanding.

We add an LLM to:

* answer questions
* infer relationships
* explain scenes

---

## 🏗 Full Image–Text Reasoning Pipeline

```
Image → Vision Encoder → Alignment → LLM → Answer
```

Optional:

```
+ Question
```

---

## 🐍 Python Lab 2 — Visual Question Answering

```python
question = "What is the person doing in the image?"

prompt = f"""
You are a vision-language assistant.
Image description:
{caption}

Question:
{question}
"""

from transformers import AutoTokenizer, AutoModelForCausalLM

llm_name = "meta-llama/Llama-3-8B-Instruct"

tokenizer = AutoTokenizer.from_pretrained(llm_name)
llm = AutoModelForCausalLM.from_pretrained(llm_name)

inputs = tokenizer(prompt, return_tensors="pt")
outputs = llm.generate(**inputs, max_new_tokens=100)

answer = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(answer)
```

---

## 🧪 Knowledge Check — Reasoning

### Q6 (True / False)

Image captioning alone is sufficient for VQA.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

## 🧠 Common Failure Modes

* Hallucinated objects
* Missed small details
* Incorrect spatial relations
* Cultural bias
* Overconfidence

> **Seeing ≠ understanding ≠ truth**

---

## 🧪 Knowledge Check — Failures

### Q7 (MCQ)

Which failure is most dangerous?

A) Slow inference
B) Hallucinated objects
C) Low resolution
D) Long captions

{{< spoiler text="Correct Answer" >}}
B) Hallucinated objects
{{< /spoiler >}}

---

## 🧠 Evaluation Metrics

| Metric       | Use                    |
| ------------ | ---------------------- |
| BLEU / CIDEr | Caption quality        |
| VQA Accuracy | QA correctness         |
| Human Eval   | Trust & clarity        |
| Calibration  | Confidence reliability |

---

## 🧪 Knowledge Check — Evaluation

### Q8 (Objective)

Why is human evaluation important for vision-language tasks?

{{< spoiler text="Answer" >}}
Because correctness depends on semantics and human perception.
{{< /spoiler >}}

---

## 🌱 Ethics in Vision–Language AI

Risks:

* surveillance
* facial recognition abuse
* bias in datasets
* privacy violation

> **If a machine sees people, it must respect humanity.**

---

## 🧪 Knowledge Check — Ethics

### Q9 (True / False)

Image–text systems can be ethically neutral.

{{< spoiler text="Answer" >}}
False.
{{< /spoiler >}}

---

## 🧠 Human-in-the-Loop (Best Practice)

* Human review for sensitive outputs
* Confidence thresholds
* Explainable responses
* Feedback-based refinement

---

## ✅ Final Takeaways

* Vision provides perception
* Language provides reasoning
* Alignment is the hardest part
* Python pipelines are modular
* Ethics is not optional

---

## 🌍 Final Reflection

{{< spoiler text="If a machine describes a human incorrectly, who is harmed?" >}}
The human — therefore responsibility lies with designers.
{{< /spoiler >}}

---