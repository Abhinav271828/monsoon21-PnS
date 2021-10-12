---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 12 October, Tuesday (Lecture 14)
author: Taught by Prof. Pawan Kumar
header-includes: \usepackage{physics}
---

# Probability (contd.)
## Distributions
### Poisson Distribution (contd.)
Suppose we wish to send a bitstring of length $n = 10^4$. The probability that a bit can be corrupted is $10^{-6}$. We need to know the probability that the message will arrive uncorrupted.  

We can use the Poisson distribution by taking $\lambda = np = 10^4 10^{-6}$, *i.e.*, $X \sim \text{Poisson}(0.01)$ is the number of corrected bits. Therefore our answer is
$$\begin{split}
P(X = 0) &= \frac{\lambda^k}{k!}e^{-\lambda} \bigg | _{k=0} \\
&= \frac{1}{1}e^{-0.01} \\
&\approx 0.99 \end{split}$$

## Expectations
### Poisson Distribution
Let $X \sim \text{Poisson}$, *i.e.*,
$$P_X(k) = \begin{cases}
\frac{e^{-\lambda} \lambda^k}{k!} & k \in R_X \\
0 & \text{otherwise}. \end{cases}$$

Therefore,
$$\begin{split}
E[X] &= \sum_{x=0}^\infty x\frac{e^{-\lambda}\lambda^x}{x!} \\
     &= \sum_{x=1}^\infty x\frac{e^{-\lambda}\lambda^x}{x!} \\
     &= e^{-\lambda}\sum_{x=1}^\infty x\frac{\lambda^x}{x!} \\
     &= e^{-\lambda} \lambda e^\lambda \\
     &= \lambda. \end{split}$$
     
### Binomial Distribution
Let $X \sim\text{Binomial}(n,p)$; then
$$P_X(k) = \begin{cases}
{n \choose k}p^k(1-p)^{n-k} & k = 0, 1, \dots, n \\
0 & \text{otherwise}. \end{cases}$$

Hence,
$$\begin{split}
E[X] &= \sum_{x=0}^n x {n \choose x}p^x(1-p)^{n-x} \\
&= \sum_{x=1}^n x {n \choose x}p^x(1-p)^{n-x} \\
&= \sum_{x=1}^n n {{n-1} \choose {x-1}}p^x(1-p)^{n-x} \\
&= \sum_{z=0}^{n-1} {{n-1} \choose z}p^{z+1}(1-p)^{n-z-1} \\
&= np. \end{split}$$

## Variance and Standard Deviation
The variance measures the divergence from the expected value of the actual values. It is defined by
$$\text{Var}(X) = E((X - \mu)^2) = \sum_x (x- \mu)^2 p(x).$$

Its positive square root is called the standard deviation:
$$\sigma = \sqrt{\text{Var(X)}}.$$

If $X$ is a discrete random variable with mean $\mu$, then
$$\text{Var}(X) = E[X^2] - \mu^2.$$

## Higher Order Moments
Just as we have $E[(X-\mu)^2]$, we can define $E[(X-\mu)^3]$ and any other power. In other words, the $n^\text{th}$ moment about the mean of a variable $X$ is defined as
$$\mu_n = E[(X - E[X])^n].$$

The 0$^\text{th}$ central moment $\mu_0$ is 1.  

The moment generating function $M_X(t)$ is the expectation value
$$M_X(t) = E[e^{tX}] = \sum_x e^{tx}p_X(x).$$

Clearly, $M_X(0) = 1$. Furthermore, $E[X] = M_X'(0)$, where the derivative is taken w.r.t $t$.
