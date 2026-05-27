# AI-Powered Business Analyzer

## Overview

This project is an end-to-end AI + data analytics pipeline built on a large retail transaction dataset and a global cities dataset. The goal is to:

* Clean and process raw business transaction data
* Engineer meaningful business and seasonal features
* Enrich sales data with geographic and population information
* Perform exploratory business analytics (EDA)
* Prepare structured time-series data for deep learning demand forecasting
* Build an AI-based business intelligence workflow for future prediction and market analysis

The notebook is written as a full learning-style pipeline with detailed explanations for each step.

---

# What the Project Does

The system takes raw retail sales transactions and converts them into a structured machine learning dataset.

It performs:

1. Dataset download and loading
2. Data cleaning and validation
3. Revenue computation
4. Cancellation and bad-row filtering
5. Outlier removal
6. Country normalization and geographic enrichment
7. Feature engineering for seasonality and business intelligence
8. Product category generation using keyword-based NLP rules
9. Exploratory data analysis and business visualization
10. Time-series preparation for LSTM forecasting
11. AI-ready dataset creation

The final result is a cleaned and enriched business dataset that can be used for:

* Demand forecasting
* Seasonal trend prediction
* Market viability scoring
* Geographic business analysis
* Revenue analytics
* Product trend analysis

---

# Datasets Used

## 1. Online Retail Dataset

Used for:

* Transaction history
* Product sales
* Revenue analysis
* Time-series forecasting
* Product demand patterns

Contains:

* Invoice data
* Product descriptions
* Quantity sold
* Price
* Customer IDs
* Country
* Timestamps

## 2. Global Cities Dataset

Used for:

* Geographic enrichment
* Population analysis
* Market-size estimation
* Country-level business intelligence
* Latitude/longitude mapping

Contains:

* City names
* Country names
* Population
* Latitude/Longitude

---

# Technologies and Libraries Used

## Data Processing

### `pandas`

Used for:

* DataFrames
* Cleaning datasets
* Filtering rows
* Grouping and aggregation
* Time-series manipulation
* Feature engineering
* Merging datasets

### `numpy`

Used for:

* Numerical operations
* Vectorized calculations
* Statistical operations
* Array manipulation

---

## Data Visualization

### `matplotlib`

Used for:

* Revenue trend charts
* Monthly seasonality analysis
* Product performance graphs
* Country revenue visualizations
* Day-of-week sales analysis

### `plotly`

Used for:

* Interactive business dashboards
* Advanced visualizations
* Geographic visualization support

---

## Machine Learning & AI

### `torch` (PyTorch)

Used for:

* Deep learning model creation
* LSTM demand forecasting
* Neural network training
* Time-series prediction
* Dataset batching and training loops

Key modules used:

* `torch.nn`
* `torch.optim`
* `torch.utils.data`

### `scikit-learn`

Used for:

* Feature scaling
* Dataset splitting
* Evaluation metrics
* Preprocessing utilities

Modules used:

* `sklearn.preprocessing`
* `sklearn.model_selection`
* `sklearn.metrics`
* `sklearn.ensemble`

---

## Dataset Access

### `kagglehub`

Used for:

* Downloading Kaggle datasets directly into the notebook
* Managing cached dataset downloads

---

## Utility Libraries

### `os`

Used for:

* File paths
* Folder creation
* Output management

### `glob`

Used for:

* Finding CSV files dynamically

### `re`

Used for:

* Regex-based product categorization
* Keyword extraction
* Text pattern matching

### `pickle`

Used for:

* Saving preprocessing objects and models

### `warnings`

Used for:

* Suppressing unnecessary warning outputs

---

# Pipeline Structure

## Step 1 — Data Loading & Inspection

Purpose:

* Download datasets
* Load CSV files
* Inspect shapes, columns, nulls, and datatypes
* Validate join compatibility between datasets

Main outputs:

* Raw retail dataset
* Raw city dataset
* Dataset summaries

---

## Step 2 — Data Cleaning

Purpose:

* Convert dates to datetime
* Rename problematic columns
* Compute revenue
* Remove cancellations
* Remove invalid quantities/prices
* Handle missing values
* Remove statistical outliers
* Normalize country names
* Merge geographic information

Important cleaning rules:

* Remove invoices beginning with `C`
* Remove rows with negative quantities/prices
* Drop rows with missing descriptions
* Fill missing customer IDs with placeholders
* Use IQR-based outlier filtering

Final output:

* Cleaned merged parquet dataset

---

## Step 3 — Feature Engineering

Purpose:

Generate machine learning features from transactional data.

Features created:

### Time Features

* Month
* Year
* Quarter
* Day of week
* Weekend flags
* Cyclical sine/cosine features

### Business Features

* Revenue per country
* Revenue per capita
* Total country revenue
* Daily sales aggregates

### Product Categorization

Products are categorized using regex-based keyword rules.

Example categories:

* Seasonal
* Lighting
* Kitchen
* Home decor
* Toys
* Gifts
* Storage
* Furniture

---

## Step 4 — Exploratory Data Analysis (EDA)

Purpose:

Visualize and understand business patterns before modelling.

Charts include:

* Monthly revenue trends
* Seasonal patterns
* Country revenue rankings
* Product revenue leaders
* Day-of-week sales behavior
* Category distribution

Business insights extracted:

* Christmas seasonality spikes
* Strongest sales months
* Highest revenue countries
* Most valuable product categories

---

## Step 5 — Deep Learning Forecasting

Purpose:

Prepare time-series sequences for AI forecasting.

Implemented components:

* Sequence generation
* Custom PyTorch datasets
* LSTM neural networks
* Training loops
* Evaluation functions
* Forecast scoring

The model is designed to learn:

* Seasonal demand patterns
* Product sales trends
* Time-based revenue behavior

---

# File Formats Used

## CSV

Used for:

* Raw dataset storage

## Parquet

Used for:

* Cleaned datasets
* Feature-engineered datasets
* Faster loading
* Reduced storage usage
* Preserving datatypes

Parquet is preferred because:

* Smaller file size
* Faster read/write speed
* Better ML pipeline compatibility

---

# Outputs Generated

The notebook creates:

* Cleaned datasets
* Feature-engineered datasets
* Daily sales datasets
* Revenue summaries
* Visual charts
* Forecast-ready time-series data
* Business insight summaries

---

# Key AI Concepts Used

## Time-Series Forecasting

Predicting future sales using historical trends.

## LSTM Networks

A recurrent neural network architecture designed for sequential data and long-term temporal dependencies.

## Feature Engineering

Transforming raw data into machine-learning-friendly features.

## Seasonality Modelling

Capturing repeating business patterns such as holiday sales spikes.

## Geographic Enrichment

Combining external location/population data with transaction data.

---

# How to Run the Project

## Requirements

Install dependencies:

```bash
pip install kagglehub torch torchvision google-generativeai plotly pandas numpy matplotlib scikit-learn
```

## Run the Notebook

Open:

```bash
AI_BUISNESS.ipynb
```

Run cells sequentially from top to bottom.

---

# Project Workflow Summary

```text
Raw Retail Data
        ↓
Data Cleaning
        ↓
Revenue Engineering
        ↓
Country & Geo Enrichment
        ↓
Feature Engineering
        ↓
Product Categorization
        ↓
EDA & Business Insights
        ↓
Daily Time-Series Creation
        ↓
LSTM Forecasting Pipeline
        ↓
AI-Powered Business Analysis
```

---

# Possible Future Improvements

* Real-time dashboard deployment
* Streamlit web application
* Transformer-based forecasting models
* Automated category generation using NLP
* Recommendation systems
* Customer segmentation
* Inventory optimization
* Market expansion prediction
* Multi-step forecasting
* Hyperparameter tuning
* API deployment
* GPU training optimization

---

# Project Purpose

This project demonstrates a complete real-world AI business analytics workflow combining:

* Data engineering
* Data cleaning
* Statistical analysis
* Visualization
* Geographic enrichment
* Machine learning
* Deep learning
* Time-series forecasting

It is designed as both:

1. A learning project for understanding AI pipelines
2. A scalable foundation for real business intelligence systems
