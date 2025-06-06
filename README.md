**🧠 Machine Learning for Stroke Risk Prediction**

A full-stack data science solution integrating machine learning, feature engineering, model evaluation, and an interactive Shiny web app for real-time stroke risk assessment. This project leverages R’s caret, Boruta, and Shiny packages to build interpretable and robust models applicable to real-world healthcare decision-making.

**💡 Objective**

To predict stroke occurrence using patient health and demographic data, enabling early detection and supporting personalized preventive strategies in clinical environments.

**📊 Overview**

Language & Tools: R, Shiny, caret, Boruta, pROC, caTools, RandomForest

ML Techniques: Logistic Regression, Random Forest, SVM, Decision Trees, KNN, GBM

Imbalance Handling: Downsampling

Feature Selection: Boruta wrapper over Random Forest

Deployment: Shiny web application for interactive risk screening

**📁 Project Structure**
bash
Copy
Edit
Machine-Learning-for-Stroke/
│
├── data/               # Dataset (CSV)
├── models/             # R scripts for training and evaluation
├── shiny_app/          # Shiny UI & server scripts
├── reports/            # EDA, visualizations, Boruta results
└── README.md           # This file
🧬 Dataset Summary
📄 Source: Stroke prediction dataset (stroke.csv)

🧑‍🤝‍🧑 Rows: 5,110 | 🔢 Features: 12

🎯 Target: Binary classification (stroke: Yes/No)

**🔍 Exploratory Data Analysis (EDA)**
Checked structure and types using glimpse()

Verified and handled missing values (bmi column cleaned)

Removed duplicates and the non-informative id column

Identified class imbalance (4700:209 → Yes:No)

**🧹 Data Preprocessing**

Applied label encoding to categorical features

Converted all features to appropriate data types

Cleaned the bmi column and removed non-numeric values

Addressed class imbalance via downsampling to balance positive/negative stroke cases

**🌟 Feature Selection with Boruta**

Used the Boruta algorithm, a powerful wrapper around Random Forests, to determine the most predictive features.

**✅ Selected Features:**

age, hypertension, heart_disease, ever_married, work_type, avg_glucose_level, bmi, smoking_status

❌ Rejected Features:

gender, Residence_type

These insights informed feature reduction for model simplicity and improved performance.

**🔀 Train-Test Splitting**

Performed an 80/20 split using caTools::sample.split() for unbiased evaluation.

**🛠️ Preparing the Training Scheme**

Utilized caret::trainControl() to define a rigorous resampling strategy:

r
Copy
Edit
fitcontrol = trainControl(
  method = "repeatedcv",
  number = 10,
  repeats = 3,
  classProbs = TRUE,
  summaryFunction = twoClassSummary
)
Why this matters:

Repeated 10-fold CV ensures model generalizability

Class probabilities allow probabilistic thresholding

AUC, Sensitivity, Specificity used instead of plain accuracy—crucial for imbalanced data

**🧠 Model Building and Performance**

Trained and evaluated multiple models under the same cross-validation scheme:

🧪 Model	🏆 AUC	✅ Accuracy	💡 Sensitivity	🔒 Specificity
Logistic Regression	0.8413	77.4%	73.8%	80.9%
Decision Tree (rpart)	0.8053	73.8%	73.8%	73.8%
Random Forest	0.8302	76.2%	73.8%	78.6%
SVM (Radial Kernel)	0.8163	73.8%	69.1%	78.6%
K-Nearest Neighbors	0.7333	67.9%	69.2%	66.7%
Gradient Boosting (GBM)	Tuned	In Progress	In Progress	In Progress

🏅 Best Performing: Logistic Regression (balanced metrics and high AUC)

**💻 Shiny Web Application**

An intuitive, browser-based interface built with Shiny allows:

Users to input health metrics and lifestyle habits

Backend model to predict stroke risk instantly

Visual feedback on risk level for awareness and action

r
Copy
Edit
shiny::runApp("shiny_app/")
📦 Includes real-time prediction using the trained logistic model
🎯 Designed for clinics, researchers, and personal use

🚀 Running the Project
1. Clone the repository:
bash
Copy
Edit
git clone https://github.com/yourusername/Machine-Learning-for-Stroke.git
2. Install required R packages:
r
Copy
Edit
install.packages(c("caret", "Boruta", "tidyverse", "pROC", "caTools", "randomForest", "shiny"))
3. Launch the Shiny app:
r
Copy
Edit
shiny::runApp("shiny_app/")
🧑‍💻 Author
Enock Bereka
Data Scientist | ML Engineer | HealthTech Enthusiast
📅 Created: May 25, 2025
🔗 LinkedIn | GitHub

📜 License
This project is released under the MIT License.

**🧠 What This Project Demonstrates**

✅ End-to-end ML pipeline: from raw data to live app
✅ Balanced model evaluation with medical impact in mind
✅ Feature selection & interpretability (Boruta)
✅ Cross-validation for reproducibility
✅ Hands-on deployment using Shiny

**🔥 Employers Take Note:**

This project exemplifies practical machine learning applied to a real-world healthcare problem, with emphasis on:

Code readability

Clinical relevance

Scalable architecture

Deployment-ready insights

I’m actively looking for roles in Data Science, HealthTech, or AI-Powered Product Development. Feel free to connect or collaborate!
