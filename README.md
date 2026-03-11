# Predictive Maintenance using NoSQL and Machine Learning

## Overview

This project implements a **predictive maintenance system** that analyzes industrial machine sensor data and predicts the probability of machine failure using machine learning models.

The project was inspired by an existing research paper that uses machine learning to detect machine stoppages based on IoT sensor data. However, the implementation was adapted and extended to build a **practical data mining system using a NoSQL database and customizable datasets**.

The system processes machine sensor parameters such as temperature, torque, rotational speed, and tool wear to predict whether a machine is likely to fail.

---

# Research Paper Inspiration

The initial research paper focuses on training a machine learning model on industrial sensor data to **predict machine failures and stoppage conditions**.

### Original Approach

The research paper used the **AdaBoost (Adaptive Boosting) algorithm** as the primary machine learning model.

**AdaBoost** is an ensemble learning algorithm that combines multiple weak learners (usually decision trees) to form a stronger predictive model.

Workflow in the research paper:

Sensor Data → Preprocessing → AdaBoost Model → Failure Prediction

The goal was to classify machine stoppage conditions using IoT-based industrial data.

---

# Changes Introduced in This Project

This project extends the original research idea by introducing several modifications and improvements.

## 1. Custom Dataset Upload

The system allows users to upload their own **CSV datasets** to train the machine learning model.

Currently, datasets must follow the **AI4I Predictive Maintenance dataset format**, which includes parameters such as:

* Air Temperature
* Process Temperature
* Rotational Speed
* Torque
* Tool Wear
* Machine Failure Label

This allows the system to be used for **dynamic data analysis instead of a fixed dataset**.

---

## 2. NoSQL Data Storage

The uploaded dataset is stored in **MongoDB**, a NoSQL database.

Benefits:

* Flexible schema storage
* Efficient handling of large datasets
* Suitable for data mining workflows

Each row of the dataset is stored as a **document in MongoDB**.

---

## 3. Data Preprocessing and Cleaning

Additional preprocessing steps were introduced before training the machine learning model.

These steps include:

* Cleaning missing or inconsistent values
* Dropping unnecessary columns
* Formatting the dataset for model compatibility
* Preparing features and labels for training

These preprocessing steps improve model reliability and training accuracy.

---

# Machine Learning Model Changes

One of the main changes from the research paper was **replacing the AdaBoost model with different machine learning algorithms** better suited for the AI4I dataset.

## Model Used in the Research Paper

**AdaBoost (Adaptive Boosting)**

Type: Ensemble learning algorithm
Purpose: Combine multiple weak learners into a strong predictive classifier.

---

## Models Used in This Project

### Random Forest Classifier

Random Forest is an ensemble learning algorithm that creates multiple decision trees and combines their predictions.

Dataset → Multiple Decision Trees → Majority Voting → Final Prediction

### Why Random Forest?

Random Forest works very well for **tabular industrial datasets** like AI4I because it:

* Handles non-linear relationships
* Works well with multiple sensor features
* Reduces overfitting
* Provides feature importance insights

It is particularly effective when working with parameters such as:

* Air Temperature
* Process Temperature
* Torque
* Rotational Speed
* Tool Wear

---

### Support Vector Machine (SVM)

**Support Vector Machine (SVM)** is a supervised learning algorithm that classifies data by finding the optimal separating boundary between classes.

### Why SVM?

SVM performs well for:

* Binary classification problems
* High-dimensional datasets
* Structured sensor data

Since predictive maintenance datasets typically predict:

Machine Failure = 0 or 1

SVM is well suited for this classification task.

---

# Key Difference Between the Research Paper and This Project

| Component         | Research Paper                       | This Project                        |
| ----------------- | ------------------------------------ | ----------------------------------- |
| Main ML Algorithm | AdaBoost (Adaptive Boosting)         | Random Forest + SVM                 |
| Model Type        | Boosting Ensemble                    | Ensemble + Margin-based classifier  |
| Dataset           | Industrial knitting machine IoT data | AI4I Predictive Maintenance dataset |
| Objective         | Classify machine stoppage types      | Predict machine failure             |

---

# Project Workflow

Dataset Upload → MongoDB Storage → Data Cleaning → Feature Selection → Model Training → Failure Prediction

Steps:

1. Upload dataset (CSV)
2. Store dataset in MongoDB
3. Perform data preprocessing
4. Train machine learning models
5. Predict machine failure
6. Evaluate model performance

---

# Technologies Used

* **MongoDB (NoSQL Database)**
* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Data Visualization Techniques**

---

# Objective

The goal of this project is to demonstrate how **data mining techniques on NoSQL databases combined with machine learning algorithms** can be used to build an effective predictive maintenance system.

Such systems help industries **predict equipment failures in advance**, reducing downtime and improving maintenance efficiency.
