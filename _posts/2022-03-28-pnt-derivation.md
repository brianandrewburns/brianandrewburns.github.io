---
layout: post
title: "A three-line derivation of the prime number theorem"
categories: math
---
With $$\pi(n)$$ the number of primes less than $$n$$, the prime number theorem says that as $$n$$ grows large,

$$ \pi(n) = (1 + o(1)) \int_{2} ^n \frac{dt}{\log(t)}  = (1+o(1)) \frac{n}{\log(n)}.$$

In other words, the "probability" that a large number $$n$$ is prime is roughly $$1/\log(n)$$.

Here's a three-line probabilistic argument that would allow you to guess the PNT had you not seen it before:

Let $$\omega(n)$$ be the "probability" that a large number $$n$$ is prime. Since the probability of $$n$$ escaping divisibility by some prime $$p$$ is $$(1-1/p)$$, the chance that it is prime is given by
$$\begin{aligned}
  \omega(n) &= \prod_{p < n} (1- 1/p) \\
  \implies \log \omega(n) &= \sum_{k=2}^n \log(1-1/k) \Xi_{\text{$$k$$ is prime}} 
\end{aligned}$$

But since $$\omega$$ gives the probability that a number is prime, for any sufficiently smooth $f$ and any set $E$ consisting of large numbers, we should have
$$\sum_{k \in E} f(x)\Xi_{\text{$$k$$ is prime}} = (1+o(1)) \int_E f(x) d\omega.$$
In particular, with $$f(x) = \log(1-1/x)$$ above, we have
$$\begin{aligned}
  \log \omega(n) &= (1+o(1))\int_{2}^n \log(1- 1/x) \omega(x) dx \\
  \implies \omega'(n)/\omega(n)^2 &= (1+o(1))\log(1- 1/x) \\
  \implies -1/\omega(n) &= (1+o(1)) \int_{2}^n \log(1-1/x) dx \\
   &= (1+o(1)) \int_{2}^n (-1/x + O(1/x^2)) dx \\
   &= -(1+o(1))\log(n),
\end{aligned}$$
i.e.
$$ \omega(n) = (1+o(1)) \frac{1}{\log(n)}$$
as desired.

