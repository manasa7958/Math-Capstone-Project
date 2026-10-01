# Predicting Online News Popularity with Regularized Linear Models

## Overview

What makes an online news article popular? Is popularity associated with an article's topic, sentiment, length, use of images and videos, publication timing, or some combination of these characteristics?

This project explores whether characteristics of online news articles can be used to predict their popularity, measured by the number of times an article is shared. The analysis uses the **Online News Popularity dataset** created by Fernandes, Vinagre, and Cortez, which contains approximately 40,000 Mashable articles and 58 predictive features, including article length, number of images and videos, keywords, topic information, publication timing, sentiment, and subjectivity.

The main goal is not simply to build the most accurate prediction model. Instead, this project investigates how **regularization and dimensionality reduction affect linear regression models when working with a relatively large set of potentially correlated predictors**.

## Research Questions

The project focuses on two main questions:

1. Can regularization improve the prediction of online news popularity compared with ordinary linear regression?
2. Which article characteristics provide the most useful information for predicting popularity?

## Models

Four linear modeling approaches will be compared:

### 1. Ordinary Least Squares (OLS)

OLS will serve as the baseline model. It estimates a coefficient for each predictor by minimizing the sum of squared prediction errors.

This provides a reference point for determining whether regularization improves out-of-sample prediction.

### 2. Ridge Regression

Ridge Regression extends ordinary least squares by adding an **L2 penalty** to the regression coefficients.

The penalty shrinks coefficients toward zero and can reduce overfitting when predictors are correlated. The regularization parameter, λ, will be selected using cross-validation.

### 3. Lasso Regression

Lasso Regression introduces an **L1 penalty**.

Unlike Ridge, Lasso can shrink some coefficients completely to zero. This makes Lasso useful not only for prediction but also for **feature selection**, allowing the project to investigate which article characteristics remain most useful after regularization.

### 4. Principal Component Regression (PCR)

Principal Component Regression first applies **Principal Component Analysis (PCA)** to transform the original predictors into a smaller set of uncorrelated principal components.

Regression is then performed using a selected number of these components. This allows the project to examine whether the information contained in dozens of article characteristics can be represented using a much smaller number of dimensions.

## Model Comparison

The models will be trained and evaluated using the same data split and compared using out-of-sample prediction metrics such as:

* Root Mean Squared Error (RMSE)
* Mean Absolute Error (MAE)
* R²

The analysis will also examine how regularization changes model coefficients, which variables are retained by Lasso, and how predictive performance changes as the number of principal components varies.

## Dataset

The project uses the **Online News Popularity** dataset from the UCI Machine Learning Repository.

The dataset contains **39,797 observations and 58 predictive features** derived from articles published by Mashable over a two-year period. The target variable, `shares`, represents the number of times each article was shared.

Source: UCI Machine Learning Repository, *Online News Popularity*.
