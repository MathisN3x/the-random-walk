---
title: "The Dirac Delta Function and Brownian Motion: A Friendly Introduction to Diffusion"
date: 2026-10-28 17:30:00 +0300
categories: [mathematics]
tags: [statistical-physics, dirac-delta, brownian-motion]
description: "An accessible introduction to the Dirac delta distribution, Brownian motion, and the diffusion equation."
math: true
---

Hey, welcome to The Random Walk! A blog dedicated to explaining fun facts in math and AI. Today we’ll talk about statistical physics. I know, it's not one of our topics, but it’s my blog; I do what I want :) But more seriously, it's fascinating, and you’ll see there is more math than you think. So let’ssssssss gooooo

***WARNING/DISCLAIMER: This article makes several compromises and may at times lack strict mathematical rigor. This is an intentional choice for the sake of popularization and accessibility. A subsequent, more rigorous article with complete formal notations will be provided later.***

### The Dirac Delta function

Okay, okay, okay. I know, the Dirac delta function isn’t exactly a function; it's a distribution. But for notation purposes, we’ll keep calling it a function.

We can picture the Dirac delta distribution informally as:

$$
\delta(x) \approx
\begin{cases}
+\infty, & x=0,\\
0, & x\ne 0.
\end{cases}
$$


such that for any function $f$ continuous in $x_0$ , we have $\int_{-\infty}^{+\infty} \delta(x-x_0) f(x) \ dx=f(x_0)$

(The Dirac delta is not an ordinary function; it is a distribution. It is often pictured informally as an infinitely narrow spike at $x=0$, with total area $1$.)


Fun Fact :
The delta function is named after physicist [Paul Dirac](https://en.wikipedia.org/wiki/Paul_Dirac), and has been applied routinely in physics and engineering to model point masses and concentrated loads. It is called the delta function because it is a continuous analogue of the [Kronecker delta](https://en.wikipedia.org/wiki/Kronecker_delta) function. The mathematical rigor of the delta function was disputed until [Laurent Schwartz](https://en.wikipedia.org/wiki/Laurent_Schwartz) developed the theory of distributions, where it is defined as a linear form acting on functions. ( source: [Wikipedia](https://en.wikipedia.org/wiki/Dirac_delta_function) )

Some properties of $\delta$ (proofs in appendix):

1.  $\delta(x)=\delta(-x)$
2.  $\delta(ax)=\frac{1}{\vert a \vert} \delta(x), a \ne 0$
3.  $\delta(x)=\frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{-i \omega x} \ d \omega$ (Fourier transform)

### Brownian motion

The simplest way to think about Brownian motion is to imagine a giant beach ball being bounced around in a crowded stadium. Even if you can’t see the thousands of fans hitting it from all sides, you can see the beach ball violently jerking, darting, and wandering randomly around the stadium.

In mathematics, standard Brownian motion $(W_t)_{t \geq 0}$ starts at zero, has continuous paths, and has independent Gaussian increments: for $0 \leq s < t$, $$W_t - W_s \sim \mathcal{N}(0, t - s)$$ It has the Markov property: once its current position is known, the distribution of its future depends on the past only through that current position. That is the precise sense in which the ideal process is often described as “memoryless”. Its motion is random, but not structureless: the model specifies probability laws for its increments.

In the real world, Brownian motion is the ceaseless, random, zigzagging movement of microscopic particles suspended in a fluid (a liquid or a gas), caused by the relentless bombardment of invisible atoms and molecules crashing into them.

![](https://www.image2url.com/r2/default/images/1792909561983-39ab90fb-f5bc-4d0d-9669-49b8cdbf6e0a.png)
Fig. 1: A visualization of a two-dimensional random walk generated using Python (NumPy and Matplotlib). The trajectory simulates a stochastic process with 2,000 sequential steps derived from a normal distribution.

One can wonder: what is the link between the Dirac delta function and Brownian motion?

Let’s imagine a particle moving along a 1D axis. Its position is given by $x(t),t\ge0$
Let's assume that it's at $x=0$ at $t=0$

Let $p(x, t)_{(t>0)}$ be the probability density function of our particle. At $t=0$, the particle is perfectly localized at the origin. This localized state is represented by setting our initial condition to a Dirac delta distribution:

$$p(x,0)=\delta (x)$$


![](https://www.image2url.com/r2/default/images/1792932607742-ca07fcd9-ae36-447a-b8fb-816bc7caa9b1.png)
 Fig.2: *Schematic representation of the Dirac delta distribution centered at $x=0$. The spike symbolizes a unit point mass concentrated at the origin; it is not the graph of an ordinary function with a literal infinite value.*
 
The movement of a cloud of Brownian particles (or the shifting probability of a single particle) is governed by the Diffusion Equation (This equation also appears as Fick’s second law for a concentration field when combined with conservation of mass and Fick’s law for the flux, $J = -D \frac{\partial c} {\partial x}$, assuming $D$ is constant. Here we are using the same equation for a probability density):

$$ \frac{\partial p}{\partial t}= D.\frac{\partial^2 p}{\partial x^2}$$
This equation calculates how the probability density $p$ changes over time $t$ relative to how it curves across space $x$, scaled by a diffusion constant $D$.

When we solve this equation using the Dirac delta function as our initial condition: $p(x, 0)$ = $\delta(x)$, this gives us a beautifully precise solution for $t>0$:

$$ p(x,t)=\frac{1}{\sqrt{4\pi Dt }}\cdot e^{\frac{-x^2}{4Dt}} $$
This is a Gaussian density with mean zero and variance $2Dt$, often written $\mathcal{N}(0, 2Dt)$. It integrates to one for every $t > 0$. The formula is the fundamental solution (or heat kernel) of the diffusion equation on the real line. As $t$ tends to zero from above, these Gaussian probability measures converge to the point mass $\delta_0$; the formula itself is defined for $t > 0$, not by substituting $t = 0$.

For standard Brownian motion $W_t$, the variance is $t$, and its density solves the same equation with diffusion coefficient $D = \frac{1}{2}$. More generally, the diffusion described here can be written as $X_t = \sqrt{2D}W_t$, which explains the variance $2Dt$.

![](https://www.image2url.com/r2/default/images/1792934804711-1b4d65cf-6898-4225-95bf-90dda5c7c11b.png)

Fig.3: The density $p(x,t) = (4\pi Dt)^{-1/2} \exp[-x^2 / (4Dt)]$ for $D = 1$ at $t = 0.5$, $t = 1$, and $t = 2$.

## Appendix

Proof of 1: $\delta(x)=\delta(-x)$

As delta is a distribution, let us consider the following integral:

$$
\int_{-\infty}^{+\infty} \delta(-x)f(x)
$$
by performing a variable change $u=-x,$ we have $du=-dx$
and the integral becomes :
$$
\int_{+\infty}^{- \infty} -\delta(u)f(-u) \ du=\int_{-\infty}^{+ \infty} \delta(u)f(-u) \ du=f(-0)=f(0)= \int_{-\infty}^{+\infty} \delta(x)f(x) \ dx
$$
so we conclude that the distributions $\delta(x)=\delta(-x)$ are identical.

2. Proof of 2: $\delta(ax)= \frac{1}{\vert a \vert} \delta(x), a \ne 0$

Let's consider the following integral :
$$
I=\int_{-\infty}^{+\infty} \delta(ax)f(x) \ dx
$$
by doing the following variable change : $u=ax$, we have $du=a.dx$

1st case: $a<0$

Thus we have $I=\int_{+\infty}^{-\infty} \frac{1}{a}\delta(u)f(\frac{u}{a}) \ du=\frac{-1}{a} \int_{-\infty}^{+\infty} \delta(u)f(\frac{u}{a})\ du=\frac{-f(0)}{a}$

2nd case: $a>0$

Thus we have $I=\frac{1}{a} \int_{-\infty}^{+\infty} \delta(u)f(\frac{u}{a})\ du=\frac{f(0)}{a}$  
so $I=\frac{f(0)}{|a|}$ . Since $\int_{-\infty}^{+\infty} \frac{1}{|a|} \delta(x) f(x) \ dx = \frac{f(0)}{|a|}$, both sides have the same action on any test function $f(x)$. Therefore, the distributions are identical.

Thus we can conclude that $\delta(ax)=\frac{1}{\vert a \vert} \delta(x)$

3. Proof of 3: $\delta(x)=\frac{1}{2\pi} \int_{-\infty}^ {+\infty} e^{-i \omega x} \ d \omega$

our distribution is centered at 0 $(x_0=0)$, so we calculate the Fourier transform of $\delta$ using the property $$\int_{-\infty}^{+\infty} \delta(x) f(x) \ dx=f(0)$$

we obtain $F(\omega) = \mathcal{F}(\delta(x)) = \frac{1}{2\pi} \int_{-\infty}^{\infty} \delta(x)e^{i\omega x} dx = \frac{1}{2\pi}.$
By definition of the Fourier transform ( assuming that the integral exists ), $$F(\omega) = \frac{1}{2\pi} \int_{-\infty}^{\infty} f(x)e^{i\omega x} dx $$ and the associated inverse Fourier transform, $f(x) = \int_{-\infty}^{\infty} F(\omega)e^{-i\omega x} d\omega.$
by doing the following substituion in the inverse Fourier transform $$ f(x)=\delta(x), F(\omega)=\frac{1}{2\pi}$$

we obtain $$\delta(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} e^{-i\omega x} , d\omega$$

## References & Further Reading

If you want to dive deeper into distribution theory and the mathematics of random walks, check out these excellent resources:

-   [Wikipedia]  [Dirac Delta Function](https://en.wikipedia.org/wiki/Dirac_delta_function#) - For a complete historical and mathematical overview of $\delta(x)$.
-   [Wikipedia]  [Laurent Schwartz](https://en.wikipedia.org/wiki/Laurent_Schwartz) - Discover the life and legacy of the French mathematician who rigorous-ized distributions.
-   [Book] Strichartz, R. (1994). A Guide to Distribution Theory and Fourier Transforms. CRC Press. - A fantastic, highly recommended textbook if you want to understand test functions and generalized functions without getting lost in overly dense measure theory.
-   [Random Walk Simulator](https://web-apps.thecoatlessprofessor.com/randomness/random-walk-simulator.html) - To explore how changing the underlying probability distribution alters the path of the particle.
-   [# Delta Function- Wolfram MathWorld](https://mathworld.wolfram.com/DeltaFunction.html)
