---
title: "Bandit Algorithms"
categories: Business, Algorithms, GenerativeAI
author: "Vidya Bhandary"
meta: "#MLOps #BanditAlgorithms  #GenerativeAI #Business"
date: 2025-08-19
---

## 1. **Bandit Algorithms**

Bandit algorithms (often called **multi-armed bandits**) are adaptive decision-making strategies used to balance **exploration** (trying out different options) and **exploitation** (choosing the best-known option).

* Example: An online marketplace deciding which product recommendation to show. The algorithm “tests” multiple products and gradually leans toward the one with the highest expected payoff.
* Core idea: Maximize cumulative reward over time while learning which choices perform best.


## 2. **Business Constraints**

In theory, a pure bandit algorithm optimizes only for statistical reward. But in the **real world**, decisions are subject to constraints such as:

* **Processing Fees**: Each transaction may incur a cost (e.g., credit card fees, API call costs). The algorithm can’t just maximize user conversions; it must factor in the net profit after fees.
* **Contractual Obligations**: Sometimes, contracts mandate a minimum number of impressions, clicks, or transactions for a given partner/vendor. Even if the algorithm finds that a certain option performs poorly, it still must allocate traffic to satisfy agreements.
* **Fairness/Compliance**: Regulations (e.g., anti-discrimination laws, licensing rules) may restrict how outcomes are distributed.


## 3. **Interaction Between the Two**

This is where it gets interesting:

* A **bandit algorithm** would normally keep optimizing toward the highest-performing arm.
* **Business constraints** act as **hard or soft boundaries** that modify the optimization space.

### Example:

Suppose a payment app is routing transactions between two providers:

* Provider A: Lower fees, higher success rate (better from the bandit’s perspective).
* Provider B: Higher fees, lower success rate, but contractual obligation says *at least 30% of transactions must go through B*.

The algorithm has to adapt:

* It can’t just route everything to A.
* It must satisfy the 30% quota for B while still trying to maximize net reward.

This usually requires **constrained bandit algorithms** (a.k.a. **bandits with knapsacks**), where optimization accounts for both rewards and resource/constraint usage.


## 4. **Why It Matters**

* **Business reality vs. pure optimization**: Algorithms must reflect economic, legal, and contractual realities.
* **Net profit focus**: By incorporating fees and obligations, companies avoid situations where an algorithm appears optimal mathematically but is **unsustainable financially or legally**.
* **Scalability**: As operations grow, constraints multiply (e.g., multi-country compliance, partner obligations), so algorithms must evolve accordingly.

👉 In short:
**Bandit algorithms** give you an efficient way to learn and optimize decisions dynamically, but **business constraints** like fees and contracts reshape the optimization problem into a *constrained bandit* setup—where the goal is not just to maximize reward, but to maximize *feasible* reward.

