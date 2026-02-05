# 🎬 Movie Review Sentiment Analysis

## 📌 Overview
This project implements a **binary sentiment analysis system** to classify movie reviews into **Positive** or **Negative** sentiments.  
The approach combines **text preprocessing**, **TF-IDF feature representation**, **sentiment-based features**, and a **weighted ensemble of machine learning models** to achieve robust and stable performance.

---

## 🧹 Text Preprocessing
Each movie review is cleaned and normalized using the following steps:

- **Lowercasing**  
  Convert all text to lowercase to ensure consistency.

- **Remove URLs and Mentions**  
  Eliminate links and mentions that do not contribute to sentiment meaning.

- **Remove Punctuation**  
  Remove punctuation symbols such as `! ? , .`.

- **Tokenization**  
  Split text into individual words.

- **Stopword Removal**  
  Remove common words (e.g., *this, is, the, and*) that do not carry sentiment.

- **Lemmatization**  
  Convert words to their base form (e.g., *running → run*).

---

## 🔢 Feature Representation

### TF-IDF Embedding
Text is transformed using **TF-IDF (Term Frequency–Inverse Document Frequency)**, producing a high-dimensional sparse vector (~10,000 features).

### Sentiment Features
Additional handcrafted sentiment features are added:
- Positive word count  
- Negative word count  
- Total word count  
- Polarity score (positive − negative)

The final feature vector is a combination of **TF-IDF + sentiment features**.

---

## 🤖 Models Used
Multiple machine learning models are trained and evaluated:

- Logistic Regression  
- Support Vector Machine (SVM)  
- Random Forest  
- LightGBM  
- XGBoost  

The final system uses a **weighted ensemble** strategy to improve stability and reduce overfitting.

---

## 📊 Results
Cross-validation accuracy results:

| Model | Accuracy |
|------|----------|
| Logistic Regression | 0.886 |
| SVM | 0.874 |
| Random Forest | 0.823 |
| LightGBM | 0.821 |
| XGBoost | 0.811 |

### Final Ensemble Strategy
- Historical ensemble prediction: **50%**
- Current model prediction: **30%**
- Meta-learning prediction (XGBoost): **20%**

The ensemble approach provides **more stable and reliable predictions** for **Positive** and **Negative** movie reviews.

---

## 🎯 Sentiment Classes
- **Positive**
- **Negative**
