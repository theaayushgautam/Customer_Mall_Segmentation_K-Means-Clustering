# Customer Segmentation using K-Means Clustering (Mall Customers)

This project demonstrates **customer segmentation** using **K-Means clustering** on the popular **Mall Customers** dataset. The goal is to group customers based on their spending behavior so businesses can design better marketing and product strategies.

---

## 📌 Project Overview

Customer segmentation means grouping customers into clusters based on similar characteristics such as:
- **Annual Income**
- **Spending Score**

Since the dataset contains **no target label**, this is an **Unsupervised Machine Learning** problem.

---

## ✅ What This Project Covers

- Loading and exploring the dataset using **Pandas**
- Selecting features for clustering (**Annual Income (k$)** and **Spending Score (1-100)**)
- Training **K-Means clustering**
- Finding the optimal number of clusters using the **Elbow Method (WCSS / inertia)**
- Visualizing clusters + centroids using **Matplotlib**
- Predicting the cluster for a new unseen customer
- Saving and loading the trained model using **Joblib**
- (Optional) Running a simple **Tkinter GUI** for user input and prediction

---

## 📊 Dataset

**Mall Customers Dataset** includes the following columns:
- `CustomerID`
- `Gender`
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)` *(a mall-defined score from 1 to 100)*

Each row represents one customer.

---

## 🧠 Model Used

### K-Means Clustering
K-Means groups customers by minimizing the distance between customers and the cluster centroid.

**Important Note:**  
K-Means cluster labels like `0,1,2,3,4` are **just indexes** — their meaning must be interpreted using the **centroids** (`cluster_centers_`).

---

## 📉 Elbow Method (WCSS / Inertia)

To choose the best number of clusters **K**, we use the Elbow Method:
- Train K-Means for K = 1..10
- Compute **WCSS (Within-Cluster Sum of Squares)** each time
- Plot WCSS vs K
- Pick the “elbow point” where improvement slows down

In this dataset, the elbow commonly appears at **K = 5**.

---

## 🖼️ Cluster Visualization

We plot:
- **Annual Income** (x-axis)
- **Spending Score** (y-axis)
- Cluster colors for each group
- **Centroids** in magenta

Typical segments include:
- High income, high spending
- High income, low spending
- Low income, high spending
- Low income, low spending
- Medium income, medium spending

---

## 🔮 Predicting for a New Customer

Example:
```python
k_means.predict([[15, 39]])  # annual income=15, spending score=39
