Telco Customer Churn Intelligence
End-to-End Data Analytics & Visualization Project

 Built with Python, Machine Learning, and Power BI
🔬 Jupyter Notebook Code Breakdown (Step-by-Step)
1. Data Loading and Initial Exploration

import pandas as pd
df = pd.read_csv('Telco-Customer-Churn.csv')
df.head()

    Loaded the original dataset.

    Performed basic inspection to understand columns, nulls, and types.

2. Data Cleaning & Preprocessing

Key Steps:

    Converted TotalCharges to numeric.

    Removed rows with missing values.

    Converted SeniorCitizen (0/1) to categorical (Yes/No).

    Dropped customerID to prevent leakage and index issues.

    One-hot encoded categorical features.

    Scaled numerical features using StandardScaler.

3. EDA (Exploratory Data Analysis)

Used libraries like matplotlib, seaborn, and plotly to uncover patterns:

    Churn Rate Distribution

    Churn by Contract Type

    Churn by Monthly Charges

    Tenure Grouping and Churn

    Correlation Heatmap

These visualizations gave a bird’s eye view of patterns contributing to churn.
4. Feature Engineering

    Created a Tenure Group column using bins.

    Identified and retained top 10 most important features using XGBoost feature importance.

5. Model Building

We tested multiple models:

    Logistic Regression

    Random Forest

    XGBoost Classifier (Best Performer)

XGBoost achieved:

    Accuracy: ~77%

    Precision/Recall/F1-score: Showed balanced performance

    Confusion Matrix: Displayed how well it differentiated churners from non-churners.

6. Model Evaluation

    Used classification_report and confusion_matrix for evaluation.

    Visualized predictions using ROC curves and feature importance bar plots.

    Explained business impact: which features contribute most to churn.

7. Saved Final Data for Power BI

Added a new column CustomerID from 1 to total rows using:

df['CustomerID'] = range(1, len(df) + 1)
df.to_csv('cleaned_telco_data.csv', index=False)

