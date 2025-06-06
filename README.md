
<h1 align="center">🧠 Machine Learning for Stroke Risk Prediction</h1>

<p align="center">
  <img src="https://img.shields.io/badge/R-Data%20Science-blue?logo=r&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Shiny-App%20Deployed-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Machine%20Learning-HealthTech-orange?style=for-the-badge" />
</p>

<p align="center">
  <em>A complete machine learning pipeline with real-time deployment using Shiny.<br/>
  Built to assist in early stroke detection and personalized prevention strategies.</em>
</p>

---

## 🚀 Project Summary

> 🧑‍⚕️ **Goal**: Predict the likelihood of stroke occurrence using individual health and demographic data.

This project:
- Implements multiple **ML models in R** with the `caret` and `Boruta` packages
- Uses **feature selection**, **cross-validation**, and **resampling**
- Deploys an **interactive Shiny app** to assess individual stroke risk

---

## 🗂️ Table of Contents

- [📁 Project Structure](#-project-structure)
- [📊 Data Overview](#-data-overview)
- [🧹 Preprocessing](#-data-preprocessing)
- [📈 Feature Selection](#-feature-selection)
- [🧪 Model Development](#-model-training--evaluation)
- [🌐 Shiny App](#-shiny-app)
- [🛠️ Installation](#-installation--usage)
- [👤 Author](#-author)
- [📄 License](#-license)

---

## 📁 Project Structure

```bash
Machine-Learning-for-Stroke/
├── data/               # Raw stroke dataset (CSV)
├── models/             # Model training & evaluation scripts
├── shiny_app/          # Shiny app code
├── reports/            # EDA results & visualizations
└── README.md           # This file
```

---

## 📊 Data Overview

- **Rows**: 5,110  
- **Features**: 12 (demographic + health metrics)  
- **Target**: `stroke` (binary: Yes/No)

EDA ensured:
- Type integrity, missing value cleanup
- Removal of outliers (`BMI`)
- Removal of irrelevant columns (`id`)
- Detection of class imbalance (`stroke: 4700 No / 209 Yes`)

---

## 🧹 Data Preprocessing

✔️ Label-encoded categorical variables  
✔️ Converted BMI to numeric and removed non-numeric entries  
✔️ Dropped `id`, `gender`, and `Residence_type` as non-informative  
✔️ Applied **downsampling** to balance the target classes

---

## 🔍 Feature Selection

Used the **Boruta algorithm** (based on Random Forest) to identify important predictors.

🎯 **Selected Features**:
```
age, hypertension, heart_disease, ever_married,
work_type, avg_glucose_level, bmi, smoking_status
```

❌ `gender` and `Residence_type` were excluded.

---

## 🧪 Model Training & Evaluation

### 🛠️ Training Control Strategy

```r
fitcontrol = trainControl(
  method = "repeatedcv",
  number = 10,
  repeats = 3,
  classProbs = TRUE,
  summaryFunction = twoClassSummary
)
```

- 10-fold cross-validation repeated 3 times
- Evaluation metrics: **AUC**, **Sensitivity**, **Specificity**
- Resampling reduces overfitting and improves reliability

---

### 🤖 Models Trained

| Model                  | AUC    | Accuracy | Sensitivity | Specificity |
|-----------------------|--------|----------|-------------|-------------|
| ✅ Logistic Regression | **0.8413** | 77.4%    | 73.8%       | 80.9%       |
| 🌳 Random Forest       | 0.8302 | 76.2%    | 73.8%       | 78.6%       |
| 🔍 Decision Tree       | 0.8053 | 73.8%    | 73.8%       | 73.8%       |
| 🌀 SVM (Radial)        | 0.8163 | 73.8%    | 69.1%       | 78.6%       |
| 🧩 K-Nearest Neighbors | 0.7333 | 67.9%    | 69.2%       | 66.7%       |
| ⚡ GBM (in progress)   | *Tuned*| *Tuned*  | *Tuned*     | *Tuned*     |

> 🥇 **Best Performer**: Logistic Regression (high AUC, simple and interpretable)

---

## 🌐 Shiny App

<p align="center">
  <img src="https://user-images.githubusercontent.com/placeholder/stroke-app-ui.png" alt="Shiny App Screenshot" width="80%" />
</p>

The app allows users to:
- Enter age, glucose, work type, BMI, smoking status, etc.
- Receive instant stroke risk predictions
- View prediction confidence (probability output)

```r
shiny::runApp("shiny_app/")
```

---

## 🛠️ Installation & Usage

### 🔧 Prerequisites

Install required packages:
```r
install.packages(c("caret", "Boruta", "tidyverse", "pROC", "caTools", "randomForest", "shiny"))
```

### 🚀 Run the App Locally

```r
# Clone the repo
git clone https://github.com/yourusername/Machine-Learning-for-Stroke.git

# Launch the app
shiny::runApp("Machine-Learning-for-Stroke/shiny_app/")
```

---

## 👤 Author

**Enock Bereka**  
📍 Data Scientist | ML Engineer | HealthTech Enthusiast  
📅 Created: May 25, 2025  

<p>
  <a href="https://github.com/yourusername"><img src="https://img.shields.io/badge/GitHub-Profile-black?logo=github&style=flat-square" /></a>
  <a href="https://linkedin.com/in/your-link"><img src="https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin&style=flat-square" /></a>
</p>

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 🌟 Key Highlights

✅ End-to-end data science workflow  
✅ Real-time predictions via deployed web app  
✅ Feature selection with interpretability  
✅ Balanced model metrics for medical fairness  
✅ Professionally structured & documented codebase  

> 💼 **Looking for opportunities** in Data Science, AI, or HealthTech. Let’s connect!
