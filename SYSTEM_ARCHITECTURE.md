# 🧠 MindWell AI — System Architecture

## Architecture Overview

The MindWell system follows a **modular AI architecture** that integrates questionnaire-based assessment with machine learning and natural language processing.

The architecture consists of **five main layers**:

1. Input Layer
2. Data Processing Layer
3. Machine Learning Layer
4. NLP Analysis Layer
5. Output & Monitoring Layer

Each layer performs a specific role in the depression risk prediction pipeline.

---

# 1️⃣ Input Layer

The input layer collects user data required for mental health assessment.

### Structured Input

PHQ-9 questionnaire responses.
PHQ1
PHQ2
PHQ3
PHQ4
PHQ5
PHQ6
PHQ7
PHQ8
PHQ9

Each response represents a depression symptom intensity.

### Unstructured Input

Optional emotional text written by the user.

Example:
"I feel exhausted and cannot concentrate."

This input is later analyzed using NLP.

---

# 2️⃣ Data Processing Layer

This layer prepares the dataset before machine learning analysis.

Key operations include:

* Missing value detection  
* Feature extraction  
* Score computation  
* Risk label generation  

### Feature Engineering

New variables are created to represent depression severity.
Total_Score
Risk_Level
Risk_Number

These features convert raw questionnaire responses into model-ready variables.

---

# 3️⃣ Machine Learning Layer

This layer performs the **core risk prediction task**.

### Model Used
Logistic Regression

The model learns relationships between PHQ responses and depression severity.

### Model Inputs
PHQ1 – PHQ9

### Model Output
Predicted_Risk_Number

The output represents the predicted depression risk category.

---

# 4️⃣ Symptom Analysis Module

After prediction, model coefficients are used to determine **symptom influence**.

This module analyzes which PHQ variables contribute most strongly to the predicted risk.

Example insights:

* Concentration difficulty  
* Feelings of worthlessness  
* Restlessness  

This step improves **model interpretability**.

---

# 5️⃣ NLP Emotion Analysis Layer

This module processes emotional text using sentiment analysis.

Tool used:
TextBlob

The model calculates a **polarity score**:
Range: -1 to +1

Interpretation:

| Sentiment | Meaning |
|----------|--------|
| Negative | Emotional distress |
| Neutral | Balanced emotional tone |
| Positive | Stable emotional state |

This allows the system to incorporate **linguistic emotional signals**.

---

# 6️⃣ Temporal Monitoring Layer

The system supports repeated assessments from the same user.

Using:
groupby(user_id)

the system tracks depression scores across multiple sessions.

This enables detection of **behavioral patterns over time**.

Possible outcomes:

* Improvement  
* Worsening condition  
* Stable mental state  

---

# 7️⃣ Output Layer

The final layer produces interpretable results.

Outputs include:

* Predicted depression risk level  
* Dominant symptom indicators  
* Sentiment polarity score  
* Historical score visualization  

These outputs can be used to support **mental health awareness tools**.

---

# Architecture Characteristics

The MindWell architecture has the following properties:

**Modular design**  
Each component can be updated independently.

**Hybrid analysis**  
Combines clinical questionnaires with AI models.

**Explainable outputs**  
Symptom importance provides transparency.

**Extensible pipeline**  
New models or NLP tools can easily be integrated.

---

# Scalability Potential

The system architecture can be extended for large-scale applications such as:

* Web-based mental health platforms  
* Mobile mental health screening apps  
* AI mental health chatbots  
* Population mental health monitoring systems  

---

# Summary

The MindWell architecture demonstrates a layered AI system where structured questionnaire data, machine learning models, and sentiment analysis are integrated to provide an intelligent mental health risk evaluation framework.
