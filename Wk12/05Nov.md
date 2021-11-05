---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 05 November, Friday (Lecture 19)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Distributions (contd.)
### Standard Gaussian Distribution
This distribution is also known as the standard normal distribution. A CRV $Z$ is said to be a standard Guassian random variable ($Z \sim N(0,1)$) if its PDF is given by
$$f_Z(z) = \frac{1}{\sqrt{2\pi}}e^{-\frac{z^2}{2}}, z \in \mathbb{R}.$$

The Central Limit Theorem states (roughly) that if we add a large number of random variables, the distirbution of the sum is normal.  

We can check that $E[Z] = 0$, as the integral is of an odd function. Also, $\text{Var}(Z) = 1$.  

The CDF of the standard Gaussian distribution is denoted by $\Phi$, and defined as
$$\Phi(x) = P(Z \leq x) = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^x e^{-\frac{u^2}{2}}du$$
This integral does not have a closed solution, but values of it have been tabulated. The CDF of any normal distribution can be written in terms of $\Phi$.  

Some properties of this function are:

* $\lim_{x \to \infty} \Phi(x) = 1, \lim_{x \to - \infty} \Phi(x) = 0$.
* $\Phi(0) = \frac12$
* $\Phi(-x) = 1-\Phi(x)$

Further, for all $x \geq 0$, it satisfies the following bound:
$$\frac{1}{\sqrt{2\pi}}\frac{x}{x^2+1}e^{\frac{-x^2}{2}} \leq 1 - \Phi(x) \leq \frac{1}{\sqrt{2\pi}}\frac{1}{x}e^{\frac{-x^2}{2}}.$$

We can prove this in the following way.
$$\begin{split}
1-\Phi(x) &= \frac{1}{\sqrt{2\pi}}\int_x^{\infty}e^{-\frac{u^2}{2}} du \\
&\leq \frac{1}{\sqrt{2\pi}}\int_x^\infty \frac{u}{x} e^{-\frac{u^2}{2}}du \text{ [as } u \geq x \text{ ]} \\
&= \frac{1}{x\sqrt{2\pi}}\int_x^\infty e^{-\frac{u^2}{2}} d\left(\frac{u^2}{2}\right) \\
&= \frac{1}{x\sqrt{2\pi}} \left[- e^{-\frac{u^2}{2}}\right]_x^\infty \\
&= \frac{1}{\sqrt{2\pi}} \frac{1}{x} e^{-\frac{x^2}{2}}. \end{split}$$

### General Gaussian Distribution
The general Gaussian distribution is obtained from the standard Gaussian by shifting and scaling. If $X = \sigma Z + \mu$, where $\sigma > 0$, then $X \sim N(\mu, \sigma^2)$.  

We can see that $E[X] = \sigma E[Z] + \mu$, which is $\mu$, and $\text{Var}(X) = \sigma^2 \text{Var}(Z)$, which is $\sigma^2$.  

Conversely, if $X \sim N(\mu, \sigma^2)$, then $Z = \frac{X-\mu}{\sigma} \sim N(0,1)$.  

The CDF of $X$ is given by
$$\begin{split}
F_X(x) = P(X \leq x) &= P(\sigma Z + \mu \leq x) \\
&= P\left(Z \leq \frac{x -\mu}{\sigma}\right) \\
&= \Phi\left(\frac{x-\mu}{\sigma}\right). \end{split}$$

We can then easily find the PDF of $X$ as
$$\begin{split}
f_X(x) &= \frac{d}{dx}F_X(x) = \frac{d}{dx} \Phi\left(\frac{x-\mu}{\sigma}\right) \\
&= \frac{1}{\sigma} \Phi'\left(\frac{x-\mu}{\sigma}\right) = \frac{1}{\sigma}f_Z\left(\frac{x-\mu}{\sigma}\right) \\
&= \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}. \end{split}$$

Thus, if $X$ is a normal RV with mean $\mu$ and variance $\sigma^2$, then $X \sim N(\mu, \sigma^2)$.  

We can see, then, that a linear transformation of a Gaussian RV is another Gaussian RV. More concretely, if $X \sim N(\mu_X, \sigma_X^2)$ and $Y = aX + b$, then $Y \sim N(a\mu_X + b, a^2 \sigma_X^2)$.

### Gamma Distribution
The gamma function $\Gamma(x)$ is an extension of the factorial function to real numbers.
