# 🏨 Aspect-Based Sentiment Analysis and Ranking of Hotel Reviews

# Multi-Aspect Hotel Review Classification  
### Aspect Detection + Aspect-Conditioned Sentiment Analysis  
**Baseline Models (TF-IDF, Word2Vec) and BERT-Based Neural Models**

---

## 1. Overview

This project implements a full pipeline for analyzing hotel reviews across **13 predefined aspects** and identifying the **sentiment** expressed toward each aspect.  
We compare classical machine learning baselines (TF-IDF, Word2Vec + Logistic Regression) with several modern transformer-based models (BERT, Multi-Head BERT, Token-Level BERT).  
The goal is to evaluate how model architecture affects multi-aspect understanding in real-world review data.

The project includes:

- **Aspect Detection** (multi-label classification)
- **Aspect-Conditioned Sentiment Analysis** (3-class: negative, neutral, positive)
- **Baselines vs. Deep Learning Comparison**
- **Reproducible experiments** with fixed seeds


---

## 🎯 Objectives
- **Aspect Extraction:** Identify key hotel aspects mentioned in reviews.  
- **Sentiment Classification:** Determine sentiment polarity for each extracted aspect.  
- **Aspect Ranking:** Rank aspects based on sentiment scores and frequency to highlight strengths and weaknesses.

---

## 🧾 Dataset
**Source:** [Kaggle – Hotel Reviews: Aspects, Sentiments, and Topics](https://www.kaggle.com/)  
- **Entries:** 23,113 reviews  
- **Format:** CSV  
- **Columns:** `review`, multiple aspect columns (e.g., `Room`, `Wi-Fi`, `Staff`, etc.), and sentiment labels.

---

## ⚙️ Installation & Requirements

### 1️⃣ Environment Setup
You can use **Google Colab** or a **local Python (≥3.8)** environment.

```bash
git clone https://github.com/anahid-rr/hotel-aspect-sentiment.git
cd hotel-aspect-sentiment
pip install -r requirements.txt
```


## 🧩 How to Run the Code

All steps are implemented in the main Colab notebook:  
📄 **`Aspect_Sentiment_Baseline.ipynb`**

### **Step 1: Load and Clean Data**
- Remove punctuation, digits, and stopwords  
- Tokenize and lemmatize each review  

### **Step 2: Split Dataset**
- 70% training, 15% validation, 15% testing  

### **Step 3: Train Baselines**
- **TF-IDF + Logistic Regression**  
- **Word2Vec + Logistic Regression**  

### **Step 4: Evaluate Models**
- Generate **classification reports** (Precision, Recall, F1-score)  
- Visualize **aspect-wise performance** using bar charts  



---

## 📊 Example Comparison Table
| Aspect | Model | Accuracy | F1-score |
|---------|--------|-----------|-----------|
| Room | TF-IDF + Logistic Regression | 0.82 | 0.79 |
| Wi-Fi | Word2Vec + Logistic Regression | 0.75 | 0.73 |


---
=== Aspect Classification Report ===
                      precision    recall  f1-score   support

               Clean       0.67      0.51      0.58       217
             Comfort       0.76      0.08      0.15       154
Facilities/Amenities       0.64      0.58      0.61       317
            Location       0.92      0.76      0.83       516
                 Bar       0.75      0.21      0.32        29
                 Bed       1.00      0.01      0.03        75
             Parking       0.62      0.60      0.61        30
               Noise       0.69      0.55      0.61       153
   Reception-checkin       0.55      0.66      0.60       102
                Lift       0.50      0.10      0.17        30
     Value for money       0.86      0.38      0.53        65
               Wi-Fi       0.79      0.71      0.75        31
             Generic       0.70      0.19      0.29       151

           micro avg       0.75      0.51      0.60      1870
           macro avg       0.73      0.41      0.47      1870
        weighted avg       0.76      0.51      0.57      1870
Interpretation

Location, Wi-Fi, Amenities, Noise → strong performance

Bed, Comfort, Generic → very low recall, indicating under-detection

Overall macro-F1 0.47, which is expected for multi-label imbalanced tasks

Token-level modeling significantly improves understanding of frequent and well-contextualized aspects

