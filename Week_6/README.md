Week 6 – Fuzzy C-Means Clustering Validity Indices (FPC, Dunn, Xie-Beni, CS) + VAT/iVAT
DATA 55100 – Unsupervised Machine Learning

Week 6 took the fuzzy clustering concepts from Week 5 and pushed them deeper by introducing cluster validity indices. 
These metrics help evaluate how good the clustering actually is — whether clusters are compact, well separated, fuzzy enough or too overlapping.

This week was all about:

✔ Data preprocessing
✔ VAT & iVAT visualization
✔ Fuzzy C-Means (FCM) clustering
✔ Cluster validity indices:

Bezdek’s Partition Coefficient (FPC)

Dunn Index
Xie-Beni Index (XB)
CS Index

✔ Experimenting with different fuzzifier values (q = 1.5, 2.0, 2.5)
✔ Analyzing how validity indices change with fuzziness

Everything below is based directly on your uploaded file.


**UML Assignment 6.ipynb - Colab**

🧠 1. What I Learned in Week 6

🔹 Data Preprocessing (Page 1)


Loaded Traffic dataset
One-Hot encoded categorical variables
Standardized all numerical variables using StandardScaler
Extracted the numeric matrix for VAT, iVAT, and clustering
This ensures that:
All features contribute equally
Fuzzy C-Means performs correctly
Distance calculations are consistent


**UML Assignment 6.ipynb - Colab**

🔹 VAT & iVAT – Cluster Tendency (Pages 1–3)

The VAT heatmap (page 3 left) shows a dense, reddish matrix with no clear block structure → weak cluster tendency.
The iVAT heatmap (page 3 right) improves visibility but still shows faint diagonal bands → slight patterns but no strong clusters.

👉 VAT & iVAT confirm the traffic dataset is highly overlapped and difficult to cluster cleanly.


**UML Assignment 6.ipynb - Colab**

🔹 Fuzzy C-Means (FCM)

You applied FCM clustering with:

C = 2 clusters  
q = 1.5, 2.0, 2.5  (fuzzifier values)


For each configuration, the notebook generated:
Scatter plots with cluster labels
Cluster centers marked with red “X”
Membership-based color blending

On pages 3–4, results show:

Higher q = fuzzier (softer) boundary
Lower q = sharper membership distribution


**UML Assignment 6.ipynb - Colab**

🔹 Cluster Validity Indices (Pages 1–4)

This is the core of Week 6 — you learned how to evaluate fuzzy clusters quantitatively.

✔ 1. FPC – Bezdek’s Partition Coefficient

Measures cluster “crispness.”
Higher FPC → cleaner, more confident clustering
Lower FPC → more fuzziness / overlap

Your results:

q = 1.5 → FPC = 0.8462 (most confident)

q = 2.0 → FPC = 0.7033

q = 2.5 → FPC = 0.6154 (most fuzzy)

✔ 2. Dunn Index

Measures separation / compactness.

Your Dunn Index = 0.0000 for all configurations →
👉 Clusters are completely overlapping (no separation).


**UML Assignment 6.ipynb - Colab**

✔ 3. Xie-Beni Index

Lower XB = better clusters.
Your results show XB = ∞ (infinite), due to:

Very small inter-cluster distance
Very high intra-cluster variance
Severe overlap between clusters
This is typical for traffic datasets with continuous values.

✔ 4. CS Index

Lower CS = more compact clusters.
Your CS values were extremely high, consistent with heavy overlap.

⚙️ 2. Algorithm Design Summary

As shown on pages 1–2:

Defined a reusable function
fuzzy_clustering_and_indices()
to compute:

Centers
Labels
FPC
Dunn Index
Xie-Beni
CS Index
Ran clustering for multiple (C, q) configurations
Plotted cluster results in scatter format


**UML Assignment 6.ipynb - Colab**

📊 3. Results of the Algorithms
📌 VAT & iVAT Results (Page 3)

No strong diagonal blocks
Weak cluster tendency
Patterns inconsistent with hard clustering

📌 FCM Results (Pages 3–4)

For q = 1.5, clusters are:
slightly defined
somewhat crisp
FPC highest
For q = 2.0, clusters become:
fuzzier
more overlap
For q = 2.5, clusters:
blend heavily
boundaries almost disappear

FPC lowest

📌 Validity Indices Summary
q	FPC	Dunn	XB	CS
1.5	0.8462	0.0000	∞	Very high
2.0	0.7033	0.0000	∞	Very high
2.5	0.6154	0.0000	∞	Very high

Conclusion:
All indices indicate very weak clustering, high fuzziness, and nearly zero separation — which is expected for traffic data.


UML Assignment 6.ipynb - Colab

🧐 4. Analysis & Interpretation

✔ Traffic dataset is extremely overlapped
Vehicle counts vary continuously → not suitable for clean clusters.
✔ FPC indicates clustering gets fuzzier as q increases
FCM is flexible, but too much fuzziness reduces interpretability.
✔ Dunn, XB, CS all reveal cluster instability

These confirm:

clusters are not compact
they are not separated
fuzzy modeling is more realistic here

✔ VAT/iVAT + Validity Indices provide a full picture

VAT/iVAT → low tendency
FCM → soft grouping

Validity indices → poor separation but valid fuzzy behavior

🏁 5. Week 6 Conclusion

Week 6 gave a deeper understanding of:

evaluating fuzzy clusters
interpreting validity indices
understanding the limitations of clustering on real-world continuous data
Your combined use of VAT, iVAT, Fuzzy C-Means and four validity indices provided a complete, rigorous analysis of the traffic dataset.
