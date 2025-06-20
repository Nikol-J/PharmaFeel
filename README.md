# PharmaFeel: Understanding Patient Sentiment Through LLM

PharmaFeel is an NLP project focused on analyzing user drug reviews to detect and classify overall sentiment and extract side effects from negative reviews.  
We use **LLM-based techniques** like RAG and few-shot classification, along with classic models as such Logistic Regression, KNN and XGBoost.

---

## Project Goals

- Classify user sentiment based on drug experience
- Predict rating value with review regression
- Compare performance of LLM vs classical ML methods
- Compare performance of between different embeddings and data balancing methods
- Extract side effects from reviews classified as "Negative"

---

## Dataset

- Source: [Kaggle – Drugs and Conditions Patient Voices (2.8M)](https://www.kaggle.com/datasets/mukeshdevrath007/drugs-and-conditions-patient-voices-2-8l)
- Format:
  - `Content`: the review text
  - `Drug Name`: medication name
  - `Condition`: treated condition
  - `Rating`: user’s score from 1 to 10
- Preprocessing:
  - HTML & link removal
  - Lowercasing & whitespace normalization
  - Label mapping (rating → sentiment class)

---

##  Models & Methods

| Task                          | Approach                       | Class Balancing                | Embeddings
|-------------------------------|--------------------------------|--------------------------------|----------------------------------------------------------|
| Sentiment classification      | Few-Shot Classification        | Weighted, Over-Sampling        | S-BERT: all-MiniLM-L6-v2                                 |
|                               | Logistic Regression            | None, Weighted, Over-Sampling  | S-BERT: all-MiniLM-L6-v2, OpenAI: Text-embedding-3-small |
|                               | XGBoost                        | None, Weighted, Over-Sampling  | S-BERT: all-MiniLM-L6-v2                                 |
| Review Regression             | Linear Regression              |                                | S-BERT: all-MiniLM-L6-v2                                 |
|                               | KNN                            |                                | S-BERT: all-MiniLM-L6-v2                                 |
|                               | Ridge Regression               |                                | S-BERT: all-MiniLM-L6-v2                                 |
| Side Effects Chatbot          | RAG                            |                                | OpenAI: Text-embedding-3-small                           |


## Evaluation & Metrics

For sentiment classification, we used:
- Accuracy
- Precision 
- F1-score

For review regression, we used:
- MAE
- MSE 
- R2

For side effect extraction:
- Manual inspection
- Keyword matching
- Ground-truth keyword comparison (precision-focused)

![Visual Abstract](Visual%20Abstract.jpg)
---
