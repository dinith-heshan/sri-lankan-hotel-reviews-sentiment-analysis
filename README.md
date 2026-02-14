# Sentiment Analysis of Sri Lankan Hotel Reviews

**A Multi-Stage NLP Study on TripAdvisor Reviews**

This repository contains the implementation and analysis of a multi-stage study on sentiment and aspect-based analysis of Sri Lankan hotel reviews. The project covers end-to-end NLP workflows, from data collection and cleaning to feature extraction, classical and contextual embedding-based classification, and topic modeling.

---

## 📌 Project Overview

Sri Lanka aims to strengthen its tourism by showcasing top destinations. This project leverages **5,000+ reviews from 200 hotels** on TripAdvisor to analyze tourist sentiment and extract actionable insights for the tourism sector.

Key objectives:

* Curate and clean a high-quality hotel review dataset
* Generate robust sentiment labels via ensemble classifiers
* Compare feature extraction methods (sparse vs. dense representations)
* Evaluate classical ML models for sentiment classification
* Explore pre-trained contextual embeddings for improved performance
* Conduct topic modeling for aspect-based sentiment analysis

---

## 🗂 Project Tasks

### Task 1: Data Collection & Cleaning

* Scraped **16,500+ English reviews** from 200 hotels using APIFY TripAdvisor scraper
* Cleaned data via multi-step pipeline: duplicates removed, lemmatization, stopword removal, language verification
* Final dataset: **11,317 high-quality reviews**
* Explored data: sentiment distribution, review lengths, frequent terms, vocabulary compression

**Limitations:**

* Skewed toward positive reviews (mitigated via downsampling)
* Sampling bias favoring high-ranked hotels
* Language filtering may not be perfect

---

### Task 2: Establishing Ground Truth

* Ensemble labeling using **VADER, BERT, and RoBERTa**, aggregated via majority voting
* Final balanced dataset:

  * Negative: 1,907
  * Neutral: 1,022
  * Positive: 2,071
* Observed discrepancies between ratings and text sentiment, highlighting importance of text-based classification

---

### Task 3: Feature Extraction

* **Sparse features:** Bag-of-Words, TF-IDF
* **Dense features:** GloVe (average), Doc2Vec
* Captures both lexical frequencies and semantic context

---

### Task 4: Classical ML Classification

* Models: Random Forest, Logistic Regression, Linear SVC
* Metrics: balanced accuracy, F1 macro, precision-recall
* Findings:

  * Linear classifiers excel with sparse features
  * Random Forest better for dense embeddings but resource-intensive
  * Confusions mainly between neutral and adjacent classes

---

### Task 5: Contextual Embeddings

* Used **RoBERTa embeddings** with classical classifiers
* Improved performance across models compared to BoW, TF-IDF, GloVe, and Doc2Vec
* Future work: implement deep learning models for further improvement

---

### Task 6: Topic Modeling & Aspect-Based Sentiment

* Clustering reviews to identify hotel aspects (e.g., staff, food, service, room)
* Enabled aspect-based sentiment analysis for more granular insights

---

## 🛠 Key Learnings

* **Data Quality Matters:** Cleaning and filtering dramatically improve model performance
* **Ensemble Labeling:** Majority voting mitigates biases of individual classifiers
* **Sparse vs Dense Features:** Linear classifiers handle sparse features efficiently; contextual embeddings outperform static embeddings
* **Generative AI Support:** ChatGPT helped with debugging, methodology clarification, and report writing

---

## 📚 References & Tools

* TripAdvisor reviews via APIFY scraper
* Python libraries: `pandas`, `numpy`, `spaCy`, `scikit-learn`, `gensim`, `transformers`, `matplotlib`
* Ensemble classifiers: VADER, BERT, RoBERTa

---

## ✅ Conclusion

This project demonstrates a full **NLP workflow for sentiment analysis**, combining classical and modern techniques. The study provides insights into **tourist sentiment on Sri Lankan hotels** and sets a foundation for aspect-based recommendations to support tourism.
