# MAGIC Gamma Telescope Dataset Analysis: K-Means Clustering & Anomaly Detection

## 🧪 Project Overview
This project applies **K-Means Clustering** and **Clustering-Based Anomaly Detection** to the **MAGIC Gamma Telescope Dataset**, which simulates high-energy gamma particle registrations. The goal is to classify gamma and hadron events and identify anomalous patterns without labeled training data.

## 📁 Dataset Information
- **Source**: UCI Machine Learning Repository – MAGIC Gamma Telescope Dataset
- **Instances**: 19,020
- **Features**: 10 continuous attributes (e.g., `fLength`, `fWidth`, `fCone`)
- **Target Variable**: `Class` – gamma (`g`) or hadron (`h`)
- **Encoding**: Gamma = 0, Hadron = 1

## 🔧 Preprocessing Steps
1. **Feature Engineering**  
   - Retained continuous features for clustering.
   - Encoded target variable for evaluation.

2. **Normalization**  
   - Applied **Min-Max Scaling** to normalize features to the range [0, 1].

3. **Train-Test Split**  
   - Split data into **70% training** and **30% testing** sets.

## 🧠 Methodology

### 1. K-Means Clustering
- **Number of clusters (k)**: 2 (gamma vs. hadron)
- **Objective**: Minimize intra-cluster variance
- **Strengths**: Efficient for low-dimensional data, provides interpretable clusters
- **Weaknesses**: Requires predefined k, assumes spherical clusters

### 2. Clustering-Based Anomaly Detection
- **Method**: Flag points with the highest Euclidean distance from cluster centroids
- **Threshold**: Top 5% of distances classified as anomalies
- **Strengths**: Unsupervised, captures rare events
- **Weaknesses**: Sensitive to distance threshold selection

## 📊 Results

### K-Means Clustering
- **Cluster 1**: 11,712 instances (84% gamma)
- **Cluster 2**: 7,308 instances (78% hadron)
- **Silhouette Score**: 0.31 → moderately separated clusters with some overlap

### Anomaly Detection
- **Anomaly threshold**: ~0.87 (scaled space)
- **Anomaly distribution**:
  - **Hadron anomalies**: 68% (higher variability)
  - **Gamma anomalies**: 32% (rare/deviant patterns)

## 🧩 Key Insights
- K-Means successfully grouped gamma and hadron events despite natural class imbalance.
- Anomaly detection effectively identified rare events, with hadrons showing greater dispersion.
- Overlap between classes suggests room for improvement with more advanced clustering methods.
- The approach is computationally efficient and scalable for large datasets.

## 📈 Visualizations (Included in Report)
- Cluster distribution plots
- Distance-to-centroid histograms with anomaly threshold
- Anomaly composition bar chart

## 🛠 Tools & Libraries
- Python
- Scikit-learn (K-Means, MinMaxScaler)
- NumPy, Pandas
- Matplotlib / Seaborn for visualization

## 📚 References
1. Bishop, C. M. (2006). *Pattern Recognition and Machine Learning*. Springer.
2. Chandola, V., Banerjee, A., & Kumar, V. (2009). *Anomaly Detection: A Survey*. ACM Computing Surveys.
3. UCI Machine Learning Repository: MAGIC Gamma Telescope Dataset.
4. Scikit-learn Documentation.

## 🚀 Future Work
- Experiment with **DBSCAN** or **Gaussian Mixture Models** to handle overlapping clusters.
- Tune anomaly detection thresholds using cross-validation.
- Apply dimensionality reduction (PCA/t-SNE) for better visualization.

---

**Note**: This project was conducted as part of a machine learning and data mining course, focusing on unsupervised learning techniques for classification and anomaly detection.
