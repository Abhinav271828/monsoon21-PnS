---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 20 October, Wednesday (Lecture 15)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Higher Order Moments (contd.)
The moment generating function for a variable $X \sim \text{Binomial}(n,p)$ is given by
$$\begin{split}
M_X(t) &= \sum_{x = 0}^n \begin{pmatrix} n \\ x \end{pmatrix} p^x (1-p)^{n-x} e^{tx} \\
&= \sum_{x = 0}^n \begin{pmatrix} n \\ x \end{pmatrix} (e^tp)^x (1-p)^{n-x} \\
&= (e^t + 1 -p)^n. \end{split}$$

Similarly for $X \sim \text{Poisson}(p)$, we have
$$\begin{split}
M_X(t) &= \sum_{x=0}^\infty e^{-\lambda} \frac{\lambda^x}{x!}e^{tx} \\
&= \sum_{x=0}^\infty e^{-\lambda} \frac{(e^t\lambda)^x}{x!} \\
&= e^{\lambda(e^t-1)}. \end{split}$$

We can also find the variance using the moment generating function: $\text{Var}(X) = M_X''(0) - M_X'(0)^2$.
