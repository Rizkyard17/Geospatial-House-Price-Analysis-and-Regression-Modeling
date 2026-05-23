# House Price Prediction in Pakistan using Linear Regression From Scratch

An end-to-end machine learning project focused on predicting house prices in Pakistan using a custom implementation of Linear Regression with Gradient Descent.

This project demonstrates:
- Machine Learning fundamentals
- Mathematical implementation of Linear Regression from scratch
- Data preprocessing and feature engineering
- Geospatial data analysis
- Model evaluation and interpretation
- Business insight generation

---

# Project Overview

The real estate market is influenced by multiple factors such as:
- location
- property size
- number of bedrooms
- property type
- geographic coordinates

The objective of this project is to build a predictive model capable of estimating property prices in Pakistan and identifying the factors that most significantly influence housing prices.

---

# Dataset Information

The dataset contains property listings in Pakistan with the following features:

| Feature | Description |
|---|---|
| city | City where the property is located |
| location | Specific neighborhood or locality |
| area | Property area |
| bedrooms | Number of bedrooms |
| bathrooms | Number of bathrooms |
| property_type | Type of property |
| purpose | Sale or Rent |
| price | Property price in PKR |
| latitude | Latitude coordinate |
| longitude | Longitude coordinate |

Dataset Source:
- Kaggle Pakistan House Price Dataset https://www.kaggle.com/datasets/sarcasmos/pakistan-house-prices-and-property-listings

---

# Project Workflow

## 1. Business Understanding

The project aims to answer:
- What factors influence house prices in Pakistan?
- Can Linear Regression accurately predict property prices?
- How significant are location and area in determining price?

---

## 2. Data Understanding

Performed:
- Dataset inspection
- Missing value analysis
- Duplicate checking
- Data type validation
- Statistical summaries

---

## 3. Exploratory Data Analysis (EDA)

### Distribution Analysis
- House price distribution
- Area distribution
- Bedroom and bathroom distribution

### Correlation Analysis
- Relationship between area and price
- Relationship between rooms and price

### Location Analysis
- Average price per city
- Property distribution across cities

### Geospatial Visualization
- Latitude-longitude property mapping
- Spatial clustering analysis

---

# Data Preprocessing

The preprocessing pipeline includes:

## Missing Value Handling
- Numerical features → median imputation
- Categorical features → mode imputation

## Outlier Treatment
- IQR-based detection
- Log transformation on skewed variables

## Feature Encoding
Applied One Hot Encoding for:
- city
- property_type
- purpose

## Feature Scaling
Standardization applied before Gradient Descent optimization.

---

# Feature Engineering

Additional features created:
- Total rooms
- Price per area
- Location-based aggregations

---

# Linear Regression From Scratch

The model was implemented manually using:
- NumPy
- Gradient Descent Optimization
- Mean Squared Error Loss

Implemented components:
- Weight initialization
- Cost function
- Gradient computation
- Parameter updates
- Training loop
  

# Model Evaluation

Evaluation metrics:
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)

---

# Results & Interpretation

## Key Findings


## Model Behavior


---

# Technologies Used

| Category | Tools |
|---|---|
| Programming | Python |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Custom Linear Regression |
| Evaluation | Scikit-learn Metrics |
| Deployment | Flask |

---

# Project Structure


# Visualizations

---

# Future Improvements


---

# Dashboard Features


---

# Conclusion

This project demonstrates the implementation of Linear Regression from scratch for real-world house price prediction problems.

The project highlights:
- machine learning fundamentals
- optimization techniques
- data preprocessing
- exploratory data analysis
- model interpretation
- business-oriented insights

---

# Author

M. Rizky Ardiansyah Putra

---

# Contact

```
