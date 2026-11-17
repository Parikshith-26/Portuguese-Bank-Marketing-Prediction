# Portuguese Bank Marketing Prediction

## Project Overview

This project focuses on analyzing bank marketing campaign data and developing Machine Learning classification models to predict whether a customer is likely to subscribe to a term deposit.

The objective is to help the bank's marketing team identify potential customers, improve customer targeting and make marketing campaigns more effective.

**Domain:** Banking and Finance  
**Project Type:** Binary Classification

## Dataset Description

The project uses the **Portuguese Bank Marketing Dataset**, which contains information about direct phone-call marketing campaigns conducted by a Portuguese banking institution between May 2008 and November 2010.

**Dataset File:** `bank-additional-full.csv`

**Dataset Details:**
- Original records: 41,188
- Records after duplicate removal: 41,176
- Total columns: 21
- Input features: 20
- Target variable: `y`

The target variable `y` indicates whether a customer subscribed to a term deposit (`yes` or `no`).

### Feature Categories

1. **Customer Demographics:** Age, job, marital status and education.
2. **Financial Information:** Credit default, housing loan and personal loan.
3. **Campaign Information:** Contact method, month, day of week, campaign contacts, previous contacts and previous campaign outcome.
4. **Economic Indicators:** Employment variation rate, consumer price index, consumer confidence index, Euribor 3-month rate and number of employees.

## Project Workflow

### 1. Data Loading and Understanding
- Loaded the dataset using Pandas.
- Examined dataset dimensions, data types and statistical summaries.
- Identified duplicate records and removed 12 duplicates.

### 2. Data Cleaning
- Checked missing and unknown values.
- Retained unknown categorical values as separate categories.
- Examined the distribution of the target variable.

### 3. Exploratory Data Analysis (EDA)
Performed analysis on:
- Customer age distribution.
- Job-wise subscription patterns.
- Education and marital status.
- Contact communication methods.
- Month-wise and weekday subscription rates.
- Number of campaign contacts.
- Previous campaign outcomes.
- Economic indicators and their relationships.

### 4. Data Preprocessing
- Excluded the `duration` column to avoid data leakage because call duration is not available before contacting a customer.
- Excluded the `campaign` column from model training.
- Encoded the target variable into binary values (No = 0, Yes = 1).
- Applied One-Hot Encoding to categorical features.
- Applied StandardScaler to numerical features.
- Used class weighting to address class imbalance.
- Split the dataset into 80% training data and 20% testing data using stratified sampling.

### 5. Machine Learning Models

Three classification algorithms were implemented:

**Logistic Regression**
- Used as a baseline classification model.
- Applied balanced class weights to handle class imbalance.

**Decision Tree Classifier**
- Used a tree-based approach to classify customers.
- Applied class weighting and controlled tree depth.

**Random Forest Classifier**
- Used an ensemble of decision trees.
- Applied balanced class weights to improve minority-class prediction.

## Model Evaluation

The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

### Model Comparison Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 83.06% | 35.96% | 64.44% | 46.16% | 80.09% |
| Decision Tree | 82.39% | 34.70% | 63.79% | 44.95% | 78.95% |
| Random Forest | **86.34%** | **42.78%** | 62.93% | **50.94%** | **81.28%** |

### Best Performing Model

**Random Forest** achieved the best overall performance among the three evaluated models.

It achieved:
- Accuracy: 86.34%
- Precision: 42.78%
- Recall: 62.93%
- F1 Score: 50.94%
- ROC-AUC: 81.28%

Therefore, Random Forest was selected as the best-performing model for predicting potential term deposit subscribers.

## Business Suggestions

Based on the analysis and predictive modelling results, the following suggestions were identified:

1. Use the Random Forest model to prioritize customers who are more likely to subscribe.
2. Focus on customers with positive previous campaign outcomes.
3. Analyze communication methods to improve customer engagement.
4. Identify suitable months and weekdays for marketing campaigns.
5. Avoid excessive repeated customer contact.
6. Regularly monitor campaign performance and subscription rates.

## Technologies Used

| Category | Tools and Libraries |
|---|---|
| Programming Language | Python |
| Development Environment | Jupyter Notebook |
| Data Manipulation | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Classification Algorithms | Logistic Regression, Decision Tree, Random Forest |

## Challenges Faced

- **Class Imbalance:** Addressed using balanced class weights.
- **Unknown Values:** Retained unknown categorical values instead of unnecessarily removing records.
- **Categorical Variables:** Converted categorical features using One-Hot Encoding.
- **Different Feature Scales:** Applied StandardScaler to numerical features.
- **Data Leakage:** Excluded the duration feature because it is not available before a marketing call.
- **Model Selection:** Compared multiple classification models using evaluation metrics.

## Project Conclusion

The project successfully demonstrates how Machine Learning can be applied to bank marketing data to predict customer subscription behaviour.

Among the three evaluated models, Random Forest achieved the highest accuracy, precision, F1 Score and ROC-AUC.

The developed model can assist the bank's marketing team in identifying potential customers, prioritizing marketing efforts and improving campaign effectiveness.

## How to Run the Project


### 4. Open Jupyter Notebook

```bash
jupyter notebook
```


### 6. Run the Notebook

Open `Portuguese Bank Marketing Prediction.ipynb` and execute the cells sequentially.

---

**Project:** Portuguese Bank Marketing Prediction  
**Domain:** Banking and Finance  
**Approach:** Exploratory Data Analysis and Machine Learning Classification
