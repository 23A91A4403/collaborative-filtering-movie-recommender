# Movie Recommendation System using Collaborative Filtering

## Overview
This project implements a comprehensive **Movie Recommendation System** using classic **Collaborative Filtering techniques**. The system predicts user movie ratings and generates personalized **Top-N movie recommendations** by comparing three different approaches:

- User-Based Collaborative Filtering
- Item-Based Collaborative Filtering
- Matrix Factorization using Singular Value Decomposition (SVD)

The goal of this project is to understand how recommendation systems work in real-world applications and to compare the effectiveness of memory-based and model-based approaches.

---

## Dataset
This project uses the **MovieLens dataset**, a widely used dataset for building and evaluating recommendation systems.

The dataset contains:
- User IDs
- Movie IDs
- Ratings given by users
- Timestamps of ratings

These ratings are used to build a **user-item interaction matrix** which forms the foundation for the recommendation algorithms.

---

## Exploratory Data Analysis (EDA)
Exploratory Data Analysis was performed to understand the dataset and its characteristics. The analysis includes:

- Distribution of movie ratings
- Total number of users and movies
- Number of ratings per user
- Most popular movies based on rating count
- Data sparsity in the user-item matrix

These insights help understand user behavior and the challenges of sparse recommendation datasets.

---

## Models Implemented

### User-Based Collaborative Filtering
User-Based Collaborative Filtering recommends movies by identifying users with similar rating patterns.

Steps:
- Compute similarity between users using metrics such as **Cosine Similarity** or **Pearson Correlation**
- Identify the most similar users
- Predict ratings based on ratings given by similar users

---

### Item-Based Collaborative Filtering
Item-Based Collaborative Filtering recommends movies based on the similarity between items (movies).

Steps:
- Compute similarity between movies based on user ratings
- Identify movies that are similar to the ones the user has liked
- Recommend the most similar movies

---

### Matrix Factorization using SVD
Singular Value Decomposition (SVD) is a **model-based collaborative filtering technique** that learns hidden relationships between users and items.

It works by:
- Decomposing the user-item interaction matrix
- Learning **latent user features** and **latent movie features**
- Predicting ratings using these learned representations

SVD often provides better performance than traditional similarity-based methods.

---

## Recommendation Generation
A function is implemented to generate **Top-N personalized movie recommendations** for a given user.

The function:
- Takes `user_id` and `N` as input
- Predicts ratings for unseen movies
- Returns the **Top-N highest predicted movies**
- Excludes movies already rated by the user

---

## Model Evaluation

To evaluate the recommendation models, the dataset is split using a **temporal split** based on timestamps. This simulates a real-world scenario where future interactions are predicted from past behavior.

Two types of evaluation metrics are used:

### Rating Prediction Metrics
- **RMSE (Root Mean Square Error)**
- **MAE (Mean Absolute Error)**

These metrics measure how accurately the system predicts user ratings.

### Ranking Metrics
- **Precision@K**
- **Recall@K**

These metrics measure how relevant the recommended movies are for the user.

---

## Model Comparison
The performance of the three recommendation approaches is compared using the evaluation metrics.

The comparison helps understand:
- Which model predicts ratings more accurately
- Which model produces better ranked recommendations
- The trade-offs between memory-based and model-based approaches

---

## Cold Start Problem
One common challenge in recommendation systems is the **cold-start problem**, where new users or new movies have no prior ratings.

A simple strategy used in this project:
- Recommend **globally popular movies**
- Recommend **highest rated movies**
- Ask new users to rate a few movies to build an initial profile

---

## Visualization
Visualizations are used to better understand both the dataset and the models. These include:

- Rating distribution plots
- Movie popularity analysis
- Visualization of latent features learned from the SVD model

These visual insights help interpret the recommendation system behavior.

---

## Technologies Used
- Python
- Pandas
- NumPy
- Surprise Library
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Key Learning Outcomes
Through this project, the following concepts were explored:

- Collaborative Filtering techniques
- User-Item interaction matrices
- Similarity metrics for recommendations
- Matrix Factorization using SVD
- Evaluation of recommendation systems
- Handling sparse datasets
- Addressing cold-start problems

This project demonstrates the complete workflow of building and evaluating a **real-world recommendation system**.

---

## Setup Instructions

1. Clone the repository

```
git clone https://github.com/23A91A4403/collaborative-filtering-movie-recommender.git
```

2. Navigate to the project directory

```
cd collaborative-filtering-movie-recommender
```

3. Install required dependencies

```
pip install -r requirements.txt
```

4. Launch Jupyter Notebook

```
jupyter notebook
```

5. Open the notebook

```
movie_recommendation_system.ipynb
```

Run all cells to reproduce the analysis, train the recommendation models, and generate personalized movie recommendations.

---

## Conclusion
This project successfully builds a **movie recommendation system** using multiple collaborative filtering approaches and evaluates their performance using different metrics.

The comparison highlights the strengths and limitations of different recommendation strategies and provides valuable insights into designing effective personalization systems used in modern platforms such as Netflix, Amazon, and Spotify.
