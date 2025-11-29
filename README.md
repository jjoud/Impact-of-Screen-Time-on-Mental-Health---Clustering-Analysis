This project explores how digital habits and screen-time behaviors relate to mental-health indicators using **unsupervised machine learning**.
The goal is to discover natural grouping patterns among individuals based on their screen-time, sleep patterns, anxiety levels, productivity, and emotional well-being.

Dataset Source (Kaggle):
[https://www.kaggle.com/datasets/khushikyad001/impact-of-screen-time-on-mental-health](https://www.kaggle.com/datasets/khushikyad001/impact-of-screen-time-on-mental-health)

---

## 📁 Project Overview

The project performs a complete clustering workflow including:

* Data loading and inspection
* Duplicate checking and dataset integrity validation
* Exploratory analysis through distributions and feature inspection
* Feature selection focusing on behavioral & psychological metrics
* Data scaling using **Standardization (Z-score normalization)**
* Applying and comparing multiple clustering algorithms:

  * **K-Means**
  * **Gaussian Mixture Models (GMM)**
  * **Hierarchical Clustering (Ward linkage)**
* Dimensionality reduction using **PCA (Principal Component Analysis)**
* Visualization of clusters and interpretation of psychological patterns

This allows us to see how people cluster based on digital behavior and mental-health symptoms without using labeled data.

---

## 📚 Dataset Description

The dataset includes numerical features describing:

* Daily screen time
* Social media usage
* Sleep duration and sleep quality
* Anxiety level
* Stress level
* Productivity
* Mood/emotional state

Seven numerical variables were selected as core features for clustering.

The dataset was checked for:

* Missing values
* Duplicate rows
* Distribution imbalance

The data was clean and ready for preprocessing.

---

## 🔧 Data Preprocessing

1. **Feature Selection**
   Seven numerical psychological and behavioral variables were selected as the main clustering inputs.

2. **Scaling**
   `StandardScaler` was used to normalize all selected features to avoid scale dominance.

   This ensures that features like *screen hours* and *stress scores* contribute fairly.

---

## 🤖 Machine Learning Models Used

### ⭐ 1) K-Means Clustering

* Trained across multiple *k* values.
* The best value of **k = 2** was selected using silhouette analysis.
* PCA visualization shows two partially distinct groups.
* Cluster interpretation:

  * Cluster 0 → Lower anxiety/stress, healthier emotional scores
  * Cluster 1 → Higher anxiety/stress, worse emotional state

### ⭐ 2) Gaussian Mixture Models (GMM)

* Provides soft probabilistic clustering instead of hard assignments.
* Reveals overlapping behavioral profiles not captured by K-Means.
* Cluster visualizations in PCA space show smooth boundaries between groups.

### ⭐ 3) Hierarchical Clustering (Ward)

* Dendrogram used to observe hierarchical structure.
* Useful for visualizing merging behavior and relationship strength.
* PCA scatter plot shows how hierarchical clusters compare to K-Means/GMM.

---

## 📉 Dimensionality Reduction (PCA)

PCA reduces the 7-dimensional feature space to:

* **2 components** for visualization
* **3 components** for deeper interpretation

Insights from PCA:

* Clusters separate mainly along anxiety, stress, and emotional-well-being dimensions.
* Screen-time is correlated with mental-health indicators but not the strongest separating feature.
* The moderate silhouette scores confirm partially overlapping behavioral groups.

---

## 🧠 Key Findings

* Two primary behavioral/psychological groups appear in the population.
* Higher screen-time correlates with:

  * Increased stress and anxiety
  * Lower emotional well-being
  * Reduced productivity
* PCA shows that mental-health features drive the clustering more than raw screen-time alone.
* GMM reveals nuanced overlaps, meaning individuals may share mixed characteristics.
