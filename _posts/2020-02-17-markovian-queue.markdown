---
layout: post
title:  "Markovian Queuing System"
date:   2020-02-17 10:12:41 -0700
categories: Finance
---
# Discrete-Time Markov Chain (DTMC)
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

  - Intuition: Transient state analysis for DTMC of n step is simply the transition matrix to the nth power $P^{n}$, notice the
    from the Kolmogorov Eq, $P(i,l)P(l,j)$ is equivalent to a dot product of row i and column j of matrix P

- Steady State Analysis:
  - Find $P(j) = \lim_{n\to\infty} P^n(i,j)$ such that $\sum_{j \in S}{P(j)} = 1 $
  - $\lim_{k\to\infty} P_{k+1}(j) = \lim_{k\to\infty} \sum_{i}{P_k(i)P(i,j)} = \sum_{i}{[\lim_{k\to\infty}P_k(i)] P(i,j)}$
  - $ P(j) = \sum_{i}{P(i)P(i,j)}$ that also satisfies $\sum_i{P(i)} = 1$ 
  - Matrix form: $\pi = \pi P , \lvert\pi\lvert = 1 $, $ \pi = [\pi_0, \pi_1, ....\pi_k] $
  - Intuition: as the markov chain reach steady state, what is the probability that it will land in a certain state

  - absorbing state
    - probably to reach non-absorbing state i is $a_i = \sum_j{a_jp_{ij}}$ 
    - time to absorption from state i $\mu_i = 1 + \sum_j{p_{ij}\mu_j}$, absorbing state has $\mu_i = 0$

- Birth and Death Markov Chain
  - $ P(i,j) = \lambda_i, for\ j = i+1; \mu_i, for\ j = i-1; 1-\lambda_i-\mu_i, for\ j = i; 0\ otherwise $
  - $ a_0 = 1, a_j = \frac{\lambda_0, \lambda_1, ...\lambda_{j-1}}{\mu_1, \mu_2, ...\mu_j}$
  - $ P(j) = \frac{a_j}{\sum_i{a_i}}$ do not have to worry about convergence if state space is finite

# Renewal Process

# Continuous-Time Markov Chain (CTMC)
- Markov Property: $P(X_{t+s} = y \| X_u, u \leq t) = P(X_{t+s} = y \| X_t)$
  - Note: continuous time is significant more difficult, the TPF now has to capture state changes with respect to time 
- Transition Probability
  - $P_{s,t}(x,y) = P(X_t = y \| X_s =x)$ 
  - Under time-homogeneous assumption
    - $P_{s,t}(x,y) = P_{0,t-s}(x,y) = P_{t-s}(x,y)$ by stationary independent increment property of poisson process
    1. $ P_t(x,y) \geq 0, t \geq 0, \forall x, y$
    2. $ \sum_y{P_t(x,y)} = 1, t \geq 0, x \in S$
    3. $ P_{t+s}(x,y) = \sum_z{P_t(x,z) P_s(z,y)}$, Chapman Kolmogrorov Eq.

# Regnerative Process

# Queueing System
