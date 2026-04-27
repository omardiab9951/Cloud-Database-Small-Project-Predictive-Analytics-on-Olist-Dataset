# 📦 Predictive Analytics with PySpark: Olist E-Commerce Project

This project demonstrates a cloud-based data pipeline and predictive modeling workflow using **Apache Spark (PySpark)**. It fulfills the requirements for the **Cloud Database** course by showcasing the transition from raw data ingestion to machine learning insights.

## 🚀 Project Overview
The goal of this project is to predict if a product is **"Heavy" (>3kg)** based on its physical dimensions (length, height, and width). This simulates a real-world logistics scenario where automated categorization helps optimize shipping and warehouse storage.

## 🛠️ Key Cloud DB Concepts Applied
* **In-Memory Processing:** Utilized PySpark DataFrames for faster execution compared to traditional disk-based MapReduce.
* **ETL Pipeline:** * **Extraction:** Data ingestion from a cloud directory using `spark.read`.
    * **Transformation:** Data cleaning (handling nulls) and feature engineering using `withColumn`.
    * **Loading:** Formatting data into a `VectorAssembler` for AI readiness.
* **Lazy Evaluation:** Implementation of transformations that build a **Directed Acyclic Graph (DAG)**, which is only executed when an **Action** (like `show` or `fit`) is called.

## 📊 Technical Workflow
1. **Session Setup:** Initialized `SparkSession` for distributed computing.
2. **Data Cleaning:** Selected physical attributes and removed incomplete (null) records.
3. **Feature Engineering:** Used `cast("integer")` to create numeric labels (0 for Light, 1 for Heavy).
4. **Vectorization:** Combined multiple features into a single vector column for the Spark ML engine.
5. **Modeling:** Trained a **Logistic Regression** model using a 70/30 train-test split to predict product categories.

## 📈 Results
The model successfully predicts product categories based on dimensions. By analyzing the **Probability** and **Prediction** outputs, the project demonstrates how a structured cloud data lake can feed directly into predictive AI engineering.

---
**Developed by:** Omar Diab  
**Environment:** Kaggle / Apache Spark
