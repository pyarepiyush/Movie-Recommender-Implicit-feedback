# Movie Recommender project

This project involves recommending top K movies based on a training file with existing ratings by user for a movie.  It uses the [Movielens 20M Dataset](https://grouplens.org/datasets/movielens/20m/) for a list of existing user-item ratings.


# Packages and technologies used

**[Turicreate](https://github.com/apple/turicreate)**: open-source machine-learning/deep-learning framework that is task-oriented. 

**scikit-learn:**  

# Data loading and cleaning
Following are two datasets used:
```
/ratings.csv
/movies.csv
```
To reduce sparsity, any movie with less than 50 ratings are removed.


# Training
To reduce the training time, only 10% of the data is selected for training.

The training is done assuming a binary target. So the ratings are converted into boolean (like/dislike) categories, i.e., if rating < 3.5 then 0 (dislike), else 1 (like). 

A Hyperparameter search is conducted using scikit-learn-compatible estimator (RandomizedSearchCV) on a 3-fold cross-validation F1 score of the top 10 recommendation for each user, and the best parameters are selected to train the final model. A total of 18 combinations of parameters are passed for the hyperparameter search. The best estimates might look something like this:
```

```

# Model Evaluation

From the list of 'test' users, top 10 recommended movies from the model is selected. This is compared against the list of movies those users actually liked. Based on this, we calculate recall, precision and F1-scores. 

Here are the evaluation metrics:
```
recall: 0.08
precision: 0.01
F1: 0.02
```
Here are some actual examples of 










