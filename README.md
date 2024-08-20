# Credit Card Fraud Detection

This repository contains the code and resources for a project aimed at detecting fraudulent transactions using machine learning techniques. The project utilizes a dataset of credit card transactions, with the goal of building a model that can accurately identify fraudulent activities.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Modeling](#modeling)
- [Evaluation](#evaluation)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview

Credit card fraud is a significant concern in the financial industry, causing substantial losses every year. This project aims to address this issue by developing a machine learning model to detect fraudulent transactions. The dataset is highly imbalanced, with fraudulent transactions being very rare compared to legitimate ones. Therefore, this project also explores techniques to handle imbalanced datasets, such as resampling methods and the use of specialized algorithms.

## Dataset

The dataset used in this project is a [Credit Card Fraud Detection dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud) available on Kaggle. It contains transactions made by credit cards in September 2013 by European cardholders. 

### Features

- The dataset has 31 columns:
  - **Time**: Number of seconds elapsed between this transaction and the first transaction in the dataset.
  - **V1** to **V28**: These are the principal components obtained with PCA, and the names are not provided to protect sensitive information.
  - **Amount**: Transaction amount.
  - **Class**: Target variable (1 = Fraudulent, 0 = Legitimate).

### Data Characteristics

- **Imbalance**: The dataset is highly imbalanced with only 0.172% of transactions being fraudulent.
- **Size**: 284,807 transactions with 492 cases of fraud.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/credit-card-fraud-detection.git
    cd credit-card-fraud-detection
    ```

2. Create and activate a virtual environment:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Exploratory Data Analysis (EDA)

The Exploratory Data Analysis phase involves understanding the distribution of the features, checking for class imbalance, and identifying any patterns that could be useful for detecting fraud. Key steps include:

- Visualizing the distribution of transaction amounts.
- Analyzing the distribution of fraudulent vs. legitimate transactions.
- Exploring the correlation between features.

The EDA is documented in the `notebooks/EDA.ipynb` file.

## Feature Engineering

Feature engineering involves creating new features or transforming existing ones to improve model performance. In this project:

- **Scaling**: The `Amount` feature is scaled to standardize the data.
- **Feature Selection**: Relevant features are selected based on their correlation with the target variable.

These processes are implemented in `src/data_preprocessing.py`.

## Modeling

Given the highly imbalanced nature of the dataset, several models are explored with techniques to handle imbalance, including:

- Logistic Regression
- Decision Trees
- Random Forest
- Gradient Boosting Machines
- XGBoost
- Support Vector Machines (SVM)
- Neural Networks

Resampling methods like **SMOTE** (Synthetic Minority Over-sampling Technique) and **undersampling** are also applied to balance the dataset. The modeling process is detailed in the `notebooks/Modeling.ipynb` notebook.

## Evaluation

Models are evaluated based on:

- **Precision**: Proportion of true positive instances among the instances predicted as fraud.
- **Recall**: Proportion of true positive instances among the actual fraud instances.
- **F1 Score**: Harmonic mean of Precision and Recall.
- **ROC-AUC**: Area under the Receiver Operating Characteristic curve.
- **Confusion Matrix**: Detailed classification results.

Given the imbalance, metrics like Precision-Recall AUC are 
