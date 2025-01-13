# Gym Churn Prediction Project

## Overview
This project is focused on predicting gym membership churn using the Gym Churn dataset. The goal is to predict whether a gym member will churn (leave) based on their demographic information and gym usage patterns. Various machine learning models were used to address this binary classification problem, including Linear Regression, Logistic Regression, Random Forest, and Neural Networks. Additionally, Exploratory Data Analysis (EDA) and data preprocessing techniques were applied to understand the data and improve model performance. Principal Component Analysis (PCA) was also explored but had limited usefulness due to the small dataset size and feature set.

## Dataset Overview
The dataset contains the following key features:

### Continuous Variables:
- **Age**
- **Avg_additional_charges_total**
- **Month_to_end_contract**
- **Lifetime**
- **Avg_class_frequency_total**
- **Avg_class_frequency_current_month**

### Non-Continuous Variables:
- **Near_Location**
- **Partner**
- **Promo_friends**
- **Group_visits**
- **Contract_period**

## Problem Addressed
The main objective is to predict whether a gym member will churn. This is a binary classification problem where the outcome is `1` (churn) or `0` (no churn). We aim to identify the key predictors of churn and use this information to create customer retention strategies.

## Methodology

### Data Preprocessing
The data was preprocessed before training the models:
1. **Missing Data Imputation**: Any missing values were filled using imputation.
2. **Encoding Categorical Variables**: Categorical variables were encoded using OneHotEncoder.
3. **Feature Scaling**: Continuous features were standardized using StandardScaler.

### Model Selection and Training
We evaluated several machine learning models for predicting churn:
- **Linear Regression**: Poor performance due to the nature of the problem being a classification task.
- **Logistic Regression**: Improved performance but only achieved 80% accuracy.
- **Random Forest**: Performed well with 91% accuracy.
- **Neural Network**: Performed best with 94% accuracy, significantly outperforming the other models.

### Neural Network Implementation
We used a Neural Network as our final model due to its superior performance. The architecture of the Neural Network included:
1. **Hidden Layers**: Three hidden layers with 128, 64, and 32 neurons, using the ReLU activation function.
2. **Batch Normalization**: Applied after each hidden layer to stabilize activations.
3. **Dropout**: A dropout rate of 0.2 was used to prevent overfitting.
4. **Class Weights**: Computed to handle class imbalance in the churn labels.
5. **Early Stopping**: The training process was stopped early once the validation loss failed to improve for 10 consecutive epochs.

The model was trained for up to 100 epochs, but early stopping halted the training at 38 epochs. This model achieved a **94% validation accuracy**.

### Evaluation Metrics
- **Accuracy**: The primary evaluation metric for the models.
- **Logistic Regression Accuracy**: 80%
- **Random Forest Accuracy**: 91%
- **Neural Network Accuracy**: 94%

The limitations of the Neural Network include:
- Difficulty in interpretation.
- Variability in performance due to the stochastic nature of training.
- Computationally intensive for large datasets.
- Requires preprocessing like normalization and scaling.

## Results
The **Neural Network** consistently outperformed all other models, achieving the highest accuracy (94%). Logistic Regression and Random Forest were also strong models, but they did not match the performance of the Neural Network.

## How to Use the Code

### Steps to Reproduce the Analysis:
1. **Load the dataset**:
   - Download the Gym Churn dataset and load it into the environment from the file path.
   
2. **Run the EDA**:
   - Perform Exploratory Data Analysis (EDA) to understand the distribution and relationships between key features. Visualizations such as bar charts and boxplots are included in this section.
   
3. **Pre-process the data**:
   - Clean the data by handling missing values.
   - Apply OneHotEncoding to categorical variables.
   - Standardize numerical features using StandardScaler.
   
4. **Run and evaluate the models**:
   - Train and evaluate the following models:
     - Logistic Regression
     - Random Forest
     - Neural Network
   - Use accuracy as the evaluation metric and visualize the results.

### Requirements:
- Python 3.x
- Required libraries:
  - Pandas
  - Numpy
  - Matplotlib
  - Seaborn
  - Scikit-learn
  - TensorFlow (for Neural Network)
  

## Conclusion
This project demonstrates how various machine learning models can be applied to predict gym churn. The **Neural Network** model outperforms other models and can be used as the most reliable approach for predicting churn in this scenario. This analysis helps gyms identify key factors influencing churn and take actions to improve customer retention.


