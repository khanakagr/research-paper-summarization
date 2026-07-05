# Research Paper Semantic Search & Summarization System

## Project Overview

This project implements an end-to-end intelligent research paper retrieval system using modern Natural Language Processing techniques. The system is designed to understand the semantic meaning of user queries and retrieve the most relevant research papers, along with concise summaries and key insights.

Unlike traditional keyword-based systems, this approach focuses on contextual understanding, enabling more accurate and meaningful search results across large collections of research documents.

---

## Features Used

### 1) Semantic Representation of Text

Research papers and queries are encoded using transformer-based sentence embeddings (**all-MiniLM-L6-v2**), enabling the system to capture contextual and semantic relationships beyond simple keyword matching.

---

### 2) Efficient Similarity Search using FAISS

High-dimensional embeddings are indexed using FAISS to allow **fast and scalable nearest-neighbor search**, making the system efficient even for large datasets.

---

### 3) Hybrid Retrieval Strategy

The system integrates:

* **Semantic similarity (FAISS)**
* **Keyword-based scoring (BM25)**

This ensures results are both **contextually relevant and keyword aligned**.

---

### 4) Query Understanding & Expansion

User queries are enriched by extracting keyphrases, allowing the system to better interpret intent and improve retrieval quality, especially for short or ambiguous queries.

---

### 5) Deep Learning-based Reranking

Retrieved results are refined using a cross-encoder model (**cross-encoder/ms-marco-MiniLM-L-6-v2**) for **precise query-document relevance scoring**.

---

### 6) Automatic Text Summarization

Each retrieved paper is summarized using (**facebook/bart-large-cnn**), enabling quick understanding without reading full abstracts.

---

### 7) Keyword Extraction for Insight Generation

KeyBERT extracts important keywords and phrases, highlighting the **core topics of each paper**.

---

### 8) Named Entity Recognition (NER)

spaCy is used to extract entities such as:

* methods
* domains
* technical terms

This enriches the textual representation used in retrieval.

---

### 9) Efficient Batch Processing

Large-scale tasks like entity extraction are optimized using `nlp.pipe`, improving processing speed significantly.

---

### 10) Robust Handling of Long Text Inputs

Text is safely truncated and processed to comply with transformer limits, ensuring **stable summarization performance**.

---

##  Data Setup

The files which were installed after running the notebook:

* `papers.csv` → processed dataset
* `paper_embeddings.npy` → embeddings
* `faiss.index` → FAISS index
* `bm25.pkl` → BM25 model

---

##  Tech Stack

* **Python**
* **Sentence Transformers**
* **FAISS**
* **Hugging Face Transformers**
* **KeyBERT**
* **spaCy**
* **scikit-learn**
* **NumPy / Pandas**

---

##  Output

For each user query, the system returns:

*  Similarity Score
*  Research Paper Title
*  Abstract 
*  Generated Summary
*  Extracted Keywords

---

## Author

Khanak Agrawal  
[LinkedIn](https://www.linkedin.com/in/khanak-agrawal-51025037b/) | [GitHub](https://github.com/khanakagr)
