---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 26 October, Tuesday (Lecture 17)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Transforming PDFs
Suppose we wish to find the PDF of a function of a random variable, say $Y = g(X)$. We can use the following formula in the cases where $g$ is differentiable and strictly increasing:
$$f_Y(x) = \begin{cases}
\frac{f_X(x_1)}{g'(x_1)} & g(x_1) = y \\
0 & \not\exists x : g(x) = y \end{cases}$$

To prove this, note that since $g$ is strictly increasing, $g^{-1}$ is well-defined. For each $y$, there exists $x_1$ such that $g(x_1) = y$.  
Now, we can try to find the CDF of $Y$ as follows.
$$\begin{split}
F_Y(y) &= P(Y \leq y) \\
&= P(g(x) \leq y) \\
&= P(x \leq g^{-1}(y)) \\
&= F_X(g^{-1}(y)) \end{split}$$

We can then find the PDF of $Y$ by differentiating and applying the chain rule.
$$\begin{split}
\frac{d}{d y}F_Y(y) &= \frac{d}{d y} F_X(g^{-1}(y)) \\
&= F_X'(x_1) \frac{d x_1}{d y} f_Y(y) \\
&= \frac{F_X'(x_1)}{g'(x_1)} \end{split}$$

In the case where $g$ is strictly decreasing, the formula is simply the negative of what we already have. The modification to the proof occurs in the steps
$$\begin{split}
F_Y(y) &= P(Y \leq y) \\
&= P(g(x) \leq y) \\
&= P(x \geq g^{-1}(y)) \\
&= 1 - P(x \leq g^{-1}(y)) \end{split}$$

Now, when we differentiate, the constant 1 disappears and only the negative sign remains, which proves our claim.  

We can then write a general formula for any monotonic function.
$$f_Y(x) = \begin{cases}
\frac{f_X(x_1)}{|g'(x_1)|} & g(x_1) = y \\
0 & \not\exists x : g(x) = y \end{cases}$$

We can also generalise further to the case where $g$ is piecewise strictly monotonic and differentiable, to
$$F_Y(y) = \sum_{i=1}^n \frac{F_X(x_i)}{|g'(x_1)|}$$
where $x_i$ is the inverse of $y$ in the interval $i$.

## Continuous Distributions
### Uniform Distribution
The PDF of $X \sim \text{Uniform}(a,b)$ is given by
$$f_X(x) = \begin{cases}
\frac{1}{b-a} & a < x < b\\
0 & \text{otherwise} \end{cases}$$

The expectation of this distribution is given by $E[X] = \frac{a+b}{2}$ and its variance by $\text{Var}(X) = \frac{(a-b)^2}{12}$.

### Exponential Distribution
Let $X$ be a CRV, having an exponential distribution with parameter $\lambda> 0$, denoted $X \sim \text{Exponential}(\lambda)$. Its PDF is:
$$f_X(x) = \begin{cases}
\lambda e^{-\lambda x} & x > 0 \\
0 & \text{otherwise} \end{cases}$$

The CDF for this distribution is
$$F_X(x) = \int_0^x \lambda e^{-\lambda t} dt = 1 - e^{-\lambda t}$$

For this distribution $E[X] = \frac1\lambda$ and $\text{Var}(X) = \frac1{\lambda^2}$.  

An important property of the exponential distribution is that it is memoryless, *i.e.*,
$$P(X > x + a \mid X > a) = P(X > x),$$
for all $a, x \geq 0$. This can be easily shown to be true:
$$\begin{split}
P(X > x + a \mid X > a) &= \frac{P(X > x + a, X > a)}{P(X > a)} \\
&= \frac{P(X > x + a)}{P(X > a)} = \frac{1 - F_X(x+a)}{1-F_X(a)} \\
&= \frac{e^{-\lambda(x+a)}}{e^{-\lambda a}} = e^{-\lambda x} \\
&= P(X > x) \end{split}$$
