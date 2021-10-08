---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 08 October, Friday (Lecture 11)
author: Taught by Prof. Pawan Kumar
header-includes: \usepackage{physics}
---

# Probability (contd.)
## Saint Petersberg Paradox
If a coin is tossed repeatedly until it shows heads, and we earn $2^n$ rupees if heads shows up on the $n^\text{th}$ toss. This gives us an infinite expected value.  
Paradoxically, therefore, we should be willing to pay an arbitrarily large amount to play. However, in practice, one is not willing to do so.

## Distributions
### Uniform Distribution
A uniform distribution on $\{1, \dots, n\}$ is defined as
$$P(x) = \begin{cases} \frac{1}{n}  & x \in \{1, \dots, n\} \\ 0 & \text{otherwise}. \end{cases}$$

### Bernoulli Distribution
$X$ is called a Bernoulli random variable with parameter $p$ (denoted $X ~ \text{Bernoulli}(p)$), if
$$P(x) = \begin{cases} p & x = 0 \\ 1 - p & x = 1. \end{cases}$$

### Geometric Distribution
$X$ is called a geometric random variable with parameter $p$ (denoted $X ~ \text{Geometric}(p)$), if
$$P(k) = \begin{cases} p(1-p)^{k-1} & k \geq 1 \\ 0 & \text{otherwise}. \end{cases}$$

### Binomial Distribution
$X$ is called a binomial random variable with parameters $n, p$ (denoted $X ~ \text{Binomial}(n,p)$), if
$$P(k) = \begin{cases} \begin{pmatrix} n \\ k \end{pmatrix} p^k (1-p)^{n-k} & k \geq 0 \\ 0 & \text{otherwise}. \end{cases}$$

Binomial$(n,p)$ is a sum of $n$ independent Bernoulli$(p)$ random variables.  

### Poisson Distribution
The Poisson distribution is the limit of the binomial as $n \to \infty$.
$$\begin{split}
P(X = k) &= \lim_{n \to \infty} \begin{pmatrix} n \\ k \end{pmatrix} \left(\frac{\lambda}{n} \right)^k \left(1 - \frac{\lambda}{n}\right)^{n-k} \\
&= \lim_{n \to \infty} \frac{n \cdot (n-1) \cdots (n-k+1)}{n^k}\frac{\lambda^k}{k!}\frac{(1 - \frac{\lambda}{n})^n}{(1 - \frac{\lambda}{n})^k} \\
&= \frac{e^{-\lambda}\lambda^k}{k!}. \end{split}$$
