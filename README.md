# Predicting Delivery Delays (Olist) 🚚📦

## Overview
This project explores whether **delivery delays can be predicted before shipping** using the **Brazilian E-Commerce Public Dataset (Olist)**.  
The goal is to estimate the **probability of delay** using only **pre-dispatch features**, supporting logistics risk monitoring and proactive decision-making.

---

## Dataset
Source: **Brazilian E-Commerce Public Dataset by Olist (Kaggle)**

Main tables used:
- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_customers_dataset.csv`
- `olist_sellers_dataset.csv`

---

## Target
Binary classification:

- `delay = 1` if `order_delivered_customer_date > order_estimated_delivery_date`
- `delay = 0` otherwise

Class imbalance: ~**7.8%** delayed orders.

---

## Features (Pre-dispatch only)
- **Timing:** purchase weekday / hour / month  
- **Order characteristics:** number of items, total price, freight cost  
- **Geography:** seller/customer state and city (one-hot encoded)

---

## Models & Evaluation
Models tested:
- **Logistic Regression** (interpretable baseline)
- **Random Forest** (non-linear interactions, robust to noise)

Evaluation strategy:
- **Time-based train/test split**
- Metric: **ROC-AUC** (appropriate for imbalanced classification)
- Oversampling tested on training set using **RandomOverSampler**

---

## Key Takeaways
- Predictive signal exists, but performance is constrained by **post-dispatch factors not available at prediction time**
- Models are most useful for **risk ranking** rather than perfect delay prediction
- Demonstrates real-world limitations of pre-dispatch logistics modeling

---

## Tech Stack
Python, pandas, NumPy, scikit-learn, imbalanced-learn, Tableau (EDA/visuals)
