# ak05144
Repository for organizing, managing, and maintaining assignments, projects, and related coursework for the BITS M.Tech in Artificial Intelligence and Machine Learning (AI/ML) program.

## Project Overview
This project focuses on building and comparing several machine learning classifiers for a binary classification problem: predicting whether a client will subscribe to a term deposit after a marketing campaign call. A Streamlit-based application is also included to evaluate trained models on uploaded test data and display metrics such as accuracy, AUC, precision, recall, F1-score, and confusion matrices.

## a) Problem Statement
The objective of this project is to predict whether a customer will subscribe to a bank term deposit based on their demographic, financial, and campaign-related attributes. This is a supervised binary classification task where the target variable is:

- y = 1: customer subscribes to the term deposit
- y = 0: customer does not subscribe

The challenge is to build a model that can accurately identify potential customers for a bank marketing campaign while balancing precision and recall, since misclassifying a potential customer can affect campaign efficiency.

## b) Dataset Description
The dataset used in this project is the UCI Bank Marketing dataset, a real-world marketing dataset commonly used for classification tasks in customer targeting.

### Source
- UCI Machine Learning Repository: Bank Marketing

### Dataset characteristics
- Type: Tabular classification dataset
- Rows: approximately 41,000 records
- Features: customer profile, current financial status, and previous campaign interactions
- Target variable: y (subscription outcome)
- Training setup: The dataset is processed and used to train five classifiers
- Preprocessing: the feature duration is excluded during model training to avoid data leakage

### Example feature categories
- Age and job type
- Marital status
- Education level
- Default status
- Housing and personal loan status
- Contact method and month of contact
- Campaign outcome history
- Previous campaign results
- Employment variation rate, consumer price index, and other economic indicators

The app supports uploaded CSV files and auto-detects whether the separator is comma-separated or semicolon-separated.

## c) Models Used
The project evaluates multiple classification algorithms to compare their predictive performance:

- Logistic Regression
- Decision Tree
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Support Vector Machine (SVM)

These models are trained and saved as joblib pipelines in the model directory, and a Streamlit interface allows users to select a model and test it on new data.

## d) Comparison Table
The following table shows the performance of the trained models on the evaluation dataset.

| Model | Accuracy | AUC | Precision | Recall | F1 Score | MCC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8337 | 0.7599 | 0.6423 | 0.7166 | 0.6648 | 0.3510 |
| Support Vector Machine | 0.8532 | 0.7326 | 0.6572 | 0.7080 | 0.6764 | 0.3617 |
| Naive Bayes | 0.8374 | 0.7354 | 0.6334 | 0.6845 | 0.6512 | 0.3138 |
| KNN | 0.8920 | 0.6645 | 0.7116 | 0.5689 | 0.5906 | 0.2415 |
| Decision Tree | 0.8410 | 0.6232 | 0.6096 | 0.6232 | 0.6156 | 0.2323 |

## e) Observation on Model Performance
Based on the comparison table:

- KNN yields the highest raw accuracy (0.8920), but its AUC and recall are weaker than Logistic Regression and SVM.
- Logistic Regression has the highest AUC (0.7599) and recall (0.7166), making it a strong baseline for identifying likely subscribers.
- Support Vector Machine provides a balanced result, with an AUC of 0.7326 and an MCC of 0.3617 on the held-out test split.
- Naive Bayes has competitive AUC, while Decision Tree has the weakest AUC and MCC among these models.

### Conclusion
No single model leads on every metric: KNN has the highest accuracy, Logistic Regression the highest AUC and recall, and SVM the highest F1 score and MCC. The preferred model depends on which evaluation metric best fits the campaign objective.

## Repository Contents
- test_data.csv: sample test data for model evaluation
- model/: trained model files and evaluation summary
- app.py: Streamlit application for model evaluation and prediction
- README.md: project documentation

## Usage
The project includes a Streamlit app that allows a user to:

1. Upload a test CSV file
2. Select a trained model
3. View evaluation metrics
4. Inspect confusion matrix and classification report
5. Download predictions

This repository is intended for coursework and academic project organization related to ML classification tasks
