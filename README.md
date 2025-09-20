# 🎯 Item-Based Collaborative Filtering Recommender System  

This project is a **C++ implementation of an Item-Based Collaborative Filtering (IBCF) recommender system**, developed for the **CMP2003 Rating Prediction Challenge** on Kaggle.  

The system predicts user ratings for items by leveraging item–item similarities and user rating histories.  

- **Competition:** [CMP2003 Rating Prediction Challenge](https://www.kaggle.com/competitions/cmp2003-rating-prediction-challenge)  
- **Kaggle Rank:** 🥇 #1  
- **RMSE Score:** 0.89777  
- **Runtime:** ~11.5 minutes  

---

## 🚀 Overview  

The core of the project is a C++ program that:  
- Reads user-item rating data  
- Builds a similarity-based model  
- Predicts ratings for the test set  
- Generates a Kaggle-ready `submission.csv`  

The algorithm calculates similarities between items and predicts ratings by aggregating the user’s ratings for the most similar items.  

---

## ✨ Features  

- **Algorithm**: Implements Item-Based Collaborative Filtering from scratch  
- **Similarity Metric**: Adjusted Cosine Similarity (ratings normalized by subtracting item averages)  
- **Prediction Model**: Weighted sum of ratings from the most similar items  
- **Data Structures**: Efficient C++ STL maps for quick lookups  
- **Performance**: Optimized, achieving a top Kaggle rank in ~11.5 minutes  

---

## ⚙️ How It Works  

1. **Data Loading**  
   Reads `train.csv` (`userId`, `itemId`, `rating`) and stores it in a nested map:  
   ```cpp
   map<itemId, map<userId, rating>>
````

2. **Similarity Calculation**
   Finds co-rated items and computes adjusted cosine similarity.

3. **Neighborhood Selection**
   Selects top *k* most similar items already rated by the user.

4. **Rating Prediction**
   Computes weighted prediction using neighbor ratings and similarity scores.

5. **Submission Generation**
   Processes `test.csv`, predicts ratings, and outputs `submission.csv`.

---

## 📂 Files

* `main.cpp`: Entry point, handles data I/O and prediction orchestration
* `RecommenderSystem.h`: Class definitions for data structures & methods
* `RecommenderSystem.cpp`: Implementation of the IBCF algorithm
* `train.csv`: Training dataset
* `test.csv`: Test dataset
* `sample_submission.csv`: Example submission file

---

## 🛠️ How to Compile and Run

1. **Compile**

   ```bash
   g++ main.cpp RecommenderSystem.cpp -o recommender -std=c++11 -O2
   ```

2. **Run**

   ```bash
   ./recommender
   ```

3. **Output**
   Console progress + `submission.csv` with predictions.

---

## 👥 Contributors

* Briksam Kasımoğlu ✨
* Firas Elbayoumi ✨
* Yaser Z. K. Shoshaa ✨
---
