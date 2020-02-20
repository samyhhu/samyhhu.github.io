---
layout: post
title:  "Markovian Queuing System"
date:   2020-02-17 10:12:41 -0700
categories: Finance
---
Discrete-Time Markov Chain (DTMC)
---------------------------------
- Markov Property: given present and past states, future states is only depended on the current state not the past  
$$P(X_{k+1} = j | X_1 = i_1, X_2 = i_2,...X_k = i) = P(X_{k+1} = j | X_k = i) = P_k(i,j)$$
  - for homogenous process $P_k(i,j) = P(i,j)$
- Basic Property: basic law of probability, note that the column may not necessarily need to sum to 1
$$P(i,j) \geq 0, \sum_{j \in S}{P(i,j)} = 1$$

- Joint distribution: based on markov property, joint distribution is the product of transition probabilities $P_0(i) = P(X_0 = i)$  
$$P(X_0 = i_0, X_1 = i_1 ... ,X_k = i_k) = P_0(i_0) \prod_{j=1}^{k}{P(i_{j-1}, i_j)}$$

- Transient Analysis: $P_k(j) = P(X_k =j)$
  - Chapman-Kolmogorov Eq: transition after m + n steps is sum of product of m-step transition from i to l and n-step transion from l to j over all l  
    $$P^{m+n}(i,j) = \sum_{l \in S}{P^{m}(i,l) P^{n}(l,j)}$$

  - Insight: Transient state analysis for DTMC of n step is simply the transition matrix to the nth power $P^{n}$, notice the
    from the Kolmogorov Eq, $P(i,l)P(l,j)$ is equivalent to a dot product of row i and column j of matrix P

Continuous-Time Markov Chain (CTMC)
------------------------------------

