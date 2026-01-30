
---

# 🧠 ProStack-MH: An Explainable Stacked Transformer Framework

### Differentiation of Anxiety and Depression in Real-World Mental-Health Discussions

---

## 📄 Abstract & Overview

Mental health identification in social media is challenging due to the narrative, complex, and inconsistent nature of user-generated text. **ProStack-MH** is a high-performance computational pipeline designed specifically to differentiate between **Anxiety** and **Depression**, which often exhibit high linguistic overlap.

This repository implements a **Probabilistic Stacking Ensemble** using fine-tuned transformer models, optimized to capture subtle emotional and cognitive cues in long-form discussions.

---

## 🚀 Key Research Features

### 1. Hybrid Stacking Architecture

The framework uses a two-tier architectural approach:

* **Base Learners:** Fine-tuned **RoBERTa-base** and **DistilRoBERTa** to extract deep contextual embeddings.
* **Meta-Learner:** A **Logistic Regression** layer that aggregates probability vectors from the base learners to make a final, refined prediction.

### 2. Explainable AI (XAI) with SHAP

To ensure clinical trust, we integrated **SHAP (SHapley Additive exPlanations)**. This allows us to:

* Identify specific tokens (words) that contribute to a diagnosis.
* Visualize global feature importance to understand the model's logic.

### 3. Data Integrity & Leakage Prevention

* **Source:** Real-world posts from the **Beyond Blue** forum.
* **User-Level Partitioning:** Ensuring that data from the same user does not appear in both training and testing sets, preventing biased performance.
* **Noise Filtering:** Automated removal of staff posts, URLs, and moderator artifacts.

---

## 📊 Performance Metrics

Compared to single transformer models, **ProStack-MH** shows superior results:

| Model | Accuracy | F1-Score | MCC | Kappa |
| --- | --- | --- | --- | --- |
| **ProStack-MH (Ours)** | **93.38%** | **0.9302** | **0.8674** | **0.8673** |
| RoBERTa-base | 83.20% | 0.8290 | 0.7800 | 0.7790 |
| DeBERTa-base | 81.50% | 0.8120 | 0.7650 | 0.7600 |

---

## 📂 Project Structure

```bash
├── data/
│   └── Mental_Health_Forum_Data.csv     # Scraped from Beyond Blue (28.2k records)
├── notebooks/
│   └── mental_health_implementation.ipynb # Implementation of ProStack-MH
├── requirements.txt                     # Library dependencies
└── README.md                            # Documentation

```

---

## 🛠️ Technology Stack

* **Models:** RoBERTa, DistilRoBERTa, Stacked Ensemble.
* **Explainability:** SHAP, LIME (optional).
* **Libraries:** `transformers`, `torch`, `scikit-learn`, `pandas`, `seaborn`.

---

## ⚙️ Installation & Usage

1. **Clone the Repo:**
```bash
git clone https://github.com/shihab13j/mental-health-analysis.git

```


2. **Install Requirements:**
```bash
pip install -r requirements.txt

```


3. **Run Notebook:**
Execute the `mental_health_implementation.ipynb` to reproduce the results and XAI visualizations.

---

## 📚 Citation

If you use this work or dataset in your research, please cite our paper:

> *ProStack-MH: An Explainable Stacked Transformer Approach to Anxiety-Depression Differentiation in Real-World Mental-Health Discussions.* (2025).

---

## 📜 Disclaimer

This system is for **research purposes only**. It is designed to assist in understanding mental health patterns and should not be used as a substitute for professional medical diagnosis or treatment.

---

