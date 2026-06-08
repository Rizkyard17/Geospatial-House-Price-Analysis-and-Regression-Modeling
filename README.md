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

Dataset Source:
- Kaggle Pakistan House Price Dataset https://www.kaggle.com/datasets/sarcasmos/pakistan-house-prices-and-property-listings
  
The dataset contains 168,446 real estate property listings across multiple cities in Pakistan.

## Dataset Features

| Feature | Data Type | Description |
|----------|-----------|-------------|
| property_id | Integer | Unique identifier for each property listing |
| location_id | Integer | Unique identifier for the location |
| page_url | String | URL of the original property listing |
| property_type | String | Property category (House, Flat, Plot, etc.) |
| price | Integer | Property price in PKR (Target Variable) |
| location | String | Neighborhood or locality name |
| city | String | City where the property is located |
| province_name | String | Province of the property location |
| latitude | Float | Geographic latitude coordinate |
| longitude | Float | Geographic longitude coordinate |
| baths | Integer | Number of bathrooms |
| area | String | Property area measurement |
| purpose | String | Listing purpose (Sale or Rent) |
| bedrooms | Integer | Number of bedrooms |
| date_added | String | Date when the listing was added |
| agency | String | Real estate agency name |
| agent | String | Real estate agent name |

## Potential Predictive Features

The following variables were considered as potential predictors:

- bedrooms
- baths
- latitude
- longitude
- area_sqft
- purpose
- city
- property_type
  
## Target Variable

The prediction target is:

- **price** → Property price in Pakistani Rupees (PKR)
---

# Project Workflow

## 1. Business Understanding

The project aims to answer:
- What factors most influence property prices in Pakistan?
- Can a Linear Regression model predict property prices?
- How much do location and size of a property affect price?
- Do characteristics such as the number of bedrooms, bathrooms, and property type significantly influence price?
- How can the information from the predictions be used to inform decision-making in the property sector?

---

## 2. Data Understanding

At this stage, an understanding of the Pakistan property dataset is carried out to determine the data structure, data quality, and characteristics of each available variable.

The following activities were performed:

- Inspected the data structure and verified the data type of each variable.
- Identified and adjusted inappropriate data types where necessary.
- Checked for missing values across all features.
- Checked for duplicate records.
- Analyzed the distribution of categorical variables, including:
  - Property types
  - Cities
  - Provinces
  - Listing purposes (Sale or Rent)
- Identified the most common property price ranges in the dataset.
- Reviewed descriptive statistics to gain an initial understanding of the data.

Key insights obtained during this stage were used to guide the preprocessing and feature engineering processes.

---

## 3. Exploratory Data Analysis (EDA)

The exploratory data analysis was conducted to understand market patterns, property characteristics, and the relationships between variables that may influence property prices.

### 1. Sale vs Rent Analysis

This analysis explores the distribution of properties listed for sale and rent across different regions.

Visualizations:

- Overall distribution of Sale vs Rent listings.
- Number of Sale and Rent properties by province.
- Number of Sale and Rent properties by city.
- Percentage distribution of Sale and Rent properties by city.

Key Findings:

- The dataset is dominated by properties listed for sale, indicating a stronger representation of the sales market compared to the rental market.
- Punjab and Sindh contain a higher proportion of properties for sale, while Islamabad has a relatively larger share of rental properties.
- The distribution of Sale and Rent listings varies across cities, suggesting that location influences market behavior.
- These findings indicate that location-related features such as city and province may contribute to property price differences.

### 2. Property Type Analysis

This analysis examines the distribution of different property categories across regions.

Visualizations:

- Property type distribution by province.
- Property type distribution by city.

Key Findings:

- Houses and Flats are the most common property types across the dataset.
- The distribution of property types varies between cities and provinces.
- Certain cities show a higher concentration of specific property categories, indicating regional preferences.
- Property type is expected to be an important predictor of property prices.

### 3. Price Analysis

This analysis investigates price variations across locations and listing purposes.

Visualizations:

- Average property price comparison between Sale and Rent listings.
- Average property price by province.
- Average property price by city.
- Average property price by city and purpose.

Key Findings:

- Properties listed for sale have significantly higher average prices than rental properties.
- Islamabad Capital shows the highest average property prices, followed by Sindh and Punjab.
- At the city level, Lahore and Karachi exhibit higher average property prices than Rawalpindi and Faisalabad.
- Price differences across provinces and cities suggest that location plays a major role in determining property value.
- The purpose of the listing (Sale or Rent) is also strongly associated with price variations.

### 4. Correlation and Relationship Analysis

This analysis evaluates the relationships between property features and price.

Activities:

- Outlier detection and treatment using Winsorization.
- Correlation analysis before and after outlier treatment.
- Scatter plot analysis between price and:
  - Area (sqft)
  - Bedrooms
  - Bathrooms
  - Latitude
  - Longitude

Key Findings:

- Outliers significantly weakened the observed relationships between features and property prices.
- After outlier treatment, the correlation between area and price increased substantially, indicating that property size is one of the strongest predictors of price.
- Bedrooms and bathrooms showed moderate positive relationships with property prices.
- Latitude and longitude exhibited weak linear correlations with price, suggesting that location effects may be better captured through city and province features.
- Property area emerged as the most influential numerical feature in explaining price variations.


### Overall EDA Insight
The exploratory analysis revealed that property prices in Pakistan are influenced by multiple factors, including:

- Property size (area)
- Number of bedrooms
- Number of bathrooms
- Property type
- Listing purpose (Sale or Rent)
- Geographic location (city and province)

Among the numerical variables, property area showed the strongest relationship with price after outlier treatment. These findings guided the feature selection and preprocessing steps used in the Linear Regression model.

---

# Data Preprocessing

The dataset was prepared for machine learning by performing several preprocessing steps to ensure data quality and compatibility with the Linear Regression algorithm.

## Data Preparation
- Reintroduced categorical variables (purpose, city, and property_type) into the dataset after outlier removal to preserve important location and property characteristics.
- Verified that no missing values remained in the final modeling dataset.
- Ensured all features were ready for feature engineering and model training.

## Feature Engineering
Several transformations were applied to convert the data into a machine-learning-ready format:

Applied One-Hot Encoding to categorical variables:
- purpose
- city
- property_type
  
Defined:
- Target variable (y): price
- Feature variables (X): property characteristics and encoded categorical features.

Implemented a custom Standard Scaler from scratch to standardize feature values before Gradient Descent optimization.

## Train-Test Split
The dataset was divided into:
- 80% Training Data
- 20% Testing Data
This split allows the model to learn from historical data while being evaluated on unseen observations.

---

# Linear Regression From Scratch
A Linear Regression model was implemented manually using NumPy without relying on machine learning libraries for the training process.

## Model Components
- Weight initialization
- Bias initialization
- Mean Squared Error (MSE) loss function
- Gradient computation
- Gradient Descent optimization
- Iterative parameter updates

## Training Configuration
- Optimization Algorithm: Gradient Descent
- Number of Epochs: 1,000
- Loss Function: Mean Squared Error (MSE)

## Training Result
The training process showed a consistent reduction in loss:

| Epoch | MSE Loss | 
|----------|-----------|
| 1 | 277.26 Trillion |
| 100 | 31.29 Trillion | 
| 500 | 30.70 Trillion | 
| 1000 | 30.66 Trillion | 

Final model parameters:

- Bias (Intercept): 17,588,084.74
- Number of learned coefficients: 14

The decreasing loss demonstrates that the Gradient Descent implementation successfully converged during training.

---

# Model Evaluation
The model was evaluated using the testing dataset with three common regression metrics.

Evaluation metrics:
| Metric | Result | 
|----------|-----------|
| MAE | PKR 5,459,268.83 |
| RMSE | PKR 7,860,393.14 | 
| R2 Score | 0.7450 |

## Interpretation
- The model explains approximately 74.5% of the variance in property prices.
- On average, predictions differ from actual prices by approximately PKR 5.46 million.
- The results indicate that the model captures the main factors influencing property prices while maintaining reasonable prediction accuracy.

---

# Residual Anlysis
Residual analysis was conducted to evaluate prediction errors and verify the assumptions of Linear Regression.

## Visualizations
- Residual vs Predicted Plot
- Residual Distribution Histogram

## Key Findings
- Residuals are generally centered around zero, indicating that the model does not exhibit strong systematic bias.
- The residual distribution shows that most prediction errors are concentrated near zero.
- Some large residual values remain, suggesting that a small number of properties are still difficult to predict accurately.

Overall, the residual analysis indicates that the model performs reasonably well and does not suffer from major prediction bias.

---

# Feature Importance
Feature importance was interpreted using the learned regression coefficients.

## Top Influential Features
| Feature | Coefficient | 
|----------|-----------|
| area_sqft | 12.46M |
| purpose_For Sale | 10.65M | 
| city_Karachi | 2.15M |

Key Findings
- Property area is the strongest predictor of house prices.
- Properties listed for sale tend to have significantly higher values than rental properties.
- Location has a substantial impact on property prices, particularly properties located in Karachi and Islamabad.
- Houses generally command higher prices compared to other property types.
- Bedrooms contribute positively to property value.

These findings align with the insights obtained during the exploratory data analysis.

---
# Comparison With Scikit-Learn
To validate the correctness of the custom implementation, the model was compared with Scikit-Learn's Linear Regression.

## Performance Comparison
| Feature | Scratch | Scikit-Learn | 
|----------|-----------|-----------|
| R2 Score | 74.50% | 74.54% |
| MAE | PKR 5,459,268.83 | PKR 5,455,669.13 | 
| Bias | 17,588,084.74 | 17,587,660.11 |

---

# Conclusion

The custom implementation achieved nearly identical performance to Scikit-Learn's implementation.

This demonstrates that:
- The Gradient Descent algorithm was implemented correctly.
- The coefficient estimates closely match those produced by a production-grade machine learning library.
- The Linear Regression model successfully learned the underlying relationships within the dataset.

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
house-price-prediction-pakistan/ │ ├── README.md │ ├── notebooks/ │ └── house_price_prediction.ipynb │ └── images/

---

# Author

M. Rizky Ardiansyah Putra

---

# Contact

```
