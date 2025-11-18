# Week 1 – Unsupervised Machine Learning  
## Dimensionality Reduction: PCA & LDA  

This week focused on two major dimensionality reduction techniques in unsupervised learning: **Principal Component Analysis (PCA)** and **Linear Discriminant Analysis (LDA)**.  
These methods help simplify complex datasets and extract the most important patterns.

---

## 📌 Principal Component Analysis (PCA)

PCA reduces the number of variables in a dataset while preserving most variance.

### Steps:
- Mean-center the data  
- Compute covariance/correlation matrix  
- Perform eigenvalue decomposition  
- Rank eigenvectors by eigenvalues  
- Select top k components  
- Project data onto the new lower-dimensional space  

### Benefits:
- Noise reduction  
- Feature extraction  
- High-dimensional visualization  
- Preprocessing for machine learning models  

### Limitation:
PCA assumes **linear** relationships.

---

## 📌 Linear Discriminant Analysis (LDA)

LDA finds feature combinations that best separate classes, but can also be applied in an unsupervised way for dimensionality reduction.

### Steps:
- Compute within-class scatter matrix  
- Compute between-class scatter matrix  
- Perform eigenvalue decomposition  
- Select eigenvectors with highest discrimination power  
- Project data into reduced space  

### Benefits:
- Maximizes class separability  
- Improves classification performance  
- Useful for visualization  

### Limitation:
Also assumes **linear** boundaries.

---

## 🧠 Summary

- PCA → maximizes variance  
- LDA → maximizes class separation  
- Both reduce dimensionality  
- Both rely on eigenvalues/eigenvectors  
- Both may overlook non-linear patterns  
