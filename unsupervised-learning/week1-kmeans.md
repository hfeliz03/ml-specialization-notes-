# Week 1 — Clustering & K-Means

## 🔹 What Is Clustering?
Clustering groups unlabeled examples by similarity. The algorithm infers structure directly from data.

---

## 🔹 K-Means Intuition
1. Choose **K**, the number of clusters  
2. Randomly initialize **K centroids**  
3. Assign each point to the nearest centroid  
4. Move each centroid to the mean of its points  
5. Repeat until convergence (centroids stop moving)

---

## 🔹 Formal Algorithm
1. Randomly initialize \( \mu_1, \mu_2, \dots, \mu_K \)  
2. Repeat:
   - Assign points:  
     \[
     c^{(i)} = \arg\min_k \| x^{(i)} - \mu_k \|
     \]
   - Update centroids:  
     \[
     \mu_k = \frac{1}{|C_k|} \sum_{i \in C_k} x^{(i)}
     \]

---

## 🔹 Empty Clusters
If a cluster gets **0 points**, either:
- Remove the cluster (reduce K)  
- Reinitialize the centroid  

---

## 🔹 Optimization Objective
K-Means does **not** use Gradient Descent.

Cost function (distortion):

\[
J = \frac{1}{m} \sum_{k=1}^K \sum_{x \in C_k} \| x - \mu_k \|^2
\]

It must **never increase** during training.

---

## 🔹 Choosing K — The Elbow Method
Plot K vs distortion J.  
Look for a point where improvements slow significantly.

But:
- There is not always a clear elbow  
- The “best" K depends on your final task  

---

## 🔹 Anomaly Detection
Outliers are detected via **density estimation**:

\[
p(x) \text{ is small} \Rightarrow x \text{ is an anomaly}
\]

Used in:
- Fraud  
- Server failures  
- Manufacturing defects  
