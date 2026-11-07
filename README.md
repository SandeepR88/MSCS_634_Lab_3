# MSCS 634 – Lab 3: Clustering with K-Means and K-Medoids

## 1. Purpose of the Lab

The purpose of this lab was to explore and compare two unsupervised machine learning algorithms, K-Means and K-Medoids, using the Wine Dataset from the Scikit-learn Python library. The main objective was to understand how clustering algorithms group similar data points and evaluate their performance using different clustering evaluation metrics.

The Wine dataset contains 178 observations, 13 numerical features, and three wine classes. Before applying the clustering algorithms, I performed data exploration and standardized the features using z-score normalization to ensure that differences in measurement scales would not negatively influence the clustering results.

Both K-Means and K-Medoids were implemented with three clusters (k=3). Their performance was evaluated using the Silhouette Score and Adjusted Rand Index (ARI). I also used Principal Component Analysis (PCA) to visualize and compare the clustering results in two dimensions.

## 2. Key Insights and Observations

The lab demonstrated that K-Means and K-Medoids can produce different clustering results even when applied to the same standardized dataset.

- **K-Means:** This algorithm groups observations based on the distance between data points and calculated cluster centroids. It is computationally efficient and works well when clusters are relatively compact and separated.

- **K-Medoids:** Unlike K-Means, K-Medoids selects actual observations as cluster representatives (medoids). This approach can make it more resistant to outliers because the cluster centers are actual data points rather than calculated averages.

- **Silhouette Score:** This metric helped evaluate how well-separated and cohesive the resulting clusters were. A higher Silhouette Score indicates better-defined clusters.

- **Adjusted Rand Index (ARI):** This metric compared the predicted cluster assignments with the actual wine class labels. A higher ARI indicates greater agreement between the clustering results and the original classifications.

- **Visualization:** The PCA scatter plots provided a visual comparison of the cluster distributions, showing differences in cluster positioning, separation, and overlap. The centroid and medoid markers also helped illustrate how the two algorithms represent their clusters.

Overall, the comparison showed the importance of evaluating clustering algorithms using both internal clustering quality and agreement with known class labels. The Silhouette Score and ARI measure different aspects of performance, so both are useful when interpreting the results.

## 3. Challenges Faced and Decisions Made

One of the main challenges was handling the different measurement scales of the Wine dataset features. Since clustering algorithms rely on distance calculations, features with larger numerical values could disproportionately influence the results. To address this, I used StandardScaler to standardize all numerical features before clustering.

Another challenge was implementing K-Medoids because it is not directly included in the standard Scikit-learn clustering library. I addressed this by implementing the Partitioning Around Medoids (PAM) approach using pairwise Euclidean distances. This allowed me to perform K-Medoids clustering without installing additional libraries.

I also used a fixed random state to improve reproducibility and ensure a consistent comparison between the algorithms. For visualization, I selected PCA to reduce the original 13 features to two principal components while retaining as much information as possible for the graphical comparison.

One important decision was to calculate the Silhouette Score and ARI using the original standardized 13-dimensional dataset rather than the reduced PCA representation. This ensured that the evaluation reflected the complete feature space.

## 4. Conclusion

This lab improved my understanding of unsupervised learning and the practical application of clustering algorithms. Both K-Means and K-Medoids provided useful ways to identify patterns and similarities within the Wine dataset.

The experiment demonstrated that selecting an appropriate clustering algorithm depends on the characteristics of the dataset, the presence of outliers, computational requirements, and the desired clustering results. K-Means is useful when efficiency is important, while K-Medoids can be a better choice when using actual data observations as cluster representatives and improving robustness to outliers is important.

The evaluation metrics and visualizations provided complementary ways to understand and compare the performance of both algorithms.
