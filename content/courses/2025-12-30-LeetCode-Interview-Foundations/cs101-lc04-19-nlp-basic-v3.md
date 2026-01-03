---
title: LC-TEST-19 — Basic NLP (V3)
weight: 120
date: '2026-01-01'
type: book
---

<!--more-->

## 🌍 Why This Document Exists

This is **not** a memorization guide.

This is how **real NLP engineers think**:
- before transformers
- before embeddings
- before GPUs

Every great NLP system starts with:
**text, counts, structure, and meaning**

---

# ⚽ A Real-World NLP Story — Messi Beyond Football

Lionel Messi is often described as a footballer,  
but to millions of people, he represents **discipline, creativity, and persistence**.

From Rosario to Barcelona, from criticism to championships,  
Messi’s story is not just about goals.

It is about **patterns**:
- repeated effort
- rare moments of brilliance
- quiet consistency

In language, meaning works the same way.

Common words appear everywhere.  
Rare words define intent.

This document treats Messi’s story as **data** —  
and trains you to **extract meaning like an NLP engineer**.

---

## 📄 The Corpus (Input Text)

```text
Lionel Messi is one of the greatest football players in history.
Messi began his career in Argentina before joining Barcelona.
At Barcelona, Messi scored goals, created chances, and inspired fans.
Many people believe Messi changed the way football is played.
Despite fame, Messi remained disciplined and focused on the game.
````

---

# 🏆 NLP Interview — 20 Problems

Difficulty increases gradually.
Try to **think before coding**.

---

## 🟢 NLP 1 — Sentence Count

**Task:**
How many sentences are in the corpus?

<details>
<summary>✅ Solution</summary>

```python
sentences = [s for s in text.split(".") if s.strip()]
print(len(sentences))
```

</details>

---

## 🟢 NLP 2 — Word Tokenization

**Task:**
Convert the corpus into a list of words (lowercased).

<details>
<summary>✅ Solution</summary>

```python
words = text.lower().replace(".", "").split()
print(words)
```

</details>

---

## 🟢 NLP 3 — Vocabulary Size

**Task:**
How many unique words exist?

<details>
<summary>✅ Solution</summary>

```python
print(len(set(words)))
```

</details>

---

## 🟡 NLP 4 — Word Frequency Count

**Task:**
Count how many times each word appears.

<details>
<summary>✅ Solution</summary>

```python
freq = {}
for w in words:
    freq[w] = freq.get(w, 0) + 1
print(freq)
```

</details>

---

## 🟡 NLP 5 — Most Frequent Word

**Task:**
Find the most common word.

<details>
<summary>✅ Solution</summary>

```python
print(max(freq, key=freq.get))
```

</details>

---

## 🟡 NLP 6 — Stopword Removal

Remove: `{"the", "is", "and", "of", "to", "in"}`

<details>
<summary>✅ Solution</summary>

```python
stop = {"the","is","and","of","to","in"}
filtered = [w for w in words if w not in stop]
print(filtered)
```

</details>

---

## 🟡 NLP 7 — Capitalized Word Detection

**Task:**
Detect words that originally started with capital letters.

<details>
<summary>✅ Solution</summary>

```python
caps = [w for w in text.split() if w[0].isupper()]
print(caps)
```

</details>

---

## 🔵 NLP 8 — Average Sentence Length

**Task:**
Compute average words per sentence.

<details>
<summary>✅ Solution</summary>

```python
lengths = [len(s.split()) for s in sentences]
print(sum(lengths) / len(lengths))
```

</details>

---

## 🔵 NLP 9 — Bigram Extraction

**Task:**
Extract all word bigrams.

<details>
<summary>✅ Solution</summary>

```python
bigrams = [(words[i], words[i+1]) for i in range(len(words)-1)]
print(bigrams)
```

</details>

---

## 🔵 NLP 10 — Keyword Search

**Task:**
Check if the word `"discipline"` exists.

<details>
<summary>✅ Solution</summary>

```python
print("discipline" in words)
```

</details>

---

## 🔵 NLP 11 — Named Entity Heuristic

**Rule:**
Words starting with capital letters = entities.

<details>
<summary>✅ Solution</summary>

```python
entities = list(set(caps))
print(entities)
```

</details>

---

## 🔴 NLP 12 — Document Frequency (DF)

**Task:**
How many sentences contain the word `"messi"`?

<details>
<summary>✅ Solution</summary>

```python
print(sum("messi" in s.lower() for s in sentences))
```

</details>

---

## 🔴 NLP 13 — TF Calculation

**Task:**
Compute TF for `"messi"` in the whole corpus.

<details>
<summary>✅ Solution</summary>

```python
tf_messi = freq["messi"] / len(words)
print(tf_messi)
```

</details>

---

## 🔴 NLP 14 — Rare Word Detection

**Task:**
Find words appearing only once.

<details>
<summary>✅ Solution</summary>

```python
rare = [w for w,c in freq.items() if c == 1]
print(rare)
```

</details>

---

## 🔴 NLP 15 — Sentence Similarity (Jaccard)

Compare sentence 1 and 3.

<details>
<summary>✅ Solution</summary>

```python
a = set(sentences[0].lower().split())
b = set(sentences[2].lower().split())
print(len(a & b) / len(a | b))
```

</details>

---

## 🔴 NLP 16 — Duplicate Sentence Detection

**Task:**
Check if any sentence is duplicated.

<details>
<summary>✅ Solution</summary>

```python
seen = set()
dup = False
for s in sentences:
    if s in seen:
        dup = True
    seen.add(s)
print(dup)
```

</details>

---

## 🔴 NLP 17 — Streaming Word Count (Big Data)

Messages arrive line by line.

<details>
<summary>✅ Solution</summary>

```python
counts = {}
for s in sentences:
    for w in s.lower().split():
        counts[w] = counts.get(w, 0) + 1
print(counts)
```

</details>

---

## 🔴 NLP 18 — MapReduce Mindset

**Map:** `(word, 1)`
**Reduce:** sum

<details>
<summary>✅ Solution</summary>

```python
mapped = [(w,1) for w in words]
reduced = {}
for w,v in mapped:
    reduced[w] = reduced.get(w,0) + v
print(reduced)
```

</details>

---

## 🔴 NLP 19 — Explainability Question

**Question:**
Why is `"messi"` less informative than `"disciplined"`?

<details>
<summary>✅ Answer</summary>

```text
Because "messi" appears many times,
while "disciplined" is rare and carries more information.
```

</details>

---

## 🔴 NLP 20 — Bridge to Modern NLP

**Question:**
Why does TF-IDF fail for deep semantics?

<details>
<summary>✅ Answer</summary>

```text
It ignores word order, context, and meaning.
Synonyms are unrelated, and semantics are not captured.
```

</details>

---

## 🎯 Final Message

If you can:

* explain these problems
* code them calmly
* justify your choices

You are **interview-ready**.

Before LLMs, there was understanding.
Before transformers, there was thinking.

This is how **real NLP engineers are made**.

---