---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | Assignment 2
author: Abhinav S Menon
---

# Problem 1
10 shots are taken. Each has a probability 0.2 of hitting the target. The total number of hits is called $X$.

## Part 1
We need to find the PMF of $X$. Consider the probability $P(X = n)$.  

There are ${10 \choose n}$ ways to choose $n$ shots to have hit the target. Each shot then has a 0.2 chance of hitting the target. Furthermore, the remaining shots each have a 0.8 chance of *not* hitting the target. Therefore,
$$
P(X = n) = \begin{cases}
{10 \choose n} (0.2)^n(0.8)^{10-n} & 0 \leq n \leq 10 \\
0 & \text{otherwise}. \end{cases}$$

This is a binomial distribution.

## Part 2
We wish to find the expectation and variance of $X$.  

We know that since $X \sim \text{Binomial}(10,0.2)$. This means that $E[X] = np = 2$.  

For the variance, we use the fact that a binomial variable is the sum of $n$ independent Bernoulli variables, and the fact that variance is linear for independent variables. Thus,  
$\text{Var}(\text{Binomial}(n,p)) = n \cdot \text{Var}(\text{Bernoulli}(p)).$

Now, to find $\text{Var}(\text{Bernoulli}(p))$, let $B \sim \text{Bernoulli}(p)$ and $\mu = E[B]$. By definition, $\mu = 0 \cdot p + 1 \cdot (1-p) = 1-p$.  
We know that $\text{Var}(B) = E[(B-\mu)^2]$. Therefore,
$$\begin{split}
\text{Var}(B) &= [0-(1-p)]^2 \cdot p + [1-(1-p)]^2 \cdot (1-p) \\
&= p(1-p)^2 + p^2(1-p) \\
&= p(1-p). \end{split}$$

Therefore $\text{Var}(\text{Bernoulli}(n,p)) = n \cdot \text{Var}(B) = np(1-p)$. This gives us $\text{Var}(X) = 10 \cdot 0.2 \cdot 0.8 = 1.6$.

## Part 3
We can see that $Y = 2X - 3$ (as he gains $2X$ dollars and loses 3). We know that expectation is linear; therefore $E[Y] = E[2X - 3] = 2E[X] - 3$.  

Hence, $E[Y] = 2(2) - 3 = 1$. Thus his expected profit is \$1.  

Also, $Y^2 = 4X^2 - 12X + 9$, which means that $E[Y^2] = 4E[X^2] - 12E[X] + 9$.  
Moreover, $\text{Var}(X) = E[X^2] - E[X]^2 \implies E[X^2] = 1.6 + 2^2 = 5.6$.  

Substituting, $E[Y] = 4 \cdot 5.6 - 12 \cdot 2 + 9 = 7.4$. Therefore the variance of his profit is 7.4.

## Part 4
In this case $Z = X^2$ is Tharun's profit. We need to find $E[Z] = E[X^2]$.  

Consider $\text{Var}(X)$. We know that $\text{Var}(X) = E[(X-\mu)^2] = E[X^2 + \mu^2 - 2X\mu]$. From this we get
$$\begin{split}
\text{Var}(X) &= E[X^2] + E[\mu^2] - E[2X\mu] \\
&= E[X^2] + \mu^2 - 2\mu E[X] \\
&= E[X^2] - E[X]^2. \end{split}$$

Therefore, $E[X^2] = \text{Var}(X) + E[X]^2 = 1.6 + 2^2 = 5.6$.

# Problem 2
$X$ is a discrete random variable with the PMF
$$P_X(x) = \begin{cases}
0.1 & x = 0.2 \\
0.2 & x = 0.4 \\
0.2 & x = 0.5 \\
0.3 & x = 0.8 \\
0.2 & x = 1 \\
0 & \text{otherwise}. \end{cases}$$

## Part 1
The range of $X$ is the set $\{0.2, 0.4, 0.5, 0.8, 1\}$.

## Part 2
$$\begin{split}
P(X \leq 0.5) &= P(0.2) + P(0.4) + P(0.5) \\
&= 0.1 + 0.2 + 0.2 \\
&= 0.5. \end{split}$$

## Part 3
$$\begin{split}
P(0.25 < X < 0.75) &= P(0.4) + P(0.5) \\
&= 0.2 + 0.2 \\
&= 0.4. \end{split}$$

## Part 4
The expectation of $X$ can be found as
$$\begin{split}
E[X] &= \sum_x xP(X = x) \\
&= (0.2 \cdot 0.1) + (0.4 \cdot 0.2) + (0.5 \cdot 0.2) + (0.8 \cdot 0.3) + (1 \cdot 0.2) \\
&= 0.02 + 0.08 + 0.10 + 0.24 + 0.2 \\
&= 0.64. \end{split}$$

To find the variance of $X$, first we calculate
$$\begin{split}
E[X^2]&= \sum_x x^2 P(X=x) \\
&= (0.2)^2 \cdot 0.1 + (0.4)^2 \cdot 0.2 + (0.5)^2 \cdot 0.2 + (0.8)^2 \cdot 0.3 + (1)^2 \cdot 0.2 \\
&= 0.004 + 0.032 + 0.05 + 0.192 + 0.2 \\
&= 0.433. \end{split}$$

Then we get $\text{Var}(X) = E[X^2] - E[X]^2 = 0.433 - 0.4096 = 0.0234$.

# Problem 3
We have the PMF of $X$ as
$$P_X(x) = \begin{cases}
0.2 & x = 0 \\
0.2 & x = 1 \\
0.3 & x = 2 \\
0.3 & x = 3 \\
0 & \text{otherwise}. \end{cases}$$

We also have $Y = X(X-1)(X-2)$. Therefore,  
if $X$ is 0, then $Y$ is 0;  
if $X$ is 1, then $Y$ is 0;  
if $X$ is 2, then $Y$ is 0; and  
if $X$ is 3, then $Y$ is 6.  

Thus,
$$\begin{split}
P(Y=0) &= P(X=0) + P(X=1) + P(X=2) \\
&= 0.2 + 0.2 + 0.3 \\
&= 0.7, \end{split}$$
and
$$P(Y=6) = P(X=3) = 0.3.$$

We can write $Y$'s PMF as
$$P_Y(y) = \begin{cases}
0.7 & y = 0 \\
0.3 & y = 6. \end{cases}$$

# Problem 4
A player is dealt 13 cards from a standard 52-card deck.

## Part 1
(assuming replacement)  

The probability that any card dealt is a king is equal to
$$\frac{\text{number of kings}}{\text{total number of cards}},$$
which is $\frac{4}{52} = \frac{1}{13}.$ Therefore this is also the probability that the 13th card is a king.

## Part 2
(assuming replacement)  

Each of the first 12 cards dealt must *not* be a king. The probability of *not* getting a king on any given card is $1 - \frac{1}{13} = \frac{12}{13}$. Once this happens, the probability that the 13th card is a king is (as found above) $\frac{1}{13}$.  

Therefore the the probability that the 13th card is the first king dealt becomes $(\frac{12}{13})^{12}(\frac{1}{13})$.

# Problem 5
An average of 20 customers arrive per hour. We have defined $X$ as the number of customers from 1300h to 1500h; we know that $X \sim \text{Poisson}(40)$ (as the interval is of 2 hours).  

We wish to find $P(15 < X < 25)$. Since $X$ is a Poisson random variable,
$$P(X=k) = \frac{e^{-40} 40^k}{k!},$$

which implies that
$$\begin{split}
P(15 < X < 25) &= \sum_{i=16}^{24} P(X=i) \\
&= \sum_{i=16}^{24} \frac{e^{-40} 40^i}{i!} \\
&\approx 0.00448. \end{split}$$

# Problem 6
Each program has a probability $p$ of being correct. $X$ is defined as the number of tries until the program works correctly.  
We can see that $P(X=k) = p(1-p)^{k-1}$ for all $k \geq 1$. This is a geometric distribution, *i.e.*, $X \sim \text{Geometric}(p)$.  

Now, by definition,
$$E[X] = \sum_{k \geq 1} k p (1-p)^{k-1}.$$
Let $f(x) = x + x^2 + x^3 + \cdots$. From this we know that $f'(x) = 1 + 2x + 3x^2 + \cdots$, which means that $E[X] = pf'(1-p)$.  
We can now find $f'(x)$ as
$$f'(x) = \left(\frac{1}{1-x} - 1 \right)' = \frac{1}{(1-x)^2}.$$

Substituting, $E[X] = p \frac{1}{p^2} = \frac{1}{p}$.  

For the variance, we have $\text{Var}(X) = E[X^2] - E[X]^2$. We need to find $E[X^2] = \sum_{k \geq 1} k^2 p (1-p)^{k-1}$.  
With $f(x)$ as defined above, $xf'(x) = x + 2x^2 + 3x^3 + \cdots$, from which we get $(xf'(x))' = 1 + 2^2x + 3^2x^2 + \cdots$. Therefore $E[X^2] = p(xf'(x))' \mid_{x=1-p}$.  

Now $xf'(x) = \frac{x}{(1-x)^2}$. Therefore,
$$(xf'(x))' = \frac{(1-x)^2 + 2x(1-x)}{(1-x)^4} = \frac{1+x}{(1-x)^3}.$$

This gives us
$$E[X^2] = p \left(\frac{2-p}{p^3} \right) = \frac{2-p}{p^2},$$

from which we can conclude that
$$\text{Var}(X) = \frac{2-p}{p^2} - \frac{1}{p^2} = \frac{1-p}{p^2}.$$

# Problem 7
We have $X \sim \text{Poisson}(\alpha)$, $Y \sim \text{Poisson}(\beta)$ and $Z = X + Y$. We wish to find $Z$'s PMF.  

$$\begin{split}
P(Z=n) &= \sum_{k=1}^{n-1} P(X=k) P(Y=n-k) \\
&= \sum_{k=1}^{n-1} \left(\frac{e^{-\alpha} \alpha^k}{k!} \right) \left(\frac{e^{-\beta}\beta^{n-k}}{(n-k)!} \right) \\
&= e^{-(\alpha+ \beta)} \sum_{k=1}^{n-1} \begin{pmatrix} n \\ k \end{pmatrix} \alpha^k \beta^{n-k} \\
&= \frac{e^{-(\alpha + \beta)} (\alpha + \beta)^n}{n!}. \end{split}$$

Thus, we have $Z \sim \text{Poisson}(\alpha + \beta)$.

# Problem 8
Each paper receives a grade from the set $G = \{A, A-, B, B-, C, C-\}$ with equal probability. Let $X$ be the number of papers handed in before each possible grade is received at least once.  

Consider $P(X = n)$. For $X$ to have the value $n$, the first $n-1$ papers must have grades from some subset of $G$ containing only 5 grades; and the $n^\text{th}$ paper must have the remaining grade. There are 6 ways to pick the grade that the $n^\text{th}$ paper is the first to get; the probability of each paper from the first $n-1$ receiving a grade from the other five is $\frac56$; and the probability that the last paper gets the chosen grade is $\frac16$. Therefore,
$$P(X =n) = 6 \cdot \left(\frac{5}{6}\right)^{n-1} \left(\frac16 \right).$$

Hence $X = 6Y$ where $Y \sim \text{Geometric}(\frac16)$. We wish to find $E[X] = 6E[Y]$.  

It has been shown (Problem 6) that the expected value of a variable having a geometric distribution with parameter $p$ is $\frac{1}{p}$. Therefore $E[Y] = \frac{1}{\frac16} = 6$, which gives us $E[X] = 36$.

# Problem 9
A mosquito lands with probability 0.5 each second. Therefore the number of mosquitoes (say $X$) landing per second follows a Poisson distribution, *i.e.*, $X \sim \text{Poisson}(0.5)$.  

Further, the expected value for a Poisson distribution is $\lambda = 0.5$ itself. Therefore an average of $E[X] = 0.5$ mosquitoes lands every second, which implies that one mosquito lands every $\frac{1}{E[X]} = 2$ seconds. Thus the expected time between two mosquito *landings* is 2 seconds.  

It is given that with a probability of 0.2, the mosquito (having landed) will bite. This means that one-fifth of the mosquito landings result in a bite, which tells us that the expected interval between two mosquito bites is 10 seconds.  

We have shown that the time between successive bites $T = \frac{5}{X}$. Therefore, to find $\text{Var}(X)$, we must calculate $\text{Var}\left(\frac{5}{X} \right)$; but the variance of the reciprocal of a random variabl has no relation to its own variance. Therefore the variance of the time cannot be found.

# Problem 10
$X$ has mean $\mu_X$ and variance $\sigma_X^2$.  
$Y$ has mean $\mu_Y$ and variance $\sigma_Y^2$.  

Since $Z = 3X + 4Y$, we know that $E[Z] = \mu_Z = 3E[X] + 4E[Y]$ (linearity of expectation).  
Substituting, $\mu_Z = 3\mu_X + 4\mu_Y$.  

To find $\text{Var}(Z)$, we can use the fact that $X$ and $Y$ are independent, allowing us to directly sum their variances. This gives us $\text{Var}(Z) = \text{Var}(3X) + \text{Var}(4Y)$, from which we get $\text{Var}(Z) = 9\text{Var}(X) + 16\text{Var}(Y)$.  
Again, we can immediately substitute to get $\sigma_Z^2 = 9\sigma_X^2 + 16\sigma_Y^2$.
