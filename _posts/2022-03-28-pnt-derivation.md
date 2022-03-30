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
  \omega(n) &= \prod_{p < n} (1- 1/p)
  \implies \log \omega(n) &= \sum_{k=2}^n \log(1-1/k) \mathbbm{1}_{\text{k is prime}}
\end{aligned}$$

$$\omega(n) = \prod_{p < n} (1 - \frac{1}{p}).$$
