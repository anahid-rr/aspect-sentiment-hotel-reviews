# 🏨 Aspect-Based Sentiment Analysis and Ranking of Hotel Reviews

## 📘 Project Overview
This project aims to analyze hotel reviews to automatically **extract aspects** (e.g., *room*, *location*, *staff*) and determine their **sentiment polarity** (*positive*, *negative*, *neutral*).  
The goal is to help hotel managers identify which service dimensions are praised or criticized, enabling **data-driven decision-making** to improve customer satisfaction.

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

### **Step 5 (Optional): Aspect Ranking**
- Compute **average sentiment score** per aspect  
- Rank aspects based on sentiment polarity and frequency  
- Display ranked aspects via **bar chart visualization**

---

## 📊 Example Comparison Table
| Aspect | Model | Accuracy | F1-score |
|---------|--------|-----------|-----------|
| Room | TF-IDF + Logistic Regression | 0.82 | 0.79 |
| Wi-Fi | Word2Vec + Logistic Regression | 0.75 | 0.73 |

*(Sample results — actual values may vary.)*

---

