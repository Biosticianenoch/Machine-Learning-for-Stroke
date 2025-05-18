**Machine-Learning-for-Stroke**

This repository contains various machine learning models trained on a stroke dataset using Caret in R. The repository also contains an interactive screening to developed by shiny to assess individuals who are at risk of developing stroke

**Study Objective**

This study aimed to develop a high-performing machine learning model trained on a stroke dataset and deploy it within an interactive Shiny web application. The integrated system is designed for practical use in real-world healthcare settings to facilitate stroke risk assessment, support early diagnosis, and promote personalized treatment strategies.

**Data Importation and Inspection**

The dataset was imported into R in CSV format. A thorough exploratory data analysis (EDA) was conducted to understand the structure of the data, identify and handle any missing values, detect duplicate records, and examine the distribution of the target variable (stroke occurrence). These steps ensured data quality and suitability for building an accurate machine learning model.

**Data Preprocessing**

The dataset was preprocessed to ensure all variables were in the appropriate data formats. Categorical variables were transformed using label encoding to convert them into numerical values suitable for machine learning algorithms. During the cleaning process, an unexpected or unknown character was detected in the BMI column and was subsequently removed to maintain data integrity. Additionally, the 'id' column, which held no predictive value, was dropped as it was irrelevant to the machine learning implementation. To address class imbalance in the target variable, the majority class was downsampled, thereby improving the model’s ability to learn from the minority class and enhancing predictive performance.
