#  PharmaFeel: Sentiment Analysis on Patient Drug Reviews

##  Overview
**PharmaFeel** is a Natural Language Processing (NLP) project that analyzes unstructured patient reviews about medications.  
The goal is to classify each review as **positive**, **neutral**, or **negative** based on the patient's experience, comparing classical ML and modern LLM-based NLP techniques.

---

##  Dataset
- **Source:** [Kaggle - Drugs and Conditions: Patient Voices](https://www.kaggle.com/datasets/mukeshdevrath007/drugs-and-conditions-patient-voices-2-8l)  
- **Size:** ~280,000 reviews  
- **Fields:**  
  - Drug Name  
  - Condition  
  - User  
  - Date  
  - Rating (1–10)  
  - Free-text Content  
- **Sentiment Labels:**  
  - **Positive:** 7–10  
  - **Neutral:** 4–6  
  - **Negative:** 1–3  
- **Average Review Length:** 91 ± 50 words

---

##  Methods

###  Preprocessing
- Lowercasing  
- Punctuation & short-word removal  
- Stopword removal  
- Sentence embeddings generated using **Sentence-BERT (MiniLM-L6-v2)**

###  Baseline Classifier
- **Model:** Logistic Regression trained on SBERT embeddings  
- **Split:** 80% training / 20% testing (stratified by sentiment)  
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-score

---

##  Baseline Results
- **Accuracy:** 62%  
- **F1-score (positive):** 0.75
- **F1-score (negative):** 0.5 
- **F1-score (neutral):** 0.05 *(model struggles with neutral sentiment)*  

---

##  Next Steps
- Implement **Zero-shot & Few-shot Classification** using LLMs (e.g. GPT)
- Use **prompt engineering** to improve LLM performance
- Add explainability tools (**SHAP**) to interpret model predictions

---

##  Authors
- Yuval Elisha  
- Nikol Jabotinski
