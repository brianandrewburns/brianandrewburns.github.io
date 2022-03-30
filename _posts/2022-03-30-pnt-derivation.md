---
layout: post
title: "A three-line derivation of the prime number theorem"
categories: math
---
With $$\pi(n)$$ the number of primes less than $$n$$, the [prime number theorem](https://en.wikipedia.org/wiki/Prime_number_theorem) says that as $$n$$ grows large,

$$ \pi(n) \approx \int_{2} ^n \frac{dt}{\log(t)}  \approx \frac{n}{\log(n)}.$$

In other words, the "probability" that a large number $$n$$ is prime is roughly $$1/\log(n)$$.

Here's a three-line probabilistic argument that would allow you to guess the PNT had you not seen it before:

Let $$\omega(n)$$ be the "probability" that a large number $$n$$ is prime, and $$P$$ the set of primes. Since the chance that $$n$$ escapes divisibility by some prime $$p$$ is $$(1-1/p)$$, its chance of being prime is

$$\begin{align*}
  \omega(n) &= \prod_{p < n} (1- 1/p) \\
  \implies \log \omega(n) &= \sum_{k=2}^n \log(1-1/k) \unicode{x1D7D9}_{k \in P}. 
\end{align*}$$

But since $$\omega$$ encodes the probabily of $$n$$ being prime, we can approximate the above sum over prime indices with an expectation over $$\mathbb{P}_\omega$$:

  $$\log \omega(n) = (1+o(1)) \int_{2}^n \log(1- 1/x) \omega(x) dx $$

We can then take derivatives to solve for $$\omega(n)$$:

$$\begin{align*}
  \omega'(n)/\omega(n)^2 &= (1+o(1))\log(1- 1/x) \\
  \implies -1/\omega(n) &= (1+o(1)) \int_{2}^n \log(1-1/x) dx \\
   &= (1+o(1)) \int_{2}^n (-1/x + O(1/x^2)) dx \\
   &= -(1+o(1))\log(n) \\
   \implies \omega(n) &= (1+o(1)) \frac{1}{\log(n)}
\end{align*}$$

as desired.

