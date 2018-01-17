---
layout: post
title: Instabilities in Mean Field Variational Bayes
categories: machine learning
author: Austen Lamacraft
---

This post is based on [Andrea Montanari's talk](https://www.newton.ac.uk/seminar/20180116090009451) at the Newton Institute today.

## A toy problem: $\mathbb{Z}_2$ Synchronization

This is described in {% cite Javanmard:2016aa %}. From the measurements of the $n \times n$ matrix $Y_{ij}$

$$
Y = \frac{\lambda}{n}zz^T + \frac{W}{\sqrt{n}},
$$

we want to recover the $z_{i}\in\{\pm 1\}$, $i=1,\ldots n$, where $W_{i>j}\in \mathcal{N}(0,1)$, with $W_{ij}=W_{ji}$ and $W_{ii}=0$. Note that the $z_i$ are only determined up to an overall sign. $\lambda$ measures the signal-to-noise: for smaller $\lambda$ it is harder to estimate the $z_i$. In the large $n$ limit there is a phase transition at $\lambda=1$. As we'll see, this corresponds to the ordering of an Ising model with couplings $Y_{ij}$, with $\lambda$ playing the role of inverse temperature.

## Variational Inference

The $z_i$ are Bernoulli variables, which we parameterize in terms of their expectation

$$
p(z_i=\pm 1;m_i) = \frac{1\pm m_i}{2}.
$$

The idea behind variational inference is to maximize the __evidence lower bound__ (ELBO, or negative of the __variational free energy__)

$$
\mathcal{L}(Y,m,q) \equiv \mathbb{E}_{z\sim q}\log p(z,Y;m) + H(q)
$$

for some proposed $q(z|Y)$. The unconstrained maximum occurs for $q(z|Y)=p(z|Y)$, at which
 $\mathcal{L}$ achieves $\log p(Y;m)$, the log probability of the data.

Applied to our problem, we have

$$
p(z,Y;m) = \prod_i p(z_i;m_i) \prod_{i>j} \sqrt{\frac{N}{2\pi}}\exp\left[-\frac{N\left(Y_{ij} - \lambda z_i z_j/n\right)^2}{2}\right].
$$

Computation of $p(Y;m)$ by marginalizing out $z$ is intractable -- it corresponds to computing the partition function of an Ising model with couplings $Y_{ij}$ -- so we propose the mean field distribution

$$
q(z|Y) = \prod_i p(z_i;m_i(Y)).
$$

The entropy is

$$
H(q) = -\sum_i \left[\frac{1 +m_i}{2} \log\left(\frac{1\ +m_i}{2}\right) + \frac{1 +m_i}{2} \log\left(\frac{1\ +m_i}{2}\right)\right],
$$

while

$$
p=
$$



References
----------

{% bibliography --cited %}
