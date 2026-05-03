# AI-RAG-System
A RAG System that evaulates Q-A based on user query
# Agentic RAG System (AI Regulation)

##  Overview

This project builds an **agentic RAG (Retrieval-Augmented Generation)** system over 4 documents on AI regulation.
The system decides how to answer a query instead of blindly retrieving.

---

##  How It Works

1. **Query Router**

   * Factual → direct answer from docs
   * Synthesis → combine multiple sources
   * Out-of-scope → say “not available”

2. **Retriever**

   * Uses FAISS to find relevant chunks

3. **Generator**

   * Generates answers strictly from retrieved content

---

##  Dataset

Place the 4 `.txt` files inside the `data/` folder:

```bash
data/
  doc1.txt
  doc2.txt
  doc3.txt
  doc4.txt
```

---

## How to Run

```bash
pip install -r requirements.txt
```

Set your API key:

```python
import os
os.environ["OPENAI_API_KEY"] = "your_key"
```

Run evaluation:

```bash
python run_evaluation.py
```

---

## 📊 Evaluation

* 15 test questions (5 factual, 5 synthesis, 5 out-of-scope)
* Metrics:

  * Routing accuracy
  * Retrieval accuracy
  * Cosine similarity
  * ROUGE score

Results are saved in:

```bash
results/results.csv
```

---

##  Limitations

* Rule-based routing can misclassify queries
* Retrieval may miss some important chunks
* Some documents contain conflicting information

---

##  Key Features

* Explicit query routing (not black-box)
* Handles multi-document reasoning
* Avoids hallucination for unknown queries

---
