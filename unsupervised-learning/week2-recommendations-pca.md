# Week 2 — Recommendations, Collaborative Filtering, PCA

## 🎬 Making Recommendations (Per-User Linear Models)

Prediction:

\[
\hat{y}_{u,i} = w^{(u)T} x^{(i)} + b^{(u)}
\]

Cost (MSE, only for rated items):

\[
J = \sum_{(u,i) \in \text{rated}} (\hat{y}_{u,i} - y_{u,i})^2
\]

Optimize with gradient descent.

---

# 🧩 Collaborative Filtering (Learning Features Automatically)

Learn simultaneously:
- User parameters \( w^{(u)} \), \( b^{(u)} \)  
- Item features \( x^{(i)} \)

CF solves:

\[
J(w,b,x) = J_{\text{users}} + J_{\text{items}}
\]

---

# 🔁 Binary Labels (Likes, Clicks)
Use logistic regression:

\[
\hat{y} = \sigma(w^T x + b)
\]

Loss: **binary cross-entropy**.

---

# 🔄 Mean Normalization
Improves prediction and generalization.

Process:
- Compute mean per user  
- Replace ratings with  
  \[
  r' = r - \mu
  \]

Unseen ratings become 0.

---

# 🔍 Finding Similar Items
Compute:

\[
\| x^{(i)} - x^{(k)} \|^2
\]

Smaller distance → more similar.

---

# 🚧 Limitations of Collaborative Filtering
- Cold start  
- Sparsity  
- Hard to scale retrieval

### Retrieval + Ranking Pipeline
1. Retrieve many candidates  
2. Remove duplicates and already-seen items  
3. Rank with ML model  

---

# 📉 Principal Component Analysis (PCA)
Goal: reduce dimension while preserving **maximum variance**.

### First Principal Component  
Direction maximizing variance.

### Second Principal Component  
Orthogonal to the first.

### Reconstruction
\[
\hat{x} = U_{\text{reduced}} z
\]

Applications:
- Visualization  
- Compression  
- Speeding up ML algorithms  
