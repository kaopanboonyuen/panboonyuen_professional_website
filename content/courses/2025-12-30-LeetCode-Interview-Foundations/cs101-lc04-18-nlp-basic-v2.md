---
title: LC-TEST-18 — Basic NLP (V2)
weight: 120
date: '2026-01-01'
type: book
---

## 📘 What Is TF-IDF? (Intuition + Math)

TF-IDF stands for:

> **Term Frequency – Inverse Document Frequency**

It answers **one fundamental NLP question**:

> ❝ Which words are important in this document,  
> compared to the entire collection? ❞

---

## 🧮 The Math (Step by Step)

### 1️⃣ Term Frequency (TF)

How often a word appears **inside one document**.

$$
\text{TF}(w, d) =
\frac{\text{count of } w \text{ in document } d}
{\text{total words in document } d}
$$

👉 Measures **local importance**

---

### 2️⃣ Document Frequency (DF)

How many documents contain the word.

$$
\text{DF}(w) = \text{number of documents containing } w
$$

👉 Measures **how common a word is across documents**

---

### 3️⃣ Inverse Document Frequency (IDF)

Penalizes words appearing in many documents.

$$
\text{IDF}(w) = \log\left(\frac{N}{\text{DF}(w)}\right)
$$

Where:

- $N$ = total number of documents

👉 Measures **global rarity**

---

### 4️⃣ TF-IDF (Final Score)

$$
\text{TF-IDF}(w, d) =
\text{TF}(w, d) \times \text{IDF}(w)
$$

This is the **importance score** used in:
- search engines
- document ranking
- classical NLP systems

---

## 🧪 Worked Example (Very Important)

### Corpus (3 documents)

```text
D1: "messi scores goals"
D2: "goals win matches"
D3: "messi inspires fans"
````

---

### Step 1: Vocabulary

```text
{messi, scores, goals, win, matches, inspires, fans}
```

---

### Step 2: Document Frequency (DF)

| Word     | DF |
| -------- | -- |
| messi    | 2  |
| goals    | 2  |
| scores   | 1  |
| win      | 1  |
| matches  | 1  |
| inspires | 1  |
| fans     | 1  |

---

### Step 3: IDF (Assume natural log)

$$
\text{IDF}(\text{messi}) = \log\left(\frac{3}{2}\right)
$$

$$
\text{IDF}(\text{scores}) = \log\left(\frac{3}{1}\right)
$$

👉 `"scores"` appears in fewer documents
👉 therefore it has **higher IDF**

---

### Step 4: TF-IDF in Document 1

Document 1 contains **3 words**:

```text
messi scores goals
```

| Word   | TF  | IDF      | TF-IDF |
| ------ | --- | -------- | ------ |
| messi  | 1/3 | log(3/2) | low    |
| scores | 1/3 | log(3/1) | HIGH   |
| goals  | 1/3 | log(3/2) | low    |

✅ **"scores" becomes the most important word**

---

## 🎯 What Interviewers Want You To Say

If asked:

> “Explain TF-IDF”

A **perfect answer** is:

> “TF-IDF measures how important a word is to a document
> relative to the whole corpus.
>
> It boosts words that are frequent in one document
> but rare across documents.”

---

## 🔗 Why TF-IDF Still Matters Today

Even in the age of GPT:

* Search engines still use it
* Keyword extraction uses it
* It explains **why attention exists**
* It is the **conceptual ancestor of embeddings**

If you understand TF-IDF deeply,
**transformers feel natural — not magical**.

---

## 🌍 Why This Document Exists

Large Language Models do **not begin with transformers**.

They begin with a simple question:

> “Which words matter?”

TF-IDF is the **bridge** between:
- raw text
- statistics
- semantic meaning

Every NLP engineer **must master this**.

---

# ⚽ Messi & Meaning — A Short Story

Messi touches the ball **less than others**.

Yet every touch **matters more**.

Common words are like defenders:
- they are everywhere
- they mean little

Rare words are like Messi:
- fewer appearances
- massive impact

That is **TF-IDF**.

---

# 🏆 Python NLP — TF-IDF Edition (20 Problems)

Difficulty increases gradually.  
**Do not skip intuition.**

---

## 🟢 TF-IDF 1 — Tokenization

```python
doc = "messi scores beautiful goals"
````

**Task:**
Convert sentence into tokens.

<details>
<summary>✅ Solution</summary>

```python
tokens = doc.split()
print(tokens)
```

</details>

---

## 🟢 TF-IDF 2 — Term Frequency (TF)

**TF(word) = count(word) / total words**

```python
doc = "messi scores goals goals"
```

<details>
<summary>✅ Solution</summary>

```python
words = doc.split()
tf = {}

for w in words:
    tf[w] = tf.get(w, 0) + 1

for w in tf:
    tf[w] /= len(words)

print(tf)
```

</details>

---

## 🟢 TF-IDF 3 — Vocabulary from Corpus

```python
docs = [
  "messi scores goals",
  "goals win matches",
  "messi inspires fans"
]
```

**Task:**
Extract unique vocabulary.

<details>
<summary>✅ Solution</summary>

```python
vocab = set()
for d in docs:
    vocab |= set(d.split())
print(vocab)
```

</details>

---

## 🟡 TF-IDF 4 — Document Frequency (DF)

**DF(word) = number of documents containing word**

<details>
<summary>✅ Solution</summary>

```python
df = {}
for word in vocab:
    df[word] = sum(word in d.split() for d in docs)
print(df)
```

</details>

---

## 🟡 TF-IDF 5 — Inverse Document Frequency (IDF)

**IDF(word) = log(N / DF)**

<details>
<summary>✅ Solution</summary>

```python
import math

N = len(docs)
idf = {w: math.log(N / df[w]) for w in df}
print(idf)
```

</details>

---

## 🟡 TF-IDF 6 — TF-IDF for One Document

<details>
<summary>✅ Solution</summary>

```python
doc = docs[0]
words = doc.split()

tf = {}
for w in words:
    tf[w] = tf.get(w, 0) + 1
for w in tf:
    tf[w] /= len(words)

tfidf = {w: tf[w] * idf[w] for w in tf}
print(tfidf)
```

</details>

---

## 🔵 TF-IDF 7 — Full TF-IDF Matrix

<details>
<summary>✅ Solution</summary>

```python
matrix = []

for d in docs:
    words = d.split()
    tf = {}
    for w in words:
        tf[w] = tf.get(w, 0) + 1
    for w in tf:
        tf[w] /= len(words)

    vec = {w: tf.get(w, 0) * idf[w] for w in vocab}
    matrix.append(vec)

print(matrix)
```

</details>

---

## 🔵 TF-IDF 8 — Important Words in Document

**Task:**
Find top-1 TF-IDF word.

<details>
<summary>✅ Solution</summary>

```python
top = max(tfidf, key=tfidf.get)
print(top)
```

</details>

---

## 🔵 TF-IDF 9 — Remove Stopwords

```python
stopwords = {"the","and","is","of"}
```

<details>
<summary>✅ Solution</summary>

```python
filtered_docs = []
for d in docs:
    filtered_docs.append(
        " ".join(w for w in d.split() if w not in stopwords)
    )
print(filtered_docs)
```

</details>

---

## 🔵 TF-IDF 10 — Normalize Vectors (Cosine Prep)

<details>
<summary>✅ Solution</summary>

```python
import math

def norm(vec):
    return math.sqrt(sum(v*v for v in vec.values()))

print(norm(tfidf))
```

</details>

---

## 🔴 TF-IDF 11 — Cosine Similarity

```python
a = "messi scores goals"
b = "messi inspires fans"
```

<details>
<summary>✅ Solution</summary>

```python
def cosine(v1, v2):
    common = set(v1) & set(v2)
    num = sum(v1[w] * v2[w] for w in common)
    den = norm(v1) * norm(v2)
    return num / den if den else 0
```

</details>

---

## 🔴 TF-IDF 12 — Find Most Similar Document

<details>
<summary>✅ Solution</summary>

```python
query = matrix[0]
sims = [cosine(query, m) for m in matrix]
print(sims)
```

</details>

---

## 🔴 TF-IDF 13 — Keyword Extraction

**Task:**
Return words with TF-IDF > threshold.

<details>
<summary>✅ Solution</summary>

```python
keywords = [w for w,v in tfidf.items() if v > 0.2]
print(keywords)
```

</details>

---

## 🔴 TF-IDF 14 — Streaming TF Update

<details>
<summary>✅ Solution</summary>

```python
stream = ["messi scores", "scores again"]

tf = {}
total = 0

for s in stream:
    for w in s.split():
        tf[w] = tf.get(w, 0) + 1
        total += 1

for w in tf:
    tf[w] /= total

print(tf)
```

</details>

---

## 🔴 TF-IDF 15 — Big Data MapReduce TF

<details>
<summary>✅ Solution</summary>

```python
mapped = []
for d in docs:
    for w in d.split():
        mapped.append((w,1))

reduced = {}
for w,v in mapped:
    reduced[w] = reduced.get(w,0) + v

print(reduced)
```

</details>

---

## 🔴 TF-IDF 16 — Rare Word Detection

**Task:**
Words with highest IDF.

<details>
<summary>✅ Solution</summary>

```python
print(sorted(idf, key=idf.get, reverse=True))
```

</details>

---

## 🔴 TF-IDF 17 — Explainability Test

**Question:**
Why does `"messi"` sometimes get low TF-IDF?

<details>
<summary>✅ Answer</summary>

```text
Because it appears in many documents,
its IDF is low, reducing its importance.
```

</details>

---

## 🔴 TF-IDF 18 — sklearn Comparison (Industry Standard)

<details>
<summary>✅ Solution</summary>

```python
from sklearn.feature_extraction.text import TfidfVectorizer

vec = TfidfVectorizer()
X = vec.fit_transform(docs)

print(vec.get_feature_names_out())
print(X.toarray())
```

</details>

---

## 🔴 TF-IDF 19 — Interview Question

**Why TF-IDF fails for semantics?**

<details>
<summary>✅ Answer</summary>

```text
It ignores word order, context, and meaning.
Synonyms are treated as unrelated.
```

</details>

---

## 🔴 TF-IDF 20 — Bridge to Transformers

**Question:**
What replaced TF-IDF?

<details>
<summary>✅ Answer</summary>

```text
Word embeddings → contextual embeddings → transformers
```

</details>

---

## 🎯 Final Message

TF-IDF teaches:

* importance
* rarity
* signal vs noise

If you understand this page:

* you understand **why attention exists**
* you understand **why embeddings work**

You are **ready for real NLP**.

---