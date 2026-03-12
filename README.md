# LLMs as Explainability Layer for ML-Based Asthma Prediction Model

An **Explainable AI framework for asthma prediction** that integrates **Machine Learning, SHAP explainability, and Large Language Models (LLMs)** to generate **human-readable explanations**.

This project demonstrates how **black-box ML predictions can be transformed into interpretable insights**, improving transparency in healthcare AI systems.

---

## Project Overview

Asthma affects millions of people worldwide, yet many machine learning models used for prediction behave like **black boxes**, making their decisions difficult to interpret.

This project introduces a system that:

- Predicts asthma risk using **Machine Learning**
- Explains predictions using **SHAP feature attribution**
- Converts technical explanations into **natural language using an LLM**

The goal is to **improve trust and interpretability in AI-based healthcare systems**.

---

## Architecture
Dataset → ML Model (SVM) → SHAP Feature Attribution → LLM Explanation → Human-Readable Output

1. Dataset is processed and fed into a trained **SVM model**
2. **SHAP values** identify feature importance for each prediction
3. Feature explanations are sent to a **Large Language Model**
4. The LLM generates a **simple natural language explanation**

---

## Dataset

- **Dataset:** Asthma Health Dataset  
- **Source:** Kaggle  
- **Total Records:** 10,000  
- **Features:** 14  

### Example Features

- Age  
- Gender  
- BMI  
- Smoking History  
- Family History  
- Air Pollution Level  
- Physical Activity  
- Comorbidities  
- ER Visits  
- Peak Expiratory Flow  

### Target Variable
Has Asthma
0 → No
1 → Yes


---

## Machine Learning Model

**Model Used:** Support Vector Machine (SVM)

Configuration:
Kernel = RBF
C = 10
Probability = True



**Model Accuracy:**  
**98.29%**

---

## Explainable AI Methods

To understand the model's predictions, we used:

### SHAP (SHapley Additive Explanations)

SHAP identifies **which features contributed most to the prediction**.

Benefits:

- Local explanation per patient
- Quantitative feature attribution
- Model interpretability

---

## LLM-Based Explanation Generation

Technical explanations from SHAP can still be difficult for non-technical users.

Therefore we used:

**LLM Model:** Mistral Large

The LLM converts SHAP feature contributions into **human-readable explanations**.

Example explanation style:

> The predicted asthma risk is influenced by factors such as smoking history, air pollution exposure, and reduced peak expiratory flow. These factors are known to increase respiratory stress and may contribute to a higher likelihood of asthma symptoms.

---

## Prompt Design

The prompt used for the LLM follows a structured reasoning format:

1. Identify the key factors influencing the prediction  
2. Explain how these factors affect asthma risk  
3. Interpret the predicted risk level  
4. Provide general health considerations  

### Safety Constraints

- No mention of machine learning algorithms  
- No medical diagnosis  
- Use simple and understandable language  

---

## Explainability Evaluation

To evaluate the reliability of generated explanations, two metrics were used.

### Fidelity

Measures alignment between **SHAP important features and LLM explanations**.

Result:
Fidelity = 0.619


Meaning:  
Most important features identified by SHAP are mentioned in the explanation.

---

### Entropy

Measures **consistency of explanations across multiple runs**.

Result:
Entropy = 0.346


Interpretation:  
Low entropy indicates **stable and consistent explanations**.

---

## Technologies Used

- Python  
- Scikit-learn  
- SHAP  
- Pandas  
- NumPy  
- Mistral Large (LLM)  
- Jupyter Notebook  

---

## Repository Structure

project
│
├── asthma_dataset.csv
├── asthma_prediction_model.ipynb
├── shap_explainability.py
├── llm_explanation_generator.py
├── evaluation_metrics.py
└── README.md



---

## Key Contributions

- Asthma prediction using **SVM**
- Feature attribution using **SHAP**
- Natural language explanations using **LLM**
- Reliability evaluation using **Fidelity and Entropy**

---

## Future Work

- Clinical validation with medical experts
- Training on larger healthcare datasets
- Integration into clinical decision support systems
- Real-time patient explainability dashboards

---

## Authors

**Shivam Pawar**  
B.Tech Artificial Intelligence & Machine Learning  
Manipal University Jaipur  

