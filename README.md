
# HR Employee Attrition Prediction

## Overview
This project predicts employee attrition using machine learning models trained on HR employee data. The analysis includes exploratory data analysis, feature engineering, model training, and comparison of multiple classification approaches.

## Problem Description and Motivation

Employee attrition is a significant challenge for organizations, impacting productivity, team stability, and operational costs. High turnover rates lead to increased recruitment and training expenses, loss of institutional knowledge, and reduced team performance.

### Key Challenges
- **Retention**: Identifying which employees are at risk of leaving
- **Proactive Intervention**: Understanding factors that drive attrition
- **Resource Planning**: Predicting turnover to better manage workforce capacity

### Project Goals
This project builds a predictive model to:
1. Identify employees likely to leave the organization
2. Discover key factors contributing to attrition
3. Enable HR teams to implement targeted retention strategies
4. Compare multiple machine learning approaches for classification on imbalanced data

By leveraging historical employee data, we can help organizations make data-driven decisions to improve retention and workplace satisfaction.

## Project Structure
```
├── notebooks/
│   ├── 01_exploration.ipynb      # Exploratory Data Analysis
│   ├── 02_modeling.ipynb         # Model Training and Evaluation
├── data/
│   └── WA_Fn-UseC_-HR-Employee-Attrition.csv
├── requirements.txt
└── README.md
```

## Setup Instructions

### 1. Clone or Download the Project
```bash
cd /path/to/mini-project-2
```

### 2. Create a Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Analysis

#### Exploratory Data Analysis
```bash
jupyter notebook notebooks/01_exploration.ipynb
```

#### Model Training and Evaluation
```bash
jupyter notebook notebooks/02_modeling.ipynb
```

### 5. Expected Output
- Data summaries and visualizations from EDA
- Model performance metrics and confusion matrices
- ROC curve comparisons
- Feature importance rankings

### Notes
- Ensure the data file `WA_Fn-UseC_-HR-Employee-Attrition.csv` is in the `data/` directory
- Models may take a few minutes to train, especially GridSearchCV
- Jupyter Notebook is required to run `.ipynb` files

## Data
- **Source**: WA_Fn-UseC_-HR-Employee-Attrition.csv
- **Records**: 1,470 employees
- **Target**: Attrition (Yes/No)
- **Features**: 34 employee attributes (demographics, employment details, satisfaction metrics)

## Exploratory Data Analysis (01_exploration.ipynb)
- Data loading and quality checks
- Target variable distribution
- Correlation analysis with attrition
- Feature relationships by department, job role, overtime, marital status
- Distance from home and promotion impact analysis

## Modeling (02_modeling.ipynb)

### Preprocessing
- One-hot encoding for categorical variables
- Standard scaling for numerical features
- 80-20 train-test split with stratification

### Models Evaluated
1. **Logistic Regression** (baseline, class weights, SMOTE)
2. **Random Forest** (baseline, class weights, SMOTE, GridSearchCV)
3. **Gradient Boosting**

### Imbalance Handling
- Class weights
- SMOTE (Synthetic Minority Oversampling)

### Hyperparameter Tuning
- GridSearchCV for Random Forest optimization

## Results
Best performing model: **Logistic Regression with Balanced Class Weights or SMOTE**
- Higher recall on balanced class weights for identifying at-risk employees (0.659574)
- Best overall performance (F1 score) with SMOTE (0.539326)

## Team Member Contributions
- Michael - EDA, data processing, model training, model evaluation, analysis
- Alex - EDA, model training, imbalanced data handling, hyperparameter tuning, imbalanced data handling, model evaluation