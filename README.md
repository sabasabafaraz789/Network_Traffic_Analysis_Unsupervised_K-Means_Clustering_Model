# [Network_Traffic_Analysis_Unsupervised_K-Means_Clustering_Model](https://github.com/sabasabafaraz789/Network_Traffic_Analysis_Unsupervised_K-Means_Clustering_Model/blob/fd923b4c03a5a47ec6f2e1a9425faab9b11ce9a4/network-traffic-analysis-unsupervised-k-means-clut.ipynb)


This project presents an **unsupervised machine learning approach** for analyzing network traffic and discovering attack patterns using **K-Means clustering**. The model focuses on grouping similar traffic flows based on engineered network features and evaluating how well the discovered clusters align with known attack categories.

---

##  Methodology

### 1️ Data Preprocessing

* Network Intrusion dataset from  [CIC-IDS- 2017](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset)
  
* Data cleaning includes:

  * Removing infinite values (`±inf`)
  * Dropping missing values
  * Eliminating duplicate flows

---

### 2️ Feature Engineering

To enhance clustering performance, several domain-specific features are created:

* **Fwd_Bwd_Pkts_Ratio** – Measures directional packet imbalance
* **Total_Bytes** – Total data volume per flow
* **Header_to_Data_Ratio** – Protocol overhead indicator
* **Bwd_to_Fwd_Bytes_Ratio** – Traffic asymmetry metric
* **Flow_IAT_Range** – Inter-arrival time variability
* **Avg_IAT** – Average packet inter-arrival time
* **Packet_Size_Spread** – Variance in packet sizes

These features capture both **statistical and behavioral characteristics** of network flows.

---

### 3 Feature Scaling & Dimensionality Reduction

* **PowerTransformer (Yeo-Johnson)** is applied to normalize skewed distributions
* **Min-Max Scaling** ensures uniform feature ranges
* **PCA (Principal Component Analysis)** is used to:

  * Reduce dimensionality
  * Improve clustering efficiency
  * Enable visualization of clusters

---

### 4 K-Means Clustering

* K-Means is applied to the transformed feature space
* The number of clusters is chosen based on:

  * Domain knowledge
  * Known number of attack categories
* The algorithm groups flows by minimizing intra-cluster variance

---

### 5 Cluster Evaluation

Although clustering is unsupervised, evaluation is performed using known labels for analysis:

* **Cluster purity** – Measures dominant attack type per cluster
* **Label distribution analysis** – Evaluates overlap between clusters and attacks
* **Comparative analysis** with other clustering approaches (e.g., DBSCAN)

This helps assess how well K-Means captures real attack behavior.

---

### 6 Visualization

* Clusters are visualized using **PCA-reduced space**
* Each cluster is color-coded
* Visual inspection helps interpret:

  * Cluster separation
  * Overlapping attack patterns

---

##  Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Matplotlib / Seaborn

---

## 👨‍💻 Author
Developed by **Saba Faraz**  
📧 Email: farazsaba96@gmail.com

---
