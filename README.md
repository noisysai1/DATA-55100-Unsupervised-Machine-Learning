📘 Unsupervised Machine Learning – Summary


This repository contains my complete 8-week learning journey for the course DATA 55100: Unsupervised Machine Learning. 
Each week introduced a new set of algorithms, concepts and practical applications centered around clustering, manifold learning, visualization and neural-based unsupervised techniques.

This README summarizes everything I learned from Week 1 through Week 8, along with links to weekly folders that contain code, reports, visualizations and implementation details.

🧠 Week-by-Week Learning Overview

**✅ Week 1 — Introduction to Unsupervised Learning & Distance Measures**

Key Topics:

Foundations of clustering
Distance & similarity measures
Roles of Euclidean, Manhattan, Minkowski distances
Importance of data scaling and normalization
How distance affects cluster formation

Main Takeaway:
Good clustering depends heavily on data representation and distance metrics. Understanding similarity is the core of every unsupervised technique.

**✅ Week 2 — K-Means, Hierarchical Clustering & Exploratory Analysis**

Key Topics:

K-Means clustering
Agglomerative hierarchical clustering
Dendrogram analysis
Determining optimal number of clusters
Exploratory analysis using scatterplots & heatmaps

Main Takeaway:
Different clustering algorithms create different structures and cluster evaluation requires both visual and numerical analysis.


**✅ Week 3 — Principal Component Analysis (PCA) & Linear Discriminant Analysis (LDA)**

Key Topics:

Dimensionality reduction
Covariance vs. correlation PC
Eigenvalues, eigenvectors
Projection of data into principal components
LDA for supervised dimensionality reduction

Main Takeaway:
PCA simplifies high-dimensional data while preserving variance; LDA finds discriminative features when labels are available.


**✅ Week 4 — Multidimensional Scaling (MDS) & Sammon Mapping**

Key Topics:

Metric & non-metric MDS
Stress functions
Sammon error
Visualizing complex high-dimensional structures
Understanding distortions during dimensionality reduction

Main Takeaway:
MDS and Sammon Mapping are powerful for visualizing similarity structures, especially when algorithms need to preserve pairwise distances.


**✅ Week 5 — Fuzzy C-Means & Cluster Tendency (VAT/iVAT)**

Key Topics:

Fuzzy C-Means (FCM) clustering
Membership matrices & fuzzifier parameter (q)
VAT & iVAT for cluster tendency
Visual assessment of clusterability
Comparing multiple (C, q) configurations

Main Takeaway:
In many datasets, clusters are not crisp. FCM captures uncertainty, while VAT/iVAT shows whether clusters even exist.


**✅ Week 6 — Fuzzy Validity Indices (FPC, Dunn, CS, Xie–Beni)**

Key Topics:

Evaluating fuzzy clusters
Partition Coefficient (FPC)
Dunn Index
Xie–Beni Index
CS Index
Effect of fuzzifier on cluster separation

Main Takeaway:
Cluster validity indices help determine how meaningful or separable clusters are, especially in noisy or overlapping datasets.

**✅ Week 7 — Self-Organizing Maps (SOM) & Traveling Salesman Problem (TSP)**

Key Topics:

Neural-based unsupervised learning
Competition, cooperation, adaptation
Weight updates & topology preservation
SOM applied to TSP path optimization
Visualizing convergence of neural maps

Main Takeaway:
SOMs show how unsupervised neural networks can self-organize complex structures and solve optimization problems like TSP.

**✅ Week 8 — Spectral Manifold Learning (Isomap & LLE)**

Key Topics:

Nonlinear dimensionality reduction
Geodesic distances & neighborhood graphs
Global manifold preservation (Isomap)
Local linearity preservation (LLE)
Applications to images, text and high-dimensional geometry

Main Takeaway:
Isomap and LLE overcome PCA’s limitations by uncovering nonlinear manifolds, forming the foundation for modern methods like t-SNE and UMAP.

**🏁 Overall Course Takeaways**

Across all weeks, I developed a strong understanding of:

✔ How unsupervised algorithms find patterns without labels
✔ The importance of distances, similarity and scaling
✔ Dimensionality reduction as a tool for visualization & preprocessing
✔ Hard vs. fuzzy clustering behavior
✔ Spectral and neural approaches for complex structure discovery
✔ How manifold learning reveals hidden geometric relationships

This course provided a complete, practical and mathematical understanding of unsupervised learning — from foundational clustering to advanced neural and spectral techniques.

📂 Repository Structure
📁 Week1 – Distance Measures & Intro
📁 Week2 – KMeans & Hierarchical Clustering
📁 Week3 – PCA & LDA
📁 Week4 – MDS & Sammon Mapping
📁 Week5 – Fuzzy C-Means + VAT/iVAT
📁 Week6 – Fuzzy Validity Indices
📁 Week7 – Self-Organizing Maps (SOM)
📁 Week8 – Isomap & LLE (Nonlinear Dimensionality Reduction)
📄 README.md


Each folder includes:

Notebook or PDF
Code implementation
Summary notes
Interpretation of results

**✨ End of Course Summary**

This 8-week journey helped me build a strong foundation in:
=
Clustering
Dimensionality reduction
Manifold learning
Soft/fuzzy clustering
Neural unsupervised models
Spectral methods.
High-dimensional data visualization

The skills learned in this course apply directly to advanced analytics, machine learning research and real-world data science workflows.
