Week 3 – Basic Sequential Clustering Algorithm (BSCA) + PCA/LDA Integration

This week, I moved beyond dimensionality reduction and learned how to combine PCA, LDA and a clustering method called the Basic Sequential Clustering Algorithm (BSCA).

The goal for Week 3 was to:

Understand BSCA
Apply BSCA to PCA & LDA outputs
Visualize recursive clustering in 1D & 2D
Build a modified BSCA algorithm with tunable parameters
Analyze how variance thresholds and max clusters affect results
All work is based on the notebook and Python script:


Assignment_3_uml

🧠 1. Technical Description (What I Learned This Week)
🔹 Basic Sequential Clustering Algorithm (BSCA)

BSCA is a recursive clustering algorithm that groups data based on dissimilarity and median splits. 
It processes data sequentially, splitting it into clusters based on variance and median thresholds.

Key Ideas of BSCA

Data is recursively divided into smaller clusters.
Splits are based on:

Highest-variance dimension (for multidimensional data)
Median value (for splitting into left & right subsets)

Recursion stops when:

Maximum depth is reached
Not enough data points remain
Cluster limit is reached
Variance is below a threshold

Why BSCA?

Simple, parameter-controlled clustering
Works naturally with PCA and LDA outputs
Helps visualize how dimensionality reduction affects cluster structure
Useful for hierarchical-like clustering without full complexity

⚙️ 2. Algorithm Design

 Assignment can implemented in two versions:

🔹 A. Standard BSCA

This version:

Selects the dimension with highest variance
Finds the median
Splits into left and right subsets
Recursively clusters both sides

Stops at:

max_depth

small dataset

1D median split

Used to cluster:

PCA 1D signals

PCA 2D signals

LDA 1D discriminant scores



🔹 B. Modified BSCA

An improved version introducing:

New Parameters
Parameter	Meaning
alpha	variance threshold for splitting
max_clusters	upper limit on cluster count
max_depth	max recursion depth
Enhancements

Only split if variance > alpha

Enforces maximum number of clusters

Adaptive to data structure

Produces cleaner clusters with better interpretability


📊 3. Results & Visualizations

🔹 PCA 1D Clustering (BSCA)

PCA compresses high-dimensional data into a 1D line.
BSCA identifies natural breaks, revealing cluster-like patterns.
Useful for uncovering hidden structure in the first principal component.


Assignment_3_uml

🔹 PCA 2D Clustering (BSCA)

BSCA splits along the dimension with highest variance.
Shows clusters more clearly than raw high-dimensional data.
Excellent visualization to understand PCA’s effectiveness.


Assignment_3_uml

🔹 LDA 1D Clustering (BSCA)

LDA emphasizes class separation, so clusters reflect separability.
BSCA uncovers additional sub-structure within LDA space.
Helps verify discriminant effectiveness beyond simple projections.


Assignment_3_uml

🔹 Modified BSCA (alpha + max_clusters tests)

You tested multiple combinations:

alpha = [0.1, 0.5, 1.0]
max_clusters = [2, 4, 6]


Observations:

Lower alpha → more clusters (more splitting)

Higher alpha → fewer clusters

Higher max_clusters → deeper recursive splitting

Visualizes sensitivity of clustering to algorithm parameters

This experimentation showed how clustering behavior changes based on hyperparameters.


Assignment_3_uml


🧐 4. Analysis

From Week 3 experiments, I learned:

✔ PCA highlights variance, and BSCA can identify sub-groups within that variance.
✔ LDA highlights class separability, and BSCA can reveal hidden class structures.
✔ Recursive median-based clustering is simple yet powerful for exploratory analysis.
✔ Modified BSCA gives more control, making clustering more meaningful.
✔ Parameter tuning (alpha, max_clusters) significantly affects final cluster patterns.

This week connected dimensionality reduction with clustering, giving a deeper understanding of how reduced representations influence data grouping.


🏁 5. Conclusion

Week 3 successfully combined:

PCA
LDA
BSCA
Modified BSCA
Visualization techniques
Parameter tuning

This week deepened my understanding of how clustering behaves after dimensionality reduction, and how algorithmic variations reveal different structures in data.

Assignment_3_uml


# Week 3 – BSCA Clustering + PCA/LDA Integration  


---

## 📘 Overview
Week 3 focused on learning and implementing the **Basic Sequential Clustering Algorithm (BSCA)** and applying it to PCA and LDA outputs. 
I explored both the original BSCA and a modified version with advanced controls such as variance thresholds and cluster limits.

This week connects **dimensionality reduction** with **recursive clustering**, helping uncover hidden structure in lower-dimensional representations.

---

## 🧠 Concepts Covered
- Basic Sequential Clustering Algorithm (BSCA)
- Median-based recursive splitting
- Variance-based dimension selection
- Clustering PCA outputs (1D & 2D)
- Clustering LDA outputs (1D)
- Modified BSCA with:
  - `alpha` (variance threshold)
  - `max_clusters`
  - `max_depth`
- Visualizing clusters in reduced dimensions

---

## ⚙️ Implementation
### Standard BSCA
- Select highest-variance dimension  
- Split at median  
- Recurse until:
  - depth limit
  - minimal elements  
- Works on PCA (1D & 2D) and LDA (1D)

### Modified BSCA
- Adds a variance threshold (`alpha`)
- Enforces cluster count limit (`max_clusters`)
- Provides more controlled clustering

---

## 📊 Visualizations
- **PCA 1D BSCA clusters**
- **PCA 2D BSCA clusters**
- **LDA 1D BSCA clusters**
- **Modified BSCA cluster experiments**  
  - Tested different `alpha` and `max_clusters` combinations  
  - Illustrated clustering sensitivity  
  - Showed how parameter tuning changes structure

---

## 🏁 Summary
BSCA is a powerful way to analyze structure in PCA and LDA outputs.  
By tuning recursion depth, variance thresholds and cluster limits, it's possible to uncover meaningful patterns in reduced-dimensional data.  
This week significantly strengthened my understanding of how clustering interacts with dimensionality reduction.

---

## 📂 Files
- PCA & LDA code  
- BSCA & Modified BSCA implementations  
- Cluster visualizations  
- Experiments with different alpha and cluster settings
