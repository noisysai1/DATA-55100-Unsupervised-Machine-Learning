📘 Week 2 – PCA & LDA Implementation + Algorithm Design & Visualization


🧠 1. Technical Summary (What I Learned This Week)

🔹 Principal Component Analysis (PCA)


Transforms original features into new orthogonal components (principal components).
Captures directions with maximum variance.

  Works by computing:

    Covariance Matrix
    Eigenvalues
    Eigenvectors
    Projection onto selected components



🔹 Linear Discriminant Analysis (LDA)

Focuses on maximizing class separation.
Works by computing:
   Class means
   Within-class scatter matrix (Sw)
   Between-class scatter matrix (Sb)
   Eigen decomposition of Sw−1SbS_w^{-1} S_bSw−1​Sb​

Used to project data into the most discriminative direction (1D in this assignment).


📄 All steps were implemented manually using NumPy, not just using library calls—helping me understand the math behind both algorithms.


⚙️ 2. Implementation Breakdown
🔹 Dataset Used
A traffic dataset with 4 main features:


CarCount
BikeCount
BusCount
TruckCount

Target variable: Traffic Situation (for LDA class separation).


🔹 PCA Implementation Steps

✔ Step 1 — Select relevant numeric columns
X = data[['CarCount', 'BikeCount', 'BusCount', 'TruckCount']]
y = data['Traffic Situation']

✔ Step 2 — Compute Covariance Matrix
cov_matrix = np.cov(X, rowvar=False)

✔ Step 3 — Eigen decomposition
eig_values_pca, eig_vectors_pca = np.linalg.eig(cov_matrix)

✔ Step 4 — Sorting eigenvalues/eigenvectors
sorted_indices_pca = np.argsort(eig_values_pca)[::-1]
eig_values_pca = eig_values_pca[sorted_indices_pca]
eig_vectors_pca = eig_vectors_pca[:, sorted_indices_pca]

✔ Step 5 — Project data into 1D, 2D, 3D
pca_1d = np.dot(X, eig_vectors_pca[:, :1])
pca_2d = np.dot(X, eig_vectors_pca[:, :2])
pca_3d = np.dot(X, eig_vectors_pca[:, :3])



🔹 LDA Implementation Steps

✔ Step 1 — Identify unique class labels
class_labels = np.unique(y)

✔ Step 2 — Compute class means
class_means = [np.mean(X[y == label], axis=0) for label in class_labels]

✔ Step 3 — Compute Sw and Sb
within_class_scatter_matrix = np.sum([np.cov(X[y == label], rowvar=False) for label in class_labels], axis=0)
overall_mean = np.mean(X, axis=0)

between_class_scatter_matrix = np.sum([
    np.outer(class_means[i] - overall_mean, class_means[i] - overall_mean)
    for i in range(len(class_labels))
], axis=0)

✔ Step 4 — Eigen decomposition
eig_values_lda, eig_vectors_lda = np.linalg.eig(
    np.linalg.inv(within_class_scatter_matrix).dot(between_class_scatter_matrix)
)

✔ Step 5 — Sort + project into 1-D discriminant axis
sorted_indices_lda = np.argsort(eig_values_lda)[::-1]
eig_vectors_lda = eig_vectors_lda[:, sorted_indices_lda]
lda_1d = np.dot(X, eig_vectors_lda[:, :1])


📊 3. Results & Visualizations
🔹 PCA Plots (1D, 2D, 3D)
You visualized how the dataset looks when compressed into 1, 2, and 3 dimensions.
✔ 1D PCA
Shows distribution along the first principal component.
✔ 2D PCA
Shows relationships between first two principal components.
✔ 3D PCA
Helps reveal clusters, structure, and separability in 3D space.

These visualizations help confirm that PCA:

preserves important variance
exposes hidden patterns in the data
reduces complexity while keeping structure




🔹 LDA 1D Plot
Visualizing LDA projection helped observe how well the algorithm:


separates traffic classes
compresses data into a single discriminative dimension


Excellent for understanding whether classes are linearly separable.
Assignment 2 UML.ipynb - Colabo…

🧐 4. Analysis / What I Understood


PCA captures variance across the dataset, but does not consider class labels.
LDA specifically finds a direction that best separates classes.
PCA is better for compression; LDA is better for classification.
Visualizations clearly showed that:
  PCA reduces noise and reveals structure
  LDA improves class separation in lower dimensions


🏁 5. Week 2 Conclusion
This week helped me practically understand PCA and LDA by manually computing covariance matrices, eigenvalues, eigenvectors, and projections.
Through visualization, I learned how dimensionality reduction:


simplifies data
enhances interpretability
preserves essential information
prepares data for clustering & classification


Week 2 was a strong step forward in mastering unsupervised learning.
Assignment 2 UML.ipynb - Colabo…

📄 README.md (Copy–Paste Ready)
# Week 2 – PCA & LDA Implementation (Dimensionality Reduction)

This week focuses on implementing **Principal Component Analysis (PCA)** and **Linear Discriminant Analysis (LDA)** from scratch using NumPy and visualizing the results in 1D, 2D, and 3D.

## 📘 Concepts Covered
- Covariance matrix computation
- Eigenvalue & eigenvector decomposition
- Sorting eigenvalues to select top components
- Manual PCA implementation
- Manual LDA implementation
- Visualizing PCA (1D, 2D, 3D)
- Visualizing LDA (1D discriminant axis)

---

## 🧠 PCA Implementation Highlights
- Calculate covariance matrix
- Perform eigen decomposition
- Sort eigenvalues in descending order
- Project dataset onto:
  - 1D (PC1)
  - 2D (PC1 & PC2)
  - 3D (PC1, PC2, PC3)

---

## 🧠 LDA Implementation Highlights
- Compute class means
- Build within-class scatter matrix (Sw)
- Build between-class scatter matrix (Sb)
- Solve generalized eigenvalue problem
- Project data onto first discriminant component

---

## 📊 Visualizations
- **PCA 1D, 2D, 3D scatter plots**
- **LDA 1D class-separation plot**

These visualizations help evaluate:
- retained structure
- separability of classes
- effectiveness of dimensionality reduction

---

## 🏁 Summary
PCA → maximizes variance  
LDA → maximizes class separation  

Both techniques reduce dimensionality while preserving important information.

This week strengthened my understanding of algorithm foundations, matrix math, and visual interpretation of reduced feature spaces.


