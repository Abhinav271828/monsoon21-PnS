---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | Assignment 4
author: Abhinav S Menon
---

# Problem 1
We have a random variable $X \sim \text{Exponential}(\lambda)$, *i.e.*, $f_X(x) = \lambda e^{-\lambda x}$.  

## Part 1
We want to know the probability $P(X > 5)$. We can find it as follows:
$$\begin{split}
P(X > 5) &= 1 - P(X \leq 5) \\
&= 1 - F_X(5). \end{split}$$

Given $f_X(x)$, we know that $F_X(x) = 1 - e^{-\lambda x}$. This gives us
$$\begin{split}
P(X > 5) &= 1 - F_X(5) \\
&= 1 - (1 - e^{-\lambda \cdot 5}) \\
&= e^{-5\lambda}. \end{split}$$

## Part 2
Now, we want to calculate $P(X > 15 \mid X > 10)$.  

We know that the exponential distribution has no memory, *i.e.*, that
$$P(X > x + a \mid X > x) = P(X > a).$$
Letting $x = 10, a = 5$ in this expression, we can see that $P(X > 15 \mid x > 10) = P(X > 5)$. We have found above that this is $e^{-5\lambda}$.

# Problem 2
We have the PDF
$$f_R(r) = \begin{cases}
2e^{-2r} & r \geq 0 \\
0 & \text{otherwise}, \end{cases}$$
*i.e.*, $R \sim \text{Exponential}(2)$.  
We are given that the variable $T$ is defined as $T = \frac1R$. We need to find its PDF.  

Now, the function $g(x) = \frac1x$ is monotonically decreasing on the interval $[0, \infty)$. Thus we need to find the PDF of $T = g(R)$.  

We can apply the usual rule for transformations, *i.e.*, for variables $X, Y$, such that $Y = g(X)$,
$$f_Y(y) = \begin{cases}
\frac{f_X(x_1)}{|g'(x_1)|} & g(x_1) = y \\
0 & \text{otherwise}, \end{cases}$$

which means that
$$f_T(t) = \begin{cases}
\frac{f_R(r)}{|-\frac1{r^2}|} & \frac1r = t \\
0 & \text{otherwise}. \end{cases}$$

Since $\frac1r = t$, we know that $r = \frac1t$. Then we can substitute this along with $f_R$ in the expression for $f_T$ to find
$$f_T(t) = \begin{cases}
\frac{2e^{-\frac2t}}{t^2} & t > 0 \\
0 & \text{otherwise}. \end{cases}$$

# Problem 3

# Problem 4
We have a CRV $X \sim \text{Exponential}(\lambda)$, *i.e.*, $f_X(x) = \lambda e^{-\lambda x}$ for all $x \geq 0$.

## Part 1
We want to find the CDF $F_X$ of $X$. We can do this straightforwardly using integration:
$$\begin{split}
F_X(x) &= \int_{-\infty}^x f_X(u) du \\
&= \int_0^x \lambda e^{-\lambda u} du \\
&= \lambda \cdot \frac{1}{-\lambda} [e^{-\lambda u}]_{u=0}^{u = x} \\
&= - [e^{-\lambda x} - e^{-\lambda \cdot 0}] \\
&= 1 - e^{-\lambda x}. \end{split}$$

## Part 2
We are given that $Y = X^2$. We wish to find $F_Y$ and $f_Y$.  

Let $g(x) = x^2$. We can see that $g$ is then a monotonically increasing function on $[0, \infty)$, and so we can apply the usual transformation. Thus, for $F_Y$, we have
$$\begin{split}
F_Y(y) &= P(Y \leq y) \\
&= P(X^2 \leq y) \\
&= P(X \leq \sqrt{y}) \\
&= F_X(\sqrt{y}) \\
&= 1 - e^{-\lambda \sqrt{y}}. \end{split}$$

We can find $f_Y$ from this as
$$\begin{split}
f_Y(y) &= \frac{d}{dy}F_Y(y) \\
&= 0 - \left(e^{-\lambda \sqrt{y}} \frac{d}{dy}(-\sqrt{y}) \right) \\
&= \frac{e^{-\lambda \sqrt{y}}}{2\sqrt{y}}. \end{split}$$
for all $y \geq 0$, and 0 otherwise.

# Problem 5
We are given a CRV $X$ with range $[0,3]$ and PDF $f_X(x) = kx^2$. We are also given a CRV $Y = X^3$.

## Part 1
We want to find $k$ and the CDF $F_X$ of $X$.  

To find $k$, we recall that $\int_{-\infty}^{\infty}f_X(u)du = 1$. We have
$$\begin{split}
\int_{-\infty}^{\infty} f_X(u)du &= \int_0^3 ku^2 du \\
&= k \left[ \frac{u^3}{3} \right]_0^3 \\
&= 9k. \end{split}$$

Since this is equal to 1, we have $k = \frac19$.  

For $F_X$, we can again integrate to find
$$\begin{split}
F_X(x) &= \int_{-\infty}^x f_X(u)du \\
&= \int_0^3 \frac19 u^2 du \\
&= \left[ \frac19 \frac{u^3}{3} \right]_0^x \\
&= \frac{x^3}{27}. \end{split}$$

## Part 2
We wish to find the expected value $E[Y]$.  

We can find it as
$$\begin{split}
E[Y] &= \int_0^3 x^3 f_X(x)dx \\
&= \int_0^3 \frac{x^5}9 \\
&= \left[ \frac{x^6}{54} \right]_0^3 \\
&= \frac{729}{54} = 13.5 \end{split}$$

## Part 3
We need to find the variance $\text{Var}(Y)$.  

We can use the identity $\text{Var}(Y) = E[Y^2] - E[Y]^2$. We have found $E[Y]$ already; we need to find $E[Y^2]$. We can do so by noting that $Y^2 = X^6$ and following the same method as above, to get
$$\begin{split}
E[Y^2] &= \int_0^3 x^6 f_X(x)dx \\
&= \int_0^3 \frac{x^8}9 \\
&= \left[ \frac{x^9}{81} \right]_0^3 \\
&= 3^{9-4} = 243. \end{split}$$

Therefore, $\text{Var}(Y) = 243 - (13.5)^2 = 60.75$.

## Part 4
We wish to find the PDF $f_Y$ of $Y$. We can proceed using the transformation as before:

$$f_Y(y) = \begin{cases}
\frac{f_X(x_1)}{3x_1^2} & x_1^3 = y \\
0 & \text{otherwise}. \end{cases}$$

We can apply this method as the cube function is strictly increasing in $[0, 3]$.  

Note that the range of $Y$ is $[0, 27]$. Now we can substitute $x_1 = \sqrt[3]{y}$ and $f_X$ to find the distribution of $Y$ as
$$f_Y(y) = \begin{cases}
\frac{\sqrt[3]{y^2}}{9}\frac1{3\sqrt[3]{y^2}} & 0 \leq y \leq 27 \\
0 & \text{otherwise}, \end{cases}$$

and cancel to get
$$f_Y(y) = \begin{cases}
\frac1{27} & 0 \leq y \leq 27 \\
0 & \text{otherwise}. \end{cases}$$

# Problem 6
$X$ is given to be the result of rolling a 4-sided die, and $Y$ that of a 6-sided die. $Z$ is the average of $X$ and $Y$. Thus we have
$$f_X(x) = \begin{cases}
\frac14 & x \in \{1,2,3,4\} \\
0 & \text{otherwise}. \end{cases}$$
$$f_Y(y) = \begin{cases}
\frac16 & x \in \{1,2,3,4,5,6\} \\
0 & \text{otherwise}. \end{cases}$$

Clearly, $Z \in \{1,1.5,2,2.5,3,3.5,4,4.5,5\}$. We can find its distribution on a case-by-case basis:
$$\begin{split}
f_Z(1) &= f_X(1) f_Y(1) = \frac1{24} \\
f_Z(1.5) &= f_X(1) f_Y(2) + f_X(2) f_Y(1) = \frac1{12} \\
f_Z(2) &= f_X(1) f_Y(3) + f_X(2) f_Y(2) + f_X(3) f_Y(1) = \frac18 \\
f_Z(2.5) &= f_X(1) f_Y(4) + f_X(2) f_Y(3) + f_X(3) f_Y(2) + f_X(4) f_Y(1) = \frac16 \\
f_Z(3) &= f_X(1) f_Y(5) + f_X(2) f_Y(4) + f_X(3) f_Y(3) + f_X(4) f_Y(2) = \frac16 \\
f_Z(3.5) &= f_X(1) f_Y(6) + f_X(2) f_Y(5) + f_X(3) f_Y(4) + f_X(4) f_Y(3) = \frac16 \\
f_Z(4) &= f_X(2) f_Y(6) + f_X(3) f_Y(5) + f_X(4) f_Y(4) = \frac18 \\
f_Z(4.5) &= f_X(3) f_Y(6) + f_X(4) f_Y(5) = \frac1{12} \\
f_Z(5) &= f_X(4) f_Y(6) = \frac1{24} \end{split}$$

## Part 1
We want to find $\sigma_X, \sigma_Y, \sigma_Z$. First, we will find the variances of the variables.  

For $X$, we know that
$$E[X] = \frac14 \sum_{i=1}^4 i = 2.5,$$
and
$$E[X^2] = \frac14 \sum_{i=1}^4 i^2 = \frac{15}{2}.$$
Therefore,
$$\begin{split}
\sigma_X^2 &= \frac{15}{2} - \frac{25}{4} \\
&= \frac{5}{4} = 1.25 \end{split}$$

Therefore $\sigma_X = \sqrt{1.25} \approx 1.118$.

For $Y$, we know that
$$E[Y] = \frac16 \sum_{i=1}^6 i = 3.5,$$
and
$$E[Y^2] = \frac16 \sum_{i=1}^6 i^2 = \frac{91}{6}$$
Therefore,
$$\begin{split}
\sigma_Y^2 &= \frac{91}{6} - \frac{49}{4} \\
&= \frac{35}{12} \approx 2.917 \end{split}$$

Therefore $\sigma_Y = \sqrt{2.917} \approx 1.708$.

For $Z$, we know that
$$E[Z] = E\left[\frac12(X+Y)\right] = \frac12(E[X] + E[Y]) = 3,$$
and
$$\begin{split}
E[Z^2] &= E\left[\frac14(X+Y)^2\right] = \frac14(E[X^2] + E[Y^2] + 2E[XY]) \\
&= \frac14 \left( \frac{45 + 91 + 105}{6} \right) \\
&= \frac{241}{24}. \end{split}$$
Therefore,
$$\begin{split}
\sigma_Z^2 &= \frac{241}{24} - 9 \\
&\approx 1.0417 \end{split}$$

Therefore $\sigma_Z = \sqrt{1.0417} \approx 1.02$.

## Part 2
Let $W$ be a random variable indicating the amount won. We can find its probability distribution as follows.

$$\begin{split}
f_W(2) &= f_X(1)P(Y < 1) = 0 \\
f_W(4) &= f_X(2)P(Y < 2) = \frac14 \cdot \frac16 = \frac1{24} \\
f_W(6) &= f_X(3)P(Y < 3) = \frac14 \cdot \frac26 = \frac1{12} \\
f_W(8) &= f_X(4)P(Y < 4) = \frac14 \cdot \frac36 = \frac18 \\
f_W(-1) &= \frac34. \end{split}$$

Therefore,
$$\begin{split}
E[W] &= (2)(0) + \frac{4}{24} + \frac{6}{12} + \frac88 + (-1)\left(\frac34\right) \\
&= \frac{11}{12}. \end{split}$$

Hence, after playing 60 games, we have an expected winning of $60E[W] = 55$ dollars.

# Problem 7
We are given
$$f_X(x) = \begin{cases}
x+ \frac12 & 0 \leq x \leq 1 \\
0 & \text{otherwise}. \end{cases}$$

We wish to find $E[X^n]$ for any $n \in \mathbb{N}$. We can do so by integrating.
$$\begin{split}
E[X^n] &= \int_0^1 x^nf_X(x) dx \\
&= \int_0^1 x^n \left(x + \frac12 \right) dx \\
&= \int_0^1 \left( x^{n+1} + \frac12 x^n\right) dx \\
&= \left[\frac{x^{n+2}}{n+2} + \frac12 \frac{x^{n+1}}{n+1}\right]_0^1 \\
&= \frac{3n+4}{(n+1)(n+2)}. \end{split}$$

# Problem 8
We have a CRV $X$ with PDF
$$f_X(x) = \begin{cases}
x^2 \left( 2x + \frac32 \right) & 0 < x \leq 1 \\
0 & \text{otherwise}. \end{cases}$$
We are given that
$$Y = \frac2X + 3$$
and we need to find $\text{Var}(Y)$.  

We can see that $g(x) = \frac2x + 3$ is strictly decreasing in the domain $(0,1]$. Thus, we can apply the transformation, using $g'(x) = -\frac2{x^2}$.
$$f_Y(y) = \begin{cases}
\frac{f_X(x_1)}{|-\frac{2}{x_1^2}|} & \frac2{x_1} + 3 = y \\
0 & \text{otherwise}. \end{cases}$$

Given $g$, we see that if $g(x_1) = y$, then $x_1 = \frac2{y-3}$. Thus, for $y \in [5, \infty)$, we have
$$\begin{split}
f_Y(y) &= x_1^2 \left( 2x_1 + \frac32 \right) \cdot \frac{x_1^2}{2} \\
&= \frac12 \left( \frac2{y-3} \right)^4 \left(\frac4{y-3} + \frac32 \right) \\
&= \frac{32}{(y-3)^5} + \frac{12}{(y-3)^4}. \end{split}$$

We now need to find $E[Y]$ and $E[Y^2]$. For $E[Y]$,
$$\begin{split}
E[Y] &= \int_5^\infty \left[\frac{32y}{(y-3)^5} + \frac{12y}{(y-3)^4} \right] dy \\
&= \int_5^\infty \left[ 32 \left\{\frac{y-3}{(y-3)^5} \right\} + \frac{96}{(y-3)^5} + 12 \left\{\frac{y-3}{(y-3)^4} \right\} + \frac{36}{(y-3)^4} \right]dy  \\
&= \int_2^\infty \left( \frac{96}{x^5} + \frac{68}{x^4} + \frac{12}{x^3} \right)dx \\
&= \frac{96}{-4} \left[\frac1{x^5}\right]_2^\infty + \frac{68}{-3}\left[ \frac1{x^3} \right]_2^\infty + \frac{12}{-2} \left[ \frac1{x^2}\right]_2^\infty \\
&= (-24)\left(-\frac1{16}\right) + \left(-\frac{68}{3}\right)\left(-\frac18\right) + (-6)\left(-\frac14\right) \\
&= \frac32 + \frac{17}6 + \frac32 = \frac{35}{6}. \end{split}$$

For $E[Y^2]$,
$$\begin{split}
E[Y^2] &= \int_5^\infty \left[\frac{32y^2}{(y-3)^5} + \frac{12y^2}{(y-3)^4} \right] dy \\
&= I_1 + I_2, \end{split}$$
where
$$\begin{split}
I_1 &= \int_5^\infty \frac{32y^2}{(y-3)^5}dy \\
&= \int_5^\infty \left[ 32\frac{(y-3)^2}{(y-3)^5} - \frac{32\cdot 9}{(y-3)^5} + \frac{32 \cdot 6y}{(y-3)^5} \right] dy \\
&= \int_5^\infty \left[ \frac{32}{(y-3)^2} - \frac{288}{(y-3)^5} + 192 \left\{ \frac{y-3}{(y-3)^5} \right\} + \frac{192 \cdot 3}{(y-3)^5} \right] dy, \end{split}$$
and
$$\begin{split}
I_2 &= \int_5^\infty \frac{12y^2}{(y-3)^4}dy \\
&= \int_5^\infty \left[ 12\frac{(y-3)^2}{(y-3)^4} - \frac{12\cdot 9}{(y-3)^4} + \frac{12 \cdot 6y}{(y-3)^4} \right] dy \\
&= \int_5^\infty \left[\frac{12}{(y-3)^2} - \frac{108}{(y-3)^4} + 72 \left\{\frac{y-3}{(y-3)^4}\right\} + \frac{72 \cdot 3}{(y-3)^4} \right] dy. \end{split}$$

Thus, we have
$$\begin{split}
E[Y^2] &= I_1 + I_2 \\
&= \int_5^\infty \left[ \frac{12}{(y-3)^2} + \frac{32+72}{(y-3)^3} + \frac{192+216-108}{(y-3)^4} + \frac{576-288}{(y-3)^5} \right] dy \\
&= \int_2^\infty \left( \frac{12}{x^2} + \frac{104}{x^3} + \frac{300}{x^4} + \frac{288}{x^5} \right) dx \\
&= \frac{12}{-1}\left[-\frac1x\right]_2^\infty + \frac{104}{-2}\left[-\frac1{x^2}\right]_2^\infty + \frac{300}{-3}\left[-\frac1{x^3}\right]_2^\infty + \frac{288}{-4}\left[\frac1{x^4}\right]_2^\infty \\
&= (-12)\left(-\frac12\right) + (-52)\left(-\frac14\right) + (-100)\left(-\frac18\right) + (-72)\left(-\frac1{16}\right) \\
&= 6 + 13 + \frac{25}{2} + \frac92 = 36. \end{split}$$

Now we can find $\text{Var}(Y)$ as
$$\begin{split}
\text{Var}(Y) &= E[Y^2] - E[Y] \\
&= 36 - \left(\frac{35}{6}\right)^2 \\
&= 6^2 - \left(6 - \frac16 \right)^2 = \left(\frac16\right)\left(\frac{71}{6}\right) = \frac{71}{36}. \end{split}$$
