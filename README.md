# 🧬 HIV Risk Prediction Using Machine Learning

This project applies machine learning techniques to predict HIV risk using a simulated behavioral surveillance dataset. It showcases a full data science pipeline in R — from feature selection to model tuning and evaluation — with a focus on clarity, interpretability, and reproducibility.

---

## 📁 Project Overview

- **Data**: (`HIV_RISK_SIMULATED.csv`) is a fully synthetic, de-identified behavioral surveillance dataset of 5,000 individuals, generated for the purpose of demonstrating predictive modeling workflows. No real patient data is used.  
- **Outcome**: Binary HIV risk classification (Low vs. High)  
- **Tools**: R, Quarto, tidymodels, ranger, vip, gtsummary, gt, ggplot2  
- **Deliverable**: Manuscript-style Quarto HTML report  
- **Manuscript**: [📄 View the full report here](https://paolabeato.github.io/hivrisk-classifier/index.html)  

---

## 🔍 Methods

### 1. Data Simulation & Cleaning
- Predictor generation: 5,000 individuals simulated with demographic (age, sex, education, race) and behavioral (number of partners, condom use, drug use, transactional sex, recent STI, PrEP awareness) features.

- Distributions: variables drawn from appropriate distributions (e.g., age from truncated normal, partners from Poisson, categorical factors from multinomial probabilities reflecting realistic prevalences).

- Outcome assignment: a probabilistic HIV risk group (“Low” vs. “High”) generated using rule-based logic informed by known epidemiologic risk factors (e.g., transactional sex, STI history, condom non-use, multiple partners), with random variation introduced to avoid deterministic labeling.

- Cleaning & labeling: categorical variables converted to factors with descriptive labels, and variable labels added for interpretability in summary tables and model outputs.

### 2. Exploratory Data Analysis (EDA)
- Visual comparisons of low vs. high-risk individuals  
- Summary tables and plots using **gtsummary** and **ggplot2**  

### 3. Predictor Selection
- Information Gain used to select top 8 predictors  
- Behavioral factors (e.g., drug use, transactional sex) ranked highest  

### 4. Modeling
Three models were developed using **tidymodels**:  
- **Logistic Regression** — interpretable baseline  
- **Random Forest (Untuned)** — nonlinear ensemble model  
- **Tuned Random Forest** — optimized with 5-fold cross-validation  

### 5. Evaluation
- Accuracy, Cohen’s Kappa, ROC AUC  
- Confusion matrices and variable importance plots  
- Combined ROC curve to compare model performance  

---

## ✅ Results Summary

| Model                | Accuracy | Cohen's Kappa | ROC AUC |
|----------------------|----------|---------------|---------|
| Logistic Regression  | ~83.5%   | ~58.8%        | ~83.2%  |
| Random Forest        | ~87.9%   | ~70.1%        | ~90.8%  |
| Tuned RF             | ~85.7%   | ~64.2%        | ~94.2%  |

- 🟧 **Tuned RF** showed the strongest **discriminative performance** (highest AUC)  
- 🟩 **Untuned RF** achieved the highest raw **accuracy**, but risked overfitting  
- 🔵 **Logistic Regression** was interpretable but limited in nonlinear signal capture  

> 📌 **All models were evaluated on the same held-out test set for fair comparison**

---

## 💡 Key Takeaways

- Behavioral risk factors (e.g., condom use, STI history) dominated prediction  
- Hyperparameter tuning improved discrimination and generalizability  
- Random Forest models offer a powerful balance between performance and interpretability in public health contexts  

---

## ⚠️ Limitations

- Simulated data limits generalizability to real-world populations  
- HIV risk was treated as binary (low/high), though risk is often continuous  
- Models were not optimized for cost-sensitive misclassification  

---

## 🔑 Code Availability

The full R/Quarto source code for this analysis is **available upon request**.  
This repository highlights the **reproducible results** and manuscript-ready output.  

---

## 👩‍💻 Author Notes

This project was created as a **portfolio piece** to demonstrate:  
- Applied skills in **biostatistics** and **machine learning**  
- Proficiency with the **tidymodels** framework  
- A clean, documented, and reproducible **Quarto** pipeline  
- Emphasis on **interpretability**, **visual storytelling**, and **public health insight**  

---
