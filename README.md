# Lab 3: Clustering Analysis Using K-Means and K-Medoids

## Purpose
The purpose of this lab was to explore unsupervised learning techniques—specifically **K-Means** and **K-Medoids**—using the **Wine Dataset** from scikit-learn.  
The objective was to cluster the wine samples into three groups (corresponding to the three actual wine classes) and evaluate the performance of each algorithm using two metrics:
- **Silhouette Score**, which measures how well the clusters are separated and cohesive.  
- **Adjusted Rand Index (ARI)**, which measures how closely the clusters match the true class labels.

By comparing these two algorithms, we aimed to understand how their design differences (mean vs. medoid centers) affect clustering performance and interpretability.

---

## Key Insights
- **K-Means** achieved a higher **Silhouette Score (0.2849)** and **ARI (0.8975)** than **K-Medoids** (**Silhouette: 0.2676**, **ARI: 0.7411**), indicating that K-Means produced more compact, better-defined clusters that aligned more closely with the actual wine classes.  
- The **PCA visualizations** showed that K-Means generated more **spherical and evenly sized clusters**, while K-Medoids produced slightly **less symmetric clusters** because its medoids are real data points rather than computed centroids.  
- Although K-Medoids was more robust to potential outliers, the Wine dataset is relatively clean and continuous, which favored K-Means.

---

## Challenges and Decisions
- Implementing **K-Medoids** required writing a custom **PAM (Partitioning Around Medoids)** algorithm in NumPy, as it is not included in scikit-learn by default.  
- Selecting the correct number of clusters (**k = 3**) was guided by prior knowledge of the Wine dataset’s three true classes.  
- Standardizing the data with **z-score normalization** was crucial to prevent features with larger numeric ranges from dominating the clustering process.  
- Using **PCA for visualization** allowed meaningful 2D comparison of high-dimensional clusters, even though metrics were calculated in the full standardized space.

---

**Conclusion:**  
For this dataset, **K-Means** outperformed **K-Medoids** in both clustering quality and accuracy relative to the ground truth, making it the more effective algorithm for this analysis.
