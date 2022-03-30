---
layout: post
title: "A three-line derivation of the prime number theorem"
categories: math
---
With $\pi(n)$ the number of primes less than $$n$$, the prime number theorem says that as $$n$$ grows large,

$$ \pi(n) = (1 + o(1)) \int_{2} ^n \frac{dt}{\log(t)}  = (1+o(1)) \frac{n}{\log(n)}.$$

In other words, the "probability" that a large number $$n$$ is prime is roughly $$1/\log(n)$$.

Here's a three-line probabilistic argument that would allow you to guess the PNT had you not seen it before:

Let $$\omega(n)$$ be the prime density function, i.e. the "probability" that a large number close to $$n$$ is prime. Computing it directly, note that $$n$$ is not divisible by a prime $p$ with probability $$(1- 1/p)$$, so that 

$$\omega(n) = \prod_{p < n} (1 - \frac{1}{p}).$$
