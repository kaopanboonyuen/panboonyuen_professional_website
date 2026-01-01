---
title: "Lecture 07 — Visual Question Answering (VQA) & Document Question Answering (DocQA)"
date: "2026-01-01"
type: book
weight: 70
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~4–5 hours (applied multimodal reasoning)

---

## 👁️📄 Why VQA & DocQA Matter to Humanity

> **VQA & DocQA turn perception into understanding.**

They allow machines to:
- 👁️ See
- 📄 Read
- ❓ Understand questions
- 🧠 Reason
- ✍️ Answer *grounded in evidence*

This is the foundation of:
- Assistive AI
- Education AI
- Legal & medical AI
- Scientific discovery
- Accessibility technology

---

## 🧠 What Is Visual Question Answering (VQA)?

**Input**
- 🖼 Image
- ❓ Natural language question

**Output**
- ✍️ Text answer grounded in the image

Example:
> **Q:** “How many people are wearing helmets?”  
> **A:** “Two.”

---

## 🧠 What Is Document Question Answering (DocQA)?

**Input**
- 📄 Document image / PDF
- ❓ Question

**Output**
- ✍️ Answer extracted or reasoned from the document

Example:
> **Q:** “What is the invoice total?”  
> **A:** “$1,245.50”

---

## 🔍 VQA vs DocQA (Key Differences)

| Aspect | VQA | DocQA |
|----|----|----|
| Main Challenge | Visual reasoning | Text + layout understanding |
| Precision | Often coarse | Extremely precise |
| OCR Required | Optional | Mandatory |
| Hallucination Risk | Medium | Very high |
| Evaluation | Semantic | Exact match critical |

> **DocQA punishes mistakes much harder than VQA.**

---

## 🧠 Cognitive Skills Required

Both tasks require:
- Visual grounding
- Cross-modal alignment
- Reasoning
- Attention control

But DocQA adds:
- Layout reasoning
- Reading order
- Table understanding
- Key-value extraction

---

## 🧱 Canonical Architecture (Unified View)

```

Image / Document
↓
Vision Encoder (ViT / CNN)
↓
OCR (DocQA only)
↓
Layout / Spatial Encoder
↓
Cross-Attention Fusion
↓
LLM Reasoning
↓
Text Answer

````

---

## 👁️ Vision Encoding

Common backbones:
- ViT
- Swin Transformer
- CNN + FPN

Key requirement:
> Preserve **spatial information**

---

## 🔤 OCR Is NOT Optional for DocQA

OCR extracts:
- Text
- Bounding boxes
- Confidence scores

Popular OCR tools:
- Tesseract
- PaddleOCR
- EasyOCR
- TrOCR (Transformer-based)

> **Bad OCR = Impossible DocQA**

---

## 🧭 Layout Understanding (CRITICAL)

Documents are not sentences — they are **spatial graphs**.

### Layout Features
- X, Y coordinates
- Width / height
- Reading order
- Font size / style

Models:
- LayoutLM
- LayoutLMv3
- DocFormer

---

## 🧠 Reasoning Types in VQA & DocQA

### VQA Reasoning
- Counting
- Spatial (“left of”, “behind”)
- Attribute recognition
- Commonsense

### DocQA Reasoning
- Lookup
- Aggregation
- Comparison
- Multi-hop reasoning

---

## 🐍 Python: Simple VQA Pipeline

```python
image = load_image("scene.jpg")
question = "How many cars are parked?"

vision_features = vision_encoder(image)
answer = llm.generate(
    visual_features=vision_features,
    prompt=question
)

print(answer)
````

---

## 🐍 Python: DocQA Pipeline (Conceptual)

```python
doc_image = load_image("invoice.png")
ocr_tokens, boxes = ocr_engine(doc_image)

doc_embedding = layout_encoder(ocr_tokens, boxes)

answer = llm.generate(
    document_embedding=doc_embedding,
    prompt="What is the total amount?"
)
```

---

## 🧠 Prompt Engineering for VQA & DocQA

Bad prompt:

> “Answer the question.”

Good prompt:

> “Answer using only visible evidence. If uncertain, say ‘Not found’.”

> **Prompt discipline reduces hallucination.**

---

## 🧪 Datasets (Must-Know)

### VQA

* VQA v2
* GQA
* CLEVR (synthetic reasoning)

### DocQA

* DocVQA
* FUNSD
* RVL-CDIP
* CORD

---

## 📏 Evaluation Metrics

### VQA

* Accuracy
* Consensus-based scoring

### DocQA

* Exact Match (EM)
* F1 score
* String normalization critical

> **One wrong digit = wrong answer**

---

## ⚠️ Hallucination: The Silent Killer

Common failure cases:

* Answering from prior knowledge
* Guessing missing fields
* Confusing similar layouts

Mitigation:

* Evidence-aware prompting
* Answer verification
* Human-in-the-loop (later lecture)

---

## 🧠 Research Insight

> DocQA is closer to **symbolic reasoning** than vision.

Strong DocQA models:

* Behave more like databases
* Require constraint enforcement
* Prefer abstention over guessing

---

## 🧪 Student Knowledge Check (Hidden Answers)

### Q1 — Objective

What extra component does DocQA require compared to VQA?

{{< spoiler text="Answer" >}}
OCR and layout understanding.
{{< /spoiler >}}

---

### Q2 — MCQ

Which model explicitly encodes layout?

A. CLIP
B. ViT
C. LayoutLM
D. ResNet

{{< spoiler text="Answer" >}}
C. LayoutLM
{{< /spoiler >}}

---

### Q3 — MCQ

Which metric is most important for DocQA?

A. BLEU
B. ROUGE
C. Exact Match
D. Perplexity

{{< spoiler text="Answer" >}}
C. Exact Match
{{< /spoiler >}}

---

### Q4 — Objective

Why is hallucination more dangerous in DocQA?

{{< spoiler text="Answer" >}}
Because answers must be exact and legally or financially correct.
{{< /spoiler >}}

---

### Q5 — Objective

What is layout reasoning?

{{< spoiler text="Answer" >}}
Understanding text based on spatial structure, not just content.
{{< /spoiler >}}

---

## 🌱 Final Reflection

{{< spoiler text="If AI can read documents perfectly, what must humans still verify?" >}}
Truth, intent, context, and ethical consequences.
{{< /spoiler >}}

---

## ✅ Key Takeaways

* VQA = visual reasoning
* DocQA = precision reasoning
* OCR quality defines upper bound
* Layout is intelligence
* Abstaining is better than hallucinating

---