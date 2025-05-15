# Machine Learning Module – CompareIt (Magasin Dashboard)

This document details the machine learning models developed for the **Magasin Dashboard** in the CompareIt Business Intelligence platform. These models enhance user experience and enable smarter purchasing decisions through intelligent recommendations, price predictions, and user segmentation.

---

## 🎯 Objectives

The ML module aims to support:
- **Product recommendation** based on user preferences.
- **Personalized filtering** by user-defined budgets.
- **Price forecasting** to help users choose the best time to buy.
- **Customer segmentation** (optional) for targeting and analysis.

---

## 🧠 Models Implemented

### 1. Product Recommendation System
- **Algorithm**: TF-IDF Vectorization + Cosine Similarity  
- **Purpose**: Recommends products similar to a given item.  
- **Input**: Product name or description.  
- **Output**: Top N most similar products.  
- **Key Features Used**: Name, category, brand, and tags.

### 2. Budget-Based Filtering
- **Layer on top of recommendation model**  
- Filters out products above the user-defined budget.  
- Ensures practical, cost-sensitive suggestions.

### 3. Price Prediction Model
- **Algorithm**: Regression (Linear Regression, Random Forest Regressor tested)  
- **Purpose**: Predicts future prices of a product based on historical data.  
- **Input**: Product features (category, vendor, historical prices).  
- **Output**: Predicted future price.  
- **Use Case**: Helps users time their purchases.

### 4. Customer Segmentation (Optional)
- **Algorithm**: Random Forest Classifier  
- **Purpose**: Classifies users into segments based on shopping behavior.  
- **Input**: Features like average spend, frequency, product categories browsed.  
- **Output**: User segment label (e.g., Budget Shopper, Premium Seeker).  
- **Status**: Optional enhancement, not integrated in current release.

---

## 🧪 Training & Evaluation

- **Tools**: Python (scikit-learn, pandas, numpy)  
- **Data Split**: 80% training, 20% testing  
- **Metrics**:
  - Recommendation: Cosine similarity score
  - Prediction: MAE, RMSE
  - Classification: Accuracy, Precision, Recall

---

## 🗃️ Data Sources

- Extracted from APIs and CSV files for product listings.
- Stored and cleaned through the ETL pipeline.
- Loaded into the SQL Server data warehouse.

---

## 🔌 Integration

- All models are exposed via a **Flask REST API**.
- Endpoints:
  - `/recommend`: Get product recommendations
  - `/predict_price`: Forecast product price
  - `/segment_user`: Classify user segment (optional)
- Tested using Postman.
- Integrated with Angular web interface and Power BI store dashboard.

---

## 🚀 Future Enhancements

- **LSTM/GRU** models for time-series price forecasting.
- **Autoencoders** for anomaly detection (suspicious price changes).
- **Reinforcement Learning** for dynamic pricing strategies.
- **Multilingual recommendation system** for expansion.

---


