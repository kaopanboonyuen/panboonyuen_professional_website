---
title: "Lecture 08 — RAG, AI Agents & Agentic Multimodal Systems"
date: "2026-01-01"
type: book
weight: 80
---

<!--more-->

{{< icon name="clock" pack="fas" >}} ~4–6 hours (modern AI systems design)

---

## 🧠 Why This Lecture Changes Everything

> **Models are not intelligent alone.  
Systems are.**

RAG and AI Agents represent a shift:
- ❌ From static models  
- ✅ To *interactive, grounded, tool-using intelligence*

This lecture connects:
- LLMs
- Multimodality
- Memory
- Tools
- Reasoning
- Real-world deployment

---

## 🧩 What Is Retrieval-Augmented Generation (RAG)?

**RAG = Knowledge + Reasoning**

Instead of forcing the model to:
- memorize everything
- hallucinate confidently

We let it:
1. Retrieve relevant information
2. Reason over it
3. Generate grounded answers

---

## 🔁 Classical LLM vs RAG

| Aspect | Classical LLM | RAG |
|----|----|----|
| Knowledge | Frozen | Dynamic |
| Hallucination | High | Lower |
| Updates | Retrain | Re-index |
| Traceability | Poor | Strong |
| Enterprise-ready | ❌ | ✅ |

> **RAG turns LLMs into “open-book thinkers.”**

---

## 🧠 Core RAG Pipeline

```

User Query
↓
Embedding
↓
Retriever (Vector DB)
↓
Relevant Context
↓
LLM Reasoning
↓
Answer + Citations

````

---

## 📦 What Can Be Retrieved?

- 📄 Documents
- 🖼 Images
- 🎥 Videos
- 🧾 Tables
- 📊 Logs
- 🧠 Memories (Agent state)

> Multimodal RAG = **cross-modal retrieval + reasoning**

---

## 🧠 Embeddings: The Heart of RAG

Embedding models map meaning → vectors.

Examples:
- Text: sentence-transformers
- Image: CLIP
- Video: InternVideo
- Document: Layout-aware embeddings

> **Good retrieval beats bigger models.**

---

## 🐍 Python: Minimal RAG Example

```python
query = "What is transformer attention?"

q_emb = embedder.encode(query)
docs = vector_db.search(q_emb, top_k=5)

context = "\n".join(docs)

answer = llm.generate(
    prompt=f"Answer using the context below:\n{context}\n\nQuestion:{query}"
)
````

---

## ⚠️ Common RAG Failure Modes

* Retrieving irrelevant chunks
* Context too long
* Context ignored
* Conflicting documents
* Over-trusting retrieved text

Mitigation:

* Chunking strategy
* Reranking
* Instruction tuning
* Answer verification

---

## 🤖 What Is an AI Agent?

> **An agent is an LLM that can act.**

Agent abilities:

* Decide next action
* Use tools
* Store memory
* Observe outcomes
* Iterate

---

## 🧠 Agent Loop (Canonical)

```
Observe → Think → Act → Reflect → Repeat
```

This is **not prompting** — it is **control flow**.

---

## 🧩 Agent Components

| Component | Role            |
| --------- | --------------- |
| LLM       | Reasoning       |
| Memory    | State           |
| Tools     | Actions         |
| Planner   | Decomposition   |
| Executor  | Tool calling    |
| Critic    | Self-evaluation |

---

## 🛠 Tools an Agent Can Use

* Search engines
* Databases
* Code execution
* APIs
* OCR
* Vision models
* File systems

> **Tools extend intelligence beyond tokens.**

---

## 🐍 Python: Simple Agent Skeleton

```python
while not task_done:
    thought = llm.think(state)
    action = planner.select(thought)
    result = tools.run(action)
    state.update(result)
```

---

## 🧠 What Is Agentic AI?

**Agentic AI** means:

* Long-horizon goals
* Autonomous planning
* Self-correction
* Tool orchestration
* Memory persistence

Examples:

* Research agents
* Coding agents
* Multimodal assistants
* Auto-analysts

---

## 🔗 RAG + Agents = Power

RAG answers questions.
Agents **decide what to retrieve and why**.

```
Agent
  ├── Query RAG
  ├── Verify answer
  ├── Ask follow-up
  ├── Use tools
  └── Deliver result
```

> This is how **real AI systems are built today**.

---

## 🧠 Multimodal Agent Example

Task:

> “Analyze this traffic video and explain why the accident occurred.”

Agent flow:

1. Extract video frames
2. Retrieve traffic rules (RAG)
3. Detect events
4. Reason causality
5. Generate explanation

---

## ⚠️ Risks of Agentic Systems

* Tool misuse
* Infinite loops
* Overconfidence
* Hidden failures
* Alignment drift

Mitigation:

* Guardrails
* Cost limits
* Human approval
* Logging
* Evaluation

---

## 📏 Evaluating RAG & Agents

### RAG Evaluation

* Retrieval recall
* Faithfulness
* Answer correctness
* Citation accuracy

### Agent Evaluation

* Task success rate
* Steps efficiency
* Error recovery
* Human satisfaction

---

## 🧠 Research Insight

> Intelligence is no longer **inside the model**
> It is **distributed across systems**

The future:

* Smaller models
* Better retrieval
* Smarter agents
* Human oversight

---

## 🧪 Student Knowledge Check (Hidden)

### Q1 — Objective

What problem does RAG primarily solve?

{{< spoiler text="Answer" >}}
Hallucination and static knowledge.
{{< /spoiler >}}

---

### Q2 — MCQ

Which is NOT a core agent component?

A. Memory
B. Planner
C. Tool interface
D. Dataset labeler

{{< spoiler text="Answer" >}}
D. Dataset labeler
{{< /spoiler >}}

---

### Q3 — MCQ

Why combine RAG with agents?

A. Reduce cost
B. Improve UI
C. Enable decision-driven retrieval
D. Increase model size

{{< spoiler text="Answer" >}}
C. Enable decision-driven retrieval
{{< /spoiler >}}

---

### Q4 — Objective

What is agentic AI?

{{< spoiler text="Answer" >}}
AI systems that plan, act, use tools, and self-correct toward goals.
{{< /spoiler >}}

---

### Q5 — Objective

Why is human oversight important for agents?

{{< spoiler text="Answer" >}}
To prevent unsafe, incorrect, or misaligned actions.
{{< /spoiler >}}

---

## 🌱 Final Reflection

{{< spoiler text="If AI agents can act autonomously, what must humans always control?" >}}
Goals, values, boundaries, and accountability.
{{< /spoiler >}}

---

## ✅ Key Takeaways

* RAG grounds intelligence
* Agents enable action
* Agentic AI is system-level intelligence
* Multimodal agents are the future
* Humans must remain in the loop

---