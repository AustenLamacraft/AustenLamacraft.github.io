---
layout: post
title: Order to Chaos Transition in Deep Nets
categories: machine learning
author: Austen Lamacraft
---

In this post I want to discuss a thread of work starting with {% cite Poole:2016aa %}. This paper makes the case that the expressive power of deep nets can be attributed to chaotic evolution as we pass from inputs to outputs. The view of deep nets dynamical systems has long been popular in the context of RNNs, along with the notion that computation is optimal at 'the edge of chaos' - see {% cite Bertschinger:2004aa %} for some of the history of this idea. Perhaps the main differences from earlier works on Boolean networks {% cite Derrida:1986aa %} {% cite Derrida:1986ab %} and spin glass models {% cite Derrida:1987aa %} are

1. The inputs and outputs in the 'modern era' are real, rather than discrete.

2. The dynamics in these earlier works was autonomous (time invariant), whereas each layer of a network has its own weights and biases, giving time-dependent dynamics.

3.

<figure>
<img src="/images/blog/order-chaos.png" width="400" />
<figcaption>Figure from {% cite Pennington:2018aa %} </figcaption>
</figure>






References
----------

{% bibliography --cited %}
