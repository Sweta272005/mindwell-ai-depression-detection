
# MindWell AI — Depression Risk Prediction System

## Overview
MindWell AI is a machine learning–based mental health risk assessment system designed to estimate depression risk using the PHQ-9 questionnaire, sentiment analysis, and trend monitoring.
The system integrates structured questionnaire responses with natural language emotional analysis to provide a more comprehensive evaluation of psychological state. The project demonstrates how data science, machine learning, and natural language processing techniques can support early mental health risk detection.

---

# Project Objective
The primary objectives of the MindWell AI system are:
* Predict depression risk using PHQ-9 symptom responses
* Classify individuals into different depression severity levels
* Identify the most influential depression symptoms
* Analyze emotional tone using natural language processing
* Track changes in mental health status over time
* Demonstrate an end-to-end machine learning workflow for mental health prediction
This project is designed as a prototype system for digital mental health monitoring and research.

---

# System Workflow
The MindWell AI system follows a structured data science pipeline:

User Input (PHQ-9 Responses + Text)

        ↓

Data Preprocessing
• Handle missing values
• Clean dataset
• Generate total score

        ↓

PHQ-9 Score Calculation
• Compute depression score

        ↓

Risk Classification
• Map scores to depression severity levels

        ↓

Machine Learning Model
• Logistic Regression classification

        ↓

Model Evaluation
• Accuracy
• Precision
• Recall
• F1 Score

        ↓

Sentiment Analysis
• Emotional tone detection using NLP

        ↓

Trend Monitoring
• Track mental health score changes over time

---

# PHQ-9 Depression Scoring
The PHQ-9 (Patient Health Questionnaire-9) is a clinically validated questionnaire used to assess depression severity.
Each of the nine questions is scored from 0 to 3 depending on symptom frequency.

| Response                | Score |
| ----------------------- | ----- |
| Not at all              | 0     |
| Several days            | 1     |
| More than half the days | 2     |
| Nearly every day        | 3     |

Total PHQ-9 score range: 0 – 27

# Depression Risk Classification
Based on PHQ-9 scoring guidelines, depression severity is categorized as follows:

| Score Range | Risk Level        |
| ----------- | ----------------- |
| 0 – 4       | Minimal / Safe    |
| 5 – 9       | Mild              |
| 10 – 14     | Moderate          |
| 15 – 19     | Moderately Severe |
| 20 – 27     | Severe            |

For machine learning training purposes, these categories were converted into numeric labels.

| Risk Level        | Label |
| ----------------- | ----- |
| Safe              | 0     |
| Mild              | 1     |
| Moderate          | 2     |
| Moderately Severe | 3     |
| Severe            | 4     |

---

# Dataset Preparation
The dataset used in this project contains responses to PHQ-9 questions along with behavioral indicators collected over multiple days.
The preprocessing stage involved several steps:
* Handling missing PHQ responses
* Removing incomplete records
* Restoring missing column headers
* Creating a **Total_Score** column representing the sum of PHQ responses
* Generating **Risk_Level** and **Risk_Number** columns for classification
These preprocessing steps converted the raw dataset into a machine learning–ready format.

---

# Machine Learning Model
The system uses **Logistic Regression** for depression risk classification.
### Input Features

PHQ1
PHQ2
PHQ3
PHQ4
PHQ5
PHQ6
PHQ7
PHQ8
PHQ9

### Target Variable: Risk_Number
### Training Pipeline
1. The dataset is divided into training and testing sets using an 80/20 split.
2. Missing values are handled using **SimpleImputer**.
3. A Logistic Regression model is trained on PHQ-9 responses.
4. Predictions are generated on the test dataset.

---

# Model Evaluation

The model was evaluated using standard classification metrics.

Evaluation metrics include:

* Accuracy
* Precision
* Recall
* F1 Score
* Classification Report

### Model Performance

The trained model achieved approximately:

Accuracy: ~98%

However, the dataset exhibits class imbalance, with severe depression cases appearing more frequently than other categories.

---

# Symptom Importance Analysis

Model coefficients were analyzed to determine which symptoms contribute most to depression risk prediction.

The most influential symptoms identified include:

* Difficulty concentrating
* Feelings of worthlessness
* Restlessness or agitation

This analysis helps interpret how different symptoms influence model predictions.

---

# Sentiment Analysis

In addition to PHQ-9 scoring, the system analyzes emotional tone in user-generated text using natural language processing techniques.

The project uses **TextBlob** sentiment analysis to calculate emotional polarity.

Sentiment score range:

-1 → Negative emotion
0 → Neutral emotion
+1 → Positive emotion


Example:

Text: "I feel empty and tired"
Sentiment score: Negative


This approach helps identify emotional distress expressed in textual responses.

---

# Trend Monitoring

The system also supports longitudinal analysis of mental health data.

By grouping responses using a user identifier, the model can track depression scores across multiple assessments.

Possible trend patterns include:

| Trend            | Interpretation                    |
| ---------------- | --------------------------------- |
| Increasing score | Mental health condition worsening |
| Decreasing score | Mental health condition improving |
| Stable score     | Condition unchanged               |

This feature enables monitoring of mental health progression over time.

---

# Technologies Used

The MindWell AI system was developed using the following technologies:

* Python
* Pandas
* NumPy
* Scikit-Learn
* TextBlob (Sentiment Analysis)
* Matplotlib (Visualization)
* Google Colab
* GitHub

---

# Project Structure

mindwell-ai-depression-detection
│
├── project.ipynb
├── Dataset_14-day_AA_depression_symptoms_mood_and_PHQ-9.csv
├── README.md
├── documentation.md
└── report.docx


---

# Limitations
This project has several limitations:
* Dataset imbalance between depression risk categories
* Sentiment analysis based on a simple polarity model
* The system should not be used as a medical diagnostic tool

The model is intended strictly for educational and research purposes.

---

# Future Improvements
Possible future enhancements include:

* Training advanced models such as Random Forest or XGBoost
* Implementing transformer-based sentiment models
* Developing a web interface for PHQ-9 assessment
* Integrating chatbot-based mental health support
* Deploying the system as an online monitoring platform

---

# Conclusion
MindWell AI demonstrates how machine learning and natural language processing can be integrated to support early detection of depression risk.
By combining clinical questionnaire scoring, AI-based prediction, and emotional analysis, the system provides a structured approach for mental health risk assessment and monitoring.

