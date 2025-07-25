# DataScience-Project
This repository contains a complete pipeline for collecting, cleaning, engineering features, and modeling real estate property sales data in Oman. It includes all steps from web scraping to building a machine learning model capable of predicting property prices.
# 🏡 Oman Property Sales Price Prediction

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Requirements](#requirements)
- [Setup Instructions](#setup-instructions)
- [Data Scraping](#data-scraping)
- [Data Cleaning & Integration](#data-cleaning--integration)
- [Feature Engineering](#feature-engineering)
- [Predictive Modeling](#predictive-modeling)
- [Visualization](#visualization)

---

## 📌 Project Overview

This repository presents a full pipeline for collecting, cleaning, engineering features, and building machine learning models to **predict real estate sale prices in Oman**. Data was collected from two major property listing platforms: **OpenSooq** and **Bayut**. The workflow covers scraping, preprocessing, feature transformation, and training several baseline models to evaluate predictive performance.

---

## ⚙️ Requirements

- Python 3.8+
- Jupyter Notebook or JupyterLab


🌐 Data Scraping
Notebooks:

Bayut Oman Scraping.ipynb

OpenSooq scraping.ipynb

Description:

Scrapes real estate listings from Bayut and OpenSooq using requests + BeautifulSoup.

Extracts relevant property information like price, location, area, number of rooms, and listing type.

Output CSVs:

opensooq_properties.csv

bayut_detailed.csv

🧹 Data Cleaning & Integration
Notebook:

Data Cleaning and Preproccessing DS project.ipynb

Steps:

Renamed columns for consistency (e.g. area → size)

Cleaned formatting (e.g. removing currency symbols, handling nulls)

Converted string-based numbers into numeric types

Dropped duplicates

Merged both datasets into a unified file

Output:

combined_cleaned_properties.csv

🏗 Feature Engineering
Notebook:

Data Cleaning and Preproccessing DS project.ipynb

Derived Features:

price_per_sqm: price / size

price_per_room: price / number of rooms

city: extracted from location text

Encoded categorical variables like city, listing_type using label encoding and one-hot encoding

Removed outliers using quantile-based filtering

Scaling Techniques:

MinMaxScaler and StandardScaler applied to numeric columns.

🤖 Predictive Modeling
Notebook:

Data Cleaning and Preproccessing DS project.ipynb

Objective: Predict property sale price using engineered features

Features Used:

size, room_number, city_encoded, listing_type_encoded, etc.

Models Evaluated:

Linear Regression

Decision Tree Regressor

Random Forest Regressor

Gradient Boosting Regressor

Metrics:

R² Score

MAE (Mean Absolute Error)

Results (after leakage fix):

Linear Regression R²: 0.95 (potential leakage)

Random Forest R²: ~0.73

Gradient Boosting R²: ~0.54

Decision Tree R²: ~0.53


📁 Files in This Repository
File	Description
opensooq_properties.csv	Raw scraped data from OpenSooq
bayut_detailed.csv	Raw scraped data from Bayut
combined_cleaned_properties.csv	Final merged and cleaned dataset
Bayut Oman Scraping.ipynb	Web scraping Bayut Oman listings
OpenSooq scraping.ipynb	Web scraping OpenSooq listings
Data Cleaning and Preproccessing DS project.ipynb	Data cleaning, feature engineering, modeling
README.md	Project overview and documentation
