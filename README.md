# Romanian Idiom Embeddings

## 📌 Overview

This project investigates the representation of Romanian idiomatic expressions and figurative language using distributed semantic models.

The main objective is to analyze how modern embedding models capture the meaning of idiomatic expressions, and to evaluate the relationship between:

* full idiomatic expressions
* their component words
* their figurative meanings
* their contextual usage

The study also explores the concept of **idiomatic opacity** and whether it can be approximated using embedding-based methods.

---

## 🎯 Research Objectives

* Build a manually annotated dataset of Romanian idiomatic expressions
* Compare embeddings of full expressions vs component words
* Estimate idiomatic opacity automatically using similarity measures
* Evaluate similarity between expressions and their figurative meanings
* Compare multiple models:

  * SentenceTransformer (multilingual MiniLM)
  * XLM-RoBERTa
  * Romanian BERT

---

## 📊 Dataset

The dataset consists of **330 Romanian idiomatic expressions**, each annotated with:

* `expression` – the idiomatic expression
* `figurative_meaning` – a short paraphrase
* `opacity` – manual score (semantic transparency vs opacity)
* `type` – expression type
* `context_sentence` – example usage

This dataset serves both as:

* an experimental resource
* a contribution to Romanian NLP resources

---

## 🧠 Methods

### 1. Compositionality Analysis

* Compare embedding of full expression vs mean embedding of component words
* Hypothesis:

  * higher similarity → more compositional (transparent)
  * lower similarity → more idiomatic (opaque)

---

### 2. Automatic Opacity Estimation

* Defined as:

```
opacity = 1 - similarity(expression, component_mean)
```

* Compared with manually annotated opacity using:

  * Pearson correlation
  * Spearman correlation

---

### 3. Expression vs Figurative Meaning

* Measure similarity between idiom and its paraphrase
* Evaluate against a **random baseline**

---

### 4. Contextual Analysis

* Compare expression embedding with its context sentence

---

### 5. Model Comparison

* SentenceTransformer (semantic similarity optimized)
* XLM-RoBERTa (multilingual transformer)
* Romanian BERT (language-specific model)

---

## 📈 Key Findings

* SentenceTransformer captures **partial semantic relationships** between idioms and their meanings
* Automatic opacity estimation based only on component similarity is **weak**
* Expression–meaning similarity is higher than random baseline → model captures some meaning
* Romanian BERT shows **moderate sensitivity to opacity**
* XLM-RoBERTa performs poorly in this setup (near-constant similarity values)

---

## ⚠️ Limitations

* Idiomatic meaning is **non-compositional**, making it difficult to model
* Tokenization is simple (whitespace-based)
* Transformer models used are not optimized for sentence similarity (except SentenceTransformer)
* Figurative language is underrepresented in training data

---

## 🚀 How to Run

1. Open the notebook in Google Colab
2. Upload the dataset file
3. Run all cells

---

## 📦 Dependencies

```
sentence-transformers
scikit-learn
pandas
numpy
matplotlib
seaborn
transformers
torch
scipy
openpyxl
```

---

## 📁 Project Structure

```
romanian-idiom-embeddings/
│
├── data/
│   └── romanian_idioms_dataset.xlsx
│
├── notebooks/
│   └── romanian_idiom_embeddings_analysis.ipynb
│
├── results/
│   └── romanian_idioms_results.xlsx
│
└── README.md
```

---

## 📝 Conclusion

The results show that modern embedding models can capture some aspects of Romanian idiomatic meaning, but remain limited in representing semantic opacity and non-compositional expressions.

This project highlights both:

* the **potential** of distributed models
* and their **limitations** in handling figurative language

---

## 👩‍🎓 Author

Dissertation project on Romanian figurative language and NLP.
