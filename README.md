# Recommender System Project: Content-Based and Collaborative Filtering

## Project Overview

This project demonstrates the implementation of both **Content-Based Filtering** and **Collaborative Filtering** to build a recommendation system for a retail dataset containing customer shopping behavior. The project leverages customer reviews, item details, and ratings to recommend items to users based on their preferences and past interactions.

### Datasets

- **shopping_behavior_updated.csv**: This dataset contains information about customers, items purchased, ratings, and product features.
  
  Key columns:
  - `Customer ID`: Unique identifier for each customer.
  - `Item Purchased`: The name of the item purchased by the customer.
  - `Review Rating`: The customer's rating of the item (1-5 scale).
  - `Category`: Product category.
  - `Size`: Product size.
  - `Color`: Product color.

### Project Components

1. **Content-Based Filtering**:
   - **Feature Engineering**: We combined multiple features of the item (`Item Purchased`, `Category`, `Size`, `Color`) into a single `combined_features` string.
   - **Vectorization**: The textual data in the `combined_features` column is transformed into numerical features using the TF-IDF Vectorizer.
   - **Similarity Calculation**: Using cosine similarity, the system computes the similarity scores between items, which is used to recommend similar items to the user.
   
   **Example**: 
   If a user purchases `jeans`, the system will recommend similar items based on their attributes.

2. **Collaborative Filtering**:
   - **Surprise Library**: We used the `Surprise` library's SVD algorithm to perform collaborative filtering.
   - **Matrix Factorization**: The algorithm predicts user ratings for items they haven't interacted with based on patterns in the user-item matrix.
   - **Evaluation**: The model is evaluated using Root Mean Squared Error (RMSE) to assess its performance in predicting ratings.

   **Example**:
   Given a `Customer ID`, the system recommends items based on past interactions of similar users.

### Key Steps in the Project:

- Data Preprocessing
  - Handling missing values and creating a `combined_features` column for Content-Based Filtering.
  
- Content-Based Filtering
  - Implemented TF-IDF vectorization and cosine similarity to recommend similar items.
  
- Collaborative Filtering
  - Used the `Surprise` library to implement SVD for collaborative filtering.
  - Split data into training and test sets and evaluated the model using RMSE.

### Results

- **Content-Based Filtering**: Recommends items based on the textual features of the products.
- **Collaborative Filtering**: Recommends items based on user ratings and interactions.
- **RMSE**: The Root Mean Squared Error (RMSE) for Collaborative Filtering was `0.7182`.


Technologies Used
Python
Pandas, NumPy for data manipulation.
Scikit-learn for TF-IDF vectorization and similarity computation.
Surprise library for collaborative filtering.
Matplotlib, Seaborn for data visualization.

