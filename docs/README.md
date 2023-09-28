# Titanic Survival Analysis

## Overview

This project explores the Titanic dataset to understand various factors that might have influenced the passengers' survival. The analysis encompasses data cleaning, exploratory data analysis (EDA), and predictive modeling using Logistic Regression, Random Forest, and Decision Tree algorithms.

## Table of Contents

1. Data Import & Preliminary Analysis
2. Data Cleaning & Feature Engineering
3. Exploratory Data Analysis (EDA)
4. Logistic Regression Model
5. Random Forest Model
6. Decision Tree Model

## 1. Data Import & Preliminary Analysis

The dataset is initially loaded to understand the available information. It's noted that the hold-out data lacks the target variable 'Survival', which will be addressed in the modeling section.

## 2. Data Cleaning & Feature Engineering

### 2.1 Handling Missing Values

- **Age:** Around 20% of the Age data is missing. Given the right-skewed distribution, the median value is used to impute missing entries.
- **Cabin:** Due to a high percentage (77%) of missing values, this variable is excluded from the analysis.
- **Embarked:** Two missing values are imputed with 'S', representing Southampton, the port where most passengers boarded.

### 2.2 Feature Engineering

- **Family Travel:** Variables `SibSp` and `Parch` are combined to create a new categorical variable indicating whether a passenger was traveling alone or with family.
- **Minor:** A new categorical variable is introduced to indicate if a passenger is under 16.
- **Dummy Variables:** Created for Passenger Class (`Pclass`), Gender (`Sex`), and Port Embarked (`Embarked`).

The same imputation and feature engineering steps are applied to the test data.

## 3. Exploratory Data Analysis (EDA)

### 3.1 Age Distribution

A higher proportion of survivors were children, indicating a likely preference for saving children.

### 3.2 Fare Distribution

Passengers who paid a higher fare were more likely to survive, possibly correlating with Passenger Class.

### 3.3 Passenger Class

First-class passengers had a higher survival rate.

### 3.4 Embarked Port

Passengers from Cherbourg had a higher survival rate, possibly related to passenger class or cabin location.

### 3.5 Family Travel

Individuals traveling with family had a higher survival rate.

### 3.6 Gender

Female passengers had a significantly higher survival rate.

## 4. Logistic Regression Model

The logistic regression model yielded a predictive score of 0.7935. The model's performance was further validated using an 80-20 split for cross-validation. The AUC score indicated a strong classification power between survived and deceased occurrences.

## 5. Random Forest Model

Random Forest, with 100 trees, provided a better out-of-sample predictive power compared to Logistic Regression. The same set of variables was used for this model.

## 6. Decision Tree Model

A Decision Tree model was also built to compare the performance against previous models. The model was pruned to avoid overfitting, and the same set of variables was used for this analysis.

## Conclusion

The analysis revealed that being a young, female passenger in the first class, embarking from Cherbourg, significantly increased the chances of survival on the Titanic. The Random Forest model, with 100 trees, provided the most accurate predictions among the three models.
