# Week 3 — Reinforcement Learning & Deep Q-Networks

## 🧠 What Is Reinforcement Learning?
RL learns behavior using **rewards and penalties**.

Applications:
- Robotics  
- Industrial automation  
- Stock trading  
- Video game agents  

---

# 🔁 Discount Factor (γ)

\[
R = r_1 + \gamma r_2 + \gamma^2 r_3 + \dots
\]

Reward sooner → more valuable.

---

# 📦 Markov Decision Process (MDP)
State transitions depend **only** on current state, not history.

---

# 🧩 State-Action Value Function (Q-function)

\[
Q(s,a) = \text{return from choosing action } a \text{ in state } s
\]

Optimal choice:

\[
\pi(s) = \arg\max_a Q(s,a)
\]

---

# 🧮 Bellman Equation
Defines Q recursively:

\[
Q(s,a) = r(s,a) + \gamma \max_{a'} Q(s', a')
\]

---

# 🧠 Deep Q-Network (DQN)

### Training Loop
1. Initialize Q-network  
2. Observe experience \((s,a,r,s')\)  
3. Store in **replay buffer**  
4. Train using target:

\[
y = r + \gamma \max_{a'} Q(s', a')
\]

5. Update Q

---

# 🎯 ε-Greedy Policy

\[
\text{With prob } 1-\epsilon: \text{ exploit best action}
\]
\[
\text{With prob } \epsilon: \text{ explore random action}
\]

Typical: \( \epsilon = 0.05 \)

---

# 🔁 Experience Replay
Breaks correlation between consecutive experiences by sampling random batches.

Benefits:
- More stable learning  
- Better generalization  
- Critical for deep RL  
