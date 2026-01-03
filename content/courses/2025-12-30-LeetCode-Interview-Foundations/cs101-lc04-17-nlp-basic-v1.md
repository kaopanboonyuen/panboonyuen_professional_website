---
title: LC-TEST-17 — Basic NLP (V1)
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Document Exists

This is **not** a pure NLP library tutorial.

This is **algorithmic thinking for NLP engineers**.

If you want to work at:
- Google (Search, Gemini)
- OpenAI (ChatGPT, alignment)
- AWS (Comprehend, Bedrock)
- Microsoft (Copilot, Bing)

You must **master strings, text, and scale**.

---

# ⚽ A Short Story — Messi & Language

Messi does not speak with words on the field.

He speaks with:
- movement
- timing
- patterns

Language is the same.

Before transformers…
Before LLMs…

There were:
- characters
- tokens
- frequencies
- distributions

This book trains your **text intuition** — not just syntax.

---

# 🏆 Python NLP — 20 String Problems

Difficulty increases **gradually**.  
Try before opening solutions.

---

## 🟢 NLP 1 — Word Count (Warm-Up)

Messi speaks:

```python
text = "messi plays football and messi inspires the world"
````

**Task:**
Count how many times each word appears.

<details>
<summary>✅ Solution</summary>

```python
counts = {}
for w in text.split():
    counts[w] = counts.get(w, 0) + 1
print(counts)
```

</details>

---

## 🟢 NLP 2 — Unique Vocabulary Size

**Task:**
Count how many **unique words** are in the text.

<details>
<summary>✅ Solution</summary>

```python
vocab = set(text.split())
print(len(vocab))
```

</details>

---

## 🟢 NLP 3 — Capitalization Detection

```python
sentence = "Messi Is The Greatest"
```

**Task:**
Return all words that start with a capital letter.

<details>
<summary>✅ Solution</summary>

```python
caps = [w for w in sentence.split() if w[0].isupper()]
print(caps)
```

</details>

---

## 🟢 NLP 4 — Lowercase Normalization

**Task:**
Convert text to lowercase and remove extra spaces.

```python
text = "  Messi   Plays   Football "
```

<details>
<summary>✅ Solution</summary>

```python
clean = " ".join(text.lower().split())
print(clean)
```

</details>

---

## 🟡 NLP 5 — Character Frequency

**Task:**
Count how often each character appears (ignore spaces).

```python
text = "messi"
```

<details>
<summary>✅ Solution</summary>

```python
freq = {}
for c in text:
    if c != " ":
        freq[c] = freq.get(c, 0) + 1
print(freq)
```

</details>

---

## 🟡 NLP 6 — Find Keywords in Text

```python
keywords = ["goal", "win", "champion"]
text = "messi scores a goal to win the match"
```

**Task:**
Return keywords that appear in text.

<details>
<summary>✅ Solution</summary>

```python
found = []
for k in keywords:
    if k in text:
        found.append(k)
print(found)
```

</details>

---

## 🟡 NLP 7 — Sentence Length Analyzer

```python
sentences = [
  "Messi plays football",
  "Messi inspires millions of people around the world"
]
```

**Task:**
Return sentence lengths (in words).

<details>
<summary>✅ Solution</summary>

```python
lengths = [len(s.split()) for s in sentences]
print(lengths)
```

</details>

---

## 🟡 NLP 8 — Stopword Removal

```python
stopwords = {"the","and","is"}
text = "messi is the best and the greatest"
```

<details>
<summary>✅ Solution</summary>

```python
filtered = [w for w in text.split() if w not in stopwords]
print(" ".join(filtered))
```

</details>

---

## 🔵 NLP 9 — Bigram Generation

```python
text = "messi wins world cup"
```

**Task:**
Generate word bigrams.

<details>
<summary>✅ Solution</summary>

```python
words = text.split()
bigrams = [(words[i], words[i+1]) for i in range(len(words)-1)]
print(bigrams)
```

</details>

---

## 🔵 NLP 10 — Most Frequent Word

```python
text = "messi messi goal goal goal win"
```

<details>
<summary>✅ Solution</summary>

```python
freq = {}
for w in text.split():
    freq[w] = freq.get(w, 0) + 1
print(max(freq, key=freq.get))
```

</details>

---

## 🔵 NLP 11 — Prefix Matching (Search Autocomplete)

```python
words = ["messi","message","meta","goal"]
prefix = "me"
```

<details>
<summary>✅ Solution</summary>

```python
print([w for w in words if w.startswith(prefix)])
```

</details>

---

## 🔵 NLP 12 — Suffix Detection

**Task:**
Find words ending with `"ing"`.

```python
words = ["playing","played","scoring","score"]
```

<details>
<summary>✅ Solution</summary>

```python
print([w for w in words if w.endswith("ing")])
```

</details>

---

## 🔴 NLP 13 — Streaming Word Count (Big Data Mindset)

Messages arrive one by one.

```python
stream = ["messi scores", "messi wins", "scores again"]
```

<details>
<summary>✅ Solution</summary>

```python
counts = {}
for msg in stream:
    for w in msg.split():
        counts[w] = counts.get(w, 0) + 1
print(counts)
```

</details>

---

## 🔴 NLP 14 — MapReduce (Word Count)

**Map:** emit `(word, 1)`
**Reduce:** sum values

<details>
<summary>✅ Solution</summary>

```python
mapped = []
for s in stream:
    for w in s.split():
        mapped.append((w,1))

reduced = {}
for w,v in mapped:
    reduced[w] = reduced.get(w,0) + v

print(reduced)
```

</details>

---

## 🔴 NLP 15 — Longest Word in Corpus

```python
text = "messi demonstrates extraordinary football intelligence"
```

<details>
<summary>✅ Solution</summary>

```python
words = text.split()
print(max(words, key=len))
```

</details>

---

## 🔴 NLP 16 — Named Entity Heuristic

**Rule:**
Words starting with capital = entity.

```python
text = "Messi plays for Argentina"
```

<details>
<summary>✅ Solution</summary>

```python
entities = [w for w in text.split() if w[0].isupper()]
print(entities)
```

</details>

---

## 🔴 NLP 17 — Sentence Tokenization

```python
text = "Messi scored. Fans celebrated. History written."
```

<details>
<summary>✅ Solution</summary>

```python
sentences = [s.strip() for s in text.split(".") if s]
print(sentences)
```

</details>

---

## 🔴 NLP 18 — Text Similarity (Bag of Words)

```python
a = "messi scores goals"
b = "messi scores"
```

<details>
<summary>✅ Solution</summary>

```python
sa, sb = set(a.split()), set(b.split())
print(len(sa & sb) / len(sa | sb))
```

</details>

---

## 🔴 NLP 19 — Detect Shouting (Uppercase Ratio)

```python
text = "GOAL GOAL Messi"
```

<details>
<summary>✅ Solution</summary>

```python
caps = sum(1 for c in text if c.isupper())
print(caps / len(text) > 0.5)
```

</details>

---

## 🔴 NLP 20 — Real NLP Interview Question

**Task:**
Detect duplicate sentences.

```python
sentences = [
  "messi scores",
  "messi wins",
  "messi scores"
]
```

<details>
<summary>✅ Solution</summary>

```python
seen = set()
dups = []

for s in sentences:
    if s in seen:
        dups.append(s)
    seen.add(s)

print(dups)
```

</details>

---

## 🎯 Final Message

Before:

* BERT
* GPT
* Transformers

There were:

* strings
* loops
* counters
* patterns

If you **master this page**,
you understand **NLP from the ground up**.

---