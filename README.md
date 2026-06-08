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
