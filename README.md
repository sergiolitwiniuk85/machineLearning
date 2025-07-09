# SVM Classification with Bagging and Stacking

## Project Overview
This project focuses on developing a machine learning model to predict the optimal color (white or black) for repainting used cars based on various vehicle characteristics. The solution implements Support Vector Machines (SVM) with ensemble techniques like bagging and stacking to improve predictive performance.

## Problem Statement
A company specializing in used car sales needs to determine the optimal repaint color for vehicles arriving in poor condition. After evaluation, they've narrowed down options to white or black. The model must predict whether a car should be painted white based on features like price, manufacturer, production year, mileage, and other technical specifications.

## Dataset
The dataset `datos_tarea25.xlsx` contains 15 features and initially had 4340 records (reduced to 2806 after deduplication). Key features include:

- **Price**: Vehicle selling price
- **Levy**: Taxes payable
- **Manufacturer**: Car maker (e.g., Hyundai, Toyota)
- **Prod. year**: Manufacturing year
- **Category**: Vehicle type (Jeep, Sedan, etc.)
- **Engine volume**: Engine size (with turbo indicator)
- **Mileage**: Distance traveled
- **Color**: Target variable (White/Black)

## Key Steps

### 1. Data Preprocessing
- Removed 1534 duplicate records
- Handled missing values in "Levy" feature
- Converted "Engine volume" to numeric and extracted "Turbo" indicator
- Transformed "Mileage" to integer values
- Addressed outliers in Price and Mileage features
- Created binary target: 1 for White, 0 for Black

### 2. Feature Engineering
- Engineered "Vehicle age" from production year
- Created combined "Manufacturer-Category" feature
- Applied log transformation to Price and Mileage
- Implemented Robust Scaling for numerical features
- Encoded categorical variables using OneHotEncoding

### 3. Model Implementation
- **Base Model**: SVM with RBF kernel
- **Bagging**: Ensemble of SVM models with random subsets
- **Stacking**: Combined SVM, Random Forest, and Logistic Regression
- Hyperparameter tuning using GridSearchCV

## Results
The stacked ensemble model achieved the best performance:
- Accuracy: 89.3%
- F1-score: 0.91
- AUC: 0.94

## How to Use
1. Install required packages: `pip install pandas numpy scikit-learn matplotlib seaborn openpyxl`
2. Run the Jupyter notebook `svm_clasification_bagging_stacking.ipynb`
3. The notebook will:
   - Load and preprocess the data
   - Perform feature engineering
   - Train and evaluate models
   - Generate performance metrics and visualizations

## Key Findings
- Vehicle age and manufacturer are most significant predictors
- Bagging and stacking improved SVM accuracy by 7-9%
- Mileage and price transformations were crucial for handling skewness
- Turbo-equipped vehicles showed different color preference patterns

## Dependencies
- Python 3.7+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- openpyxl
