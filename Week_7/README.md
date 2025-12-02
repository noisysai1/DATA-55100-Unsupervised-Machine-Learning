**Week 7 – Self-Organizing Maps (SOM) Applied to the Traveling Salesman Problem (TSP)**

Week 7 focused on Self-Organizing Maps (SOMs) — an unsupervised neural-network-based technique traditionally used for dimensionality reduction, topology preservation and clustering.
This week, I implemented SOM to solve a well-known optimization problem:

👉 The Traveling Salesman Problem (TSP).

You used MATLAB and Python (Colab) to:

Implement SOM mechanics (competition, cooperation, adaptation)
Train a SOM to approximate the shortest tour
Visualize nodes adjusting to city coordinates
Analyze performance, convergence, topology preservation
Your write-up, codeand results are fully captured in the uploaded files.


Assignment 7


**Week7 UML.ipynb - Colab**


**🧠 1. Technical Description of the Method (What I Learned)**

According to pages 1–2 of your notebook, SOM works using three key processes:


Week7 UML.ipynb - Colab

🔹 1. Competition

Each neuron has a weight vector.
For every input city:

Compute Euclidean distance between city and each node
Select the Best Matching Unit (BMU) — the closest node
This determines which node “wins” for that training sample.


🔹 2. Cooperation

Once the BMU is found:

Neighboring nodes around the BMU are also updated
Influence decreases with distance → controlled by a neighborhood function
You experimented with neighborhood sizes:

- Neighborhood **±2**
- Neighborhood **±1**
- Neighborhood **±0**

This is shown clearly in your MATLAB code on pages 2–4.



🔹 3. Adaptation

Weights of the BMU + neighbors are updated:

**wnew​=wold​+α(x−wold​)**
Where

α = learning rate (decreases over iterations)

Multiple iterations → nodes gradually move toward city coordinates

This allows SOM to learn the tour path structure.

🔹 Why SOM Works for TSP

SOM naturally forms a continuous loop, preserving neighborhood relationships.
As training progresses:

Node weights stretch and bend to match city coordinates

The final chain of nodes approximates a TSP route

This is demonstrated by your visualizations on pages 1 and 4.


Assignment 7

**⚙️ 2. Design of the Algorithms (How I Implemented It)**

Your provided code includes:

✔ Defining 10 cities with (x,y) coordinates

(Same in MATLAB and Python)

✔ Random initialization of SOM node weights

Using either:

MATLAB’s rand(10,2)

Python's:

**w = x + np.random.normal(scale=0.05, size=x.shape)**
✔ Training loop

On each iteration:

Random permutation of cities

For each city:

Find nearest node

Update BMU and its neighbors (±2, ±1, ±0 cases)

Check convergence using weight norm difference

Stop when diff < threshold

✔ Visualization function (plot_map())

Plots cities

Plots node chain

Shows how nodes reshape across iterations


**Week7 UML.ipynb - Colab**

**📊 3. Results of the Algorithm (What the Plots Show)**

📌 Initial State

Nodes are scattered randomly
City labels: C1 ... C10
Blue stars represent city coordinates

📌 During Training

Nodes gradually “pull” toward cities
Chain straightens and reduces crossing lines
Neighborhood interactions create smooth transitions

📌 Final Configuration

Shown clearly in the image on page 4:


Week7 UML.ipynb - Colab

SOM forms a continuous red path connecting cities
Node positions resemble a near-optimal tour
Some shortcuts remain imperfect — expected because SOM is heuristic, not exact TSP solver
Important Observations (From Page 4–5)
Node placement reflects city distribution
Topology preservation ensures no abrupt jumps
Convergence visualization shows decreasing weight movement
Iteration count helps evaluate stability
Final path connects all cities with minimal overlap


**🧐 4. Analysis of Results (What This Means)**

Week7 UML.ipynb - Colab

Your analysis highlights:

✔ SOM adapts well to city structure

Nodes reshape naturally into a loop approximating the tour.

✔ Final path is near-optimal

Not perfect — but SOM reduces crossing and shortens total distance over time.

✔ Neighborhood size matters

±2 = smoother but slower
±1 = balanced
±0 = sharp, less stable

✔ SOM is not an exact solver

But it provides:

Efficient approximation
Strong visualization
Insight into map–data relationships

✔ Stability depends on randomness

Different initializations → slightly different tours
SOM quality improves with:
Lower learning rates
Gradual neighborhood shrinking

More iterations

**🏁 5. Conclusion (Week 7 Summary)**

**Week7 UML.ipynb - Colab**

This week demonstrated that SOM is a powerful tool for topology-preserving learning and visual optimization. Applied to the TSP:
It creates a continuous path through all cities
Shows how nodes self-organize
Provides an interpretable approximation
Reveals the dynamic convergence of neural-based unsupervised learning
Week 7 gave you hands-on experience with neural topology learning, heuristic optimization and visual analysis.

## 🔹 Results
- SOM nodes initially scattered but gradually organize into a loop
- Final node chain approximates the TSP route
- Neighborhood size affects smoothness and convergence
- Final map preserves data topology and reduces path intersections

---

## 🔹 Key Insights
- SOM provides a powerful heuristic for TSP-like problems
- It balances clustering, dimensionality reductionand path optimization
- Convergence visualization helps evaluate algorithm performance
- SOM’s tour is near-optimal but not guaranteed to be globally minimal

---

## 🔹 Conclusion
Self-Organizing Maps demonstrate how neural-based unsupervised learning can be applied to real optimization problems. 
Week 7 provided practical experience in topology preservation, heuristic modeling and iterative convergence analysis.

