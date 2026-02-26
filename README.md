# AI Concepts & Machine Learning Experiments   

---

## Project Overview

This repository contains my practical implementation of core Artificial Intelligence and Machine Learning concepts through regression and classification modelling.

The objective of this project was not simply to achieve high accuracy, but to deeply understand:

- How datasets must be cleaned and structured before modelling  
- How different algorithms behave across various random states  
- The impact of hyperparameter tuning on model performance  
- Model stability vs peak accuracy  
- The structural difference between classical ML models and neural networks  

Two real world datasets were used:
- Asia COVID-19 Cases Dataset (Kaggle)
- Student Mental Health Dataset (Kaggle)

This project reflects structured experimentation and practical implementation rather than copy-paste model building.

---

## Structure

~~~text
AI_Concepts_And_Machine_Learning
├── Classification.ipynb 
├── Regression.ipynb
├── NNRC.ipynb
├── AsiaCovidCases.csv
├── Students.csv
└── .gitignore
~~~

The `.gitignore` ensures coursework documents (e.g., Mahi2309398AI.docx) are not publicly tracked.

---

# Task 1 – Model Performance Comparison

## 1️⃣ Regression Models (COVID Dataset)

**Target Variable:** `TotalDeaths`

### Random Forest Regressor
- Highest R²: 0.99  
- Lowest R²: -2.6  
- Average R²: 0.294  

**Observation:**  
Random Forest achieved the highest peak performance. However, results varied significantly across random states, showing sensitivity to data splits.

---

### Decision Tree Regressor
- Highest R²: 0.96  
- Lowest R²: 0.13  
- Average R²: 0.59  

**Observation:**  
Decision Tree showed more stable overall performance and avoided extreme negative scores seen in Random Forest.

**Key Learning:**  
Consistency and robustness matter as much as maximum accuracy.

---

## 2️⃣ Neural Network Models

A separate dataset was used for neural network implementation to reduce preprocessing complexity.

### Neural Network – Regression
- Average Accuracy ≈ 0.53  
- Optimizer: RMSprop  
- Output Layer: Linear  

I experimented with:
- Varying neuron units  
- Reducing model complexity  
- Comparing optimizers  

Reducing neuron size improved generalisation performance on my local environment.

---

### Neural Network – Classification
- Highest Accuracy: 0.97  
- Average Accuracy: 0.94  
- Optimizer: Adam  
- Output Layer: Softmax  

This model delivered the most consistent high performance across random states.

---

## 3️⃣ Classification Models (Student Mental Health Dataset)

**Target Variable:** `Depression` (Binary: 0 / 1)

### Logistic Regression
- Average Accuracy: 0.74  
- Stable across random states  
- Tuned Parameters: `C`, `max_iter`  

The model showed strong consistency without major fluctuations.

---

### Support Vector Classifier (SVC)
- Highest Accuracy: 0.86  
- Average Accuracy: 0.76  
- Tuned Parameters: `kernel`, `C`, `random_state`  

SVC slightly outperformed Logistic Regression overall and handled the dataset effectively.

Evaluation methods used:
- Accuracy Score  
- Confusion Matrix  
- Classification Report  

---

# Data Preprocessing & Feature Engineering

Significant preprocessing was required:

### COVID Dataset
- Dropped irrelevant columns (ID, per-million metrics, redundant totals)
- One hot encoded `Country`
- Reduced dimensionality after encoding (53+ columns)

### Student Dataset
- Removed unnecessary text-heavy columns
- Converted “Family History of Mental Illness” to Boolean
- Target column already in binary format

### Neural Network Dataset
- Used `pd.factorize()` for safe label conversion
- Ensured numeric-only feature inputs

Preprocessing decisions significantly improved model clarity and performance.

---

# Hyperparameter Tuning Strategy

Instead of using default configurations, I manually experimented with:

**Random Forest**
- `n_estimators`
- `min_samples_leaf`

**Decision Tree**
- `criterion`
- `max_depth`

**Logistic Regression**
- `C`
- `max_iter`

**SVC**
- `kernel`
- `C`

**Neural Networks**
- Optimizer comparison (Adam vs RMSprop)
- Neuron count variation
- Output layer adjustments

Each configuration was tested across multiple random states to evaluate robustness.

---

# Technical Skills Demonstrated

- Data Cleaning & Feature Selection  
- One-Hot Encoding (`pd.get_dummies`)  
- Regression & Classification Modelling  
- R² Evaluation & Accuracy Metrics  
- Confusion Matrix & Classification Report  
- Neural Network Architecture Design  
- Hyperparameter Tuning  
- Overfitting Awareness  
- Model Stability Analysis  

Libraries Used:
- pandas  
- scikit-learn  
- TensorFlow / Keras  
- matplotlib  

---

# What This Project Demonstrates

- Ability to work with real-world datasets  
- Understanding of regression vs classification tasks  
- Practical use of ensemble methods  
- Neural network experimentation  
- Analytical comparison of multiple algorithms  
- Structured ML workflow implementation  

This repository forms part of my AI learning portfolio and demonstrates hands-on understanding of applied machine learning concepts.

---

# References

Datasets:
- https://www.kaggle.com/

Documentation:
- https://scikit-learn.org/stable/
- https://keras.io/api/optimizers/
- https://pandas.pydata.org/

---


This project is maintained as part of my Artificial Intelligence coursework and professional learning development.


---

## Author
Mahi Chudela
---
