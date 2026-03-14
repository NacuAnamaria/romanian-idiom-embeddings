# romanian-idiom-embeddings
Romanian Idiom Embeddings – Analyzing the Representation of Figurative Meaning in Romanian using Distributional Models
# Romanian Idiom Embeddings

## Overview

This project explores how modern NLP embedding models represent **figurative language in Romanian**, focusing on **idiomatic expressions and figures of speech**.

The main goal is to investigate whether semantic representations produced by transformer-based models capture the **figurative meaning of idioms** or remain closer to their **literal word composition**.

To achieve this, the project constructs a **small annotated corpus of Romanian idioms**, extracts sentence embeddings using multilingual transformer models, and compares the embedding of the entire idiom with the embeddings of its individual components.

The work aims to contribute both:

* a **small curated resource of Romanian idiomatic expressions**, and
* a **simple methodology for analyzing figurative meaning in distributional semantic models**.

---

## Research Objective

The project evaluates how well distributed semantic representations capture **non-compositional meaning**.

Specifically, it tests whether the embedding of a full idiomatic expression differs significantly from the average embedding of its component words.

Example idiom:

```
"a da cu bâta-n baltă"
figurative meaning: "a face o gafă"
```

If the embedding of the full expression diverges strongly from the mean embedding of the words, this may indicate that the model captures **idiomatic meaning beyond literal composition**.

---

## Methodology

### 1. Corpus Creation

A dataset of approximately **100–200 Romanian idioms and figurative expressions** is collected and manually annotated.

Each entry includes:

* the idiomatic expression
* its component words
* a short figurative meaning description
* optional linguistic notes

Example dataset format:

| id | expression           | components                    | figurative_meaning | type  |
| -- | -------------------- | ----------------------------- | ------------------ | ----- |
| 1  | a da cu bâta-n baltă | a da | cu | bâta | în | baltă | a face o gafă      | idiom |
| 2  | a freca menta        | a freca | menta               | a pierde timpul    | idiom |

---

### 2. Embedding Extraction

Sentence embeddings are extracted using multilingual transformer models:

* `sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2`
* `xlm-roberta-base` (contextual representation)

Embeddings are computed for:

1. the **full idiomatic expression**
2. each **individual word component**

---

### 3. Similarity Analysis

For each expression:

1. Compute the **embedding of the full expression**
2. Compute embeddings for each component word
3. Calculate the **average embedding of the components**
4. Measure **cosine similarity** between:

   * full expression embedding
   * mean component embedding

This allows us to evaluate **how compositional the representation is**.

---

### 4. Interpretation

The results are analyzed to determine:

* whether idiomatic expressions are treated compositionally
* whether models capture figurative meaning
* differences between sentence-transformer embeddings and contextual transformer embeddings

---

## Expected Results

The project produces:

* an **annotated corpus of Romanian idioms**
* similarity scores between idioms and component words
* visualizations of semantic similarity distributions
* observations about **the ability of transformer models to represent figurative language**

---

## Contribution

This project contributes:

* a **small linguistic resource for Romanian idiomatic expressions**
* an **experimental framework for evaluating figurative meaning in embedding models**
* insights into the **limitations of distributional semantics for non-compositional language**

Master's Dissertation Project
Natural Language Processing / Computational Linguistics
