**Machine-Learning-for-Stroke**

This repository contains a collection of machine learning models developed using the caret package in R, all trained on a stroke dataset to predict the likelihood of stroke occurrence. In addition to the model training scripts, the repository includes an interactive stroke risk screening tool built with Shiny. This user-friendly web application allows individuals to input relevant health and lifestyle information to assess their risk of developing a stroke. The tool is designed to support early detection and personalized prevention strategies by leveraging the predictive capabilities of the trained machine learning models.

**Study Objective**

This study aimed to develop a high-performing machine learning model trained on a stroke dataset and deploy it within an interactive Shiny web application. The integrated system is designed for practical use in real-world healthcare settings to facilitate stroke risk assessment, support early diagnosis, and promote personalized treatment strategies.

**Data Importation and Inspection**

The dataset was imported into R in CSV format. A thorough exploratory data analysis (EDA) was conducted to understand the structure of the data, identify and handle any missing values, detect duplicate records, and examine the distribution of the target variable (stroke occurrence). These steps ensured data quality and suitability for building an accurate machine learning model.

**Data Preprocessing**

The dataset was preprocessed to ensure all variables were in the appropriate data formats. Categorical variables were transformed using label encoding to convert them into numerical values suitable for machine learning algorithms. During the cleaning process, an unexpected or unknown character was detected in the BMI column and was subsequently removed to maintain data integrity. Additionally, the 'id' column, which held no predictive value, was dropped as it was irrelevant to the machine learning implementation. To address class imbalance in the target variable, the majority class was downsampled, thereby improving the model’s ability to learn from the minority class and enhancing predictive performance.

**Feature Selection**

Feature importance analysis was conducted using the Boruta algorithm, a robust wrapper method built around the random forest classifier. This technique was employed to identify the most relevant predictors for stroke classification. The Boruta analysis confirmed that the following variables significantly contributed to the prediction task: Age, Hypertension, Heart Disease, Marital Status, Work Type, Average Glucose Level, BMI, and Smoking Status. Conversely, Gender and Residence Type were deemed unimportant, as they did not exhibit a statistically significant influence on the target variable. These insights guided the selection of features for subsequent machine learning model development.

**Splitting the data into Training and Testing sets**

The dataset was divided into training and testing subsets using the caTools package in R, with 80% of the data allocated for training and the remaining 20% reserved for testing. This split ensured that the machine learning models were trained on a majority portion of the data while preserving a separate subset for unbiased evaluation of model performance on unseen data.

**Preparing the Training Scheme**

The training scheme was prepared using the trainControl() function from the caret package in R, which is essential for setting up the resampling method and performance evaluation criteria during model training. In this case, a repeated 10-fold cross-validation approach was specified, meaning the dataset was divided into 10 equal parts, and the training process was repeated 4 times to ensure stability and robustness of the model’s performance estimates. This approach helps to reduce the variance that may result from a single split of the data and improves the reliability of the performance metrics. Additionally, the classProbs = TRUE parameter was included to enable the calculation of class probabilities, which is particularly useful for evaluating classification models using metrics that depend on probability thresholds. The summaryFunction = twoClassSummary argument was specified to compute performance metrics such as the Area Under the ROC Curve (AUC), sensitivity, and specificity, which are more informative than simple accuracy for imbalanced classification tasks. Overall, this training control configuration supports a rigorous and well-rounded evaluation of classification models.
