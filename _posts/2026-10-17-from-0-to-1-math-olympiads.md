---
title: "From 0 to 1: How to Break Into High School Math Olympiads"
date: 2026-10-17 19:55:00 +0300
categories: [advice]
tags: [math-olympiads, beginners, problem-solving]
description: "In my first article, I share my journey through math olympiads and give advice to complete beginners who want to get started."
math: true
---

#### Disclaimer

This is my story and my advice, not a magic formula or a one-size-fits-all pathway.

## Who am I?

Hey there! My name is Mathis, and I am from Burkina Faso. I am a former olympiad medalist. I have participated in several competitions and won a number of prizes, including:

- A silver medal at PAMO 2025.
- First prize in both the national mathematics olympiad and the national physics olympiad in 2026.
- A Silver Honour, placing in the top 2%, at the 2025 International Youth Math Contest, along with a national first prize.
- First prize at the 2025 national mathematics olympiad.

And guess what? Back in 2024, I did not even know what math olympiads were.

I grew up in an environment where mathematics was often undervalued and math olympiads were rare. For example, at the time I started, my country did not participate in the IMO. I am sharing this to show that it is possible to start with almost no knowledge of olympiads and make real progress.

## How did I discover math olympiads?

I discovered math olympiads through the club at my high school, the National Scientific High School of Bobo-Dioulasso. It was a revelation.

The format was pretty cool. Most olympiads consist of a set number of problems that contestants must solve within a limited amount of time. For example, in competitions such as the PAMO and IMO, contestants solve three problems in four and a half hours per day, over two days. The exact format can vary from one competition to another.

The main olympiad subjects are number theory, algebra, geometry, and combinatorics.

## My advice for getting started in math olympiads

### Start with the basics

Begin with the basic topics: number theory, geometry, combinatorics, and algebra.

I remember wasting a lot of time working on advanced problems when I was a beginner. You cannot solve problems well without the right background knowledge and tools. Build your foundations, practise regularly, read books, and do some research. When you study a solution, try to understand why each step works instead of memorizing it.

### Train yourself to think creatively

When you try an approach and it is not working, try another one. Do not stay fixed on a single idea. Draw a diagram, look for a pattern, test a small case, or rewrite the problem in a different way. Try as many reasonable approaches as you can, and learn from the ones that do not work.

### Accept that the journey can be demanding

It is not always simple. Try, fail, and try again. That is part of the path. You need to practise regularly and be patient with yourself.

During serious preparation, I recommend aiming for a few focused hours a day when your schedule allows it. I sometimes recommend three or four hours, or even more, but a sustainable routine is better than studying so much that you burn out. Start with an amount you can keep up consistently.

### Approach problems by trying special cases

What better way to explain this than with an example?

If a problem is about an abstract integer $n$, try small values such as $n=1,2,3,\ldots$. You could also test something more specific, such as $n \equiv 1 \pmod 3$. Why not? It can also be worth splitting the problem into cases.

Consider the sequence $(u_n)_{n\geq 1}$ defined by $u_1=2$ and

$$
u_{n+1}=\frac{1+u_n}{1-u_n}\qquad\text{for every }n\geq 1.
$$

Determine the exact value of $u_{2026}$.

Let's calculate the first few terms:

$$
\begin{aligned}
u_1 &= 2,\\
u_2 &= \frac{1+2}{1-2}=-3,\\
u_3 &= \frac{1+(-3)}{1-(-3)}=-\frac{1}{2},\\
u_4 &= \frac{1+(-1/2)}{1-(-1/2)}=\frac{1}{3},\\
u_5 &= \frac{1+(1/3)}{1-(1/3)}=2.
\end{aligned}
$$

The first five terms reveal a cycle. Since $u_5=u_1=2$, the same calculations repeat:

$$
u_6=u_2=-3,\qquad u_7=u_3=-\frac{1}{2},\qquad u_8=u_4=\frac{1}{3},\qquad u_9=u_5=2,\ldots
$$

Therefore, the sequence has period $4$. Its terms follow this pattern:

$$
u_n=
\begin{cases}
2 & \text{if } n\equiv 1\pmod 4,\\
-3 & \text{if } n\equiv 2\pmod 4,\\
-\frac{1}{2} & \text{if } n\equiv 3\pmod 4,\\
\frac{1}{3} & \text{if } n\equiv 0\pmod 4.
\end{cases}
$$

To find $u_{2026}$, divide the index by the period:

$$
2026=4\cdot 506+2.
$$

Thus, $2026\equiv 2\pmod 4$, so $u_{2026}$ has the same value as $u_2$:

$$
\boxed{u_{2026}=u_2=-3}.
$$

Trying a few special cases helped us spot the cycle and solve for a very large index. Of course, spotting a pattern is not the same as proving it. Once you have a good conjecture, look for a reason that proves it must continue.

## Some useful resources

Here are a few resources to explore:

- [Evan Chen's olympiad materials](https://web.evanchen.cc/olympiad.html), with handouts and advice on a range of topics.
- [OTIS, or Olympiad Training for Individual Study](https://web.evanchen.cc/otis.html), with materials organized into different difficulty tracks.
- [The OTIS Excerpts](https://web.evanchen.cc/excerpts.html), a collection of olympiad problems and solutions.
- [104 Number Theory Problems](https://link.springer.com/book/10.1007/978-0-8176-4561-8), by Titu Andreescu, Dorin Andrica, and Zuming Feng.
- [102 Combinatorial Problems](https://link.springer.com/book/10.1007/978-0-8176-8222-4), by Titu Andreescu and Zuming Feng.

Titu Andreescu is one of my favorite authors in math olympiad literature. Some of his books can be challenging, so if you are just starting out, take your time and focus on understanding the ideas behind the solutions.

## Final thoughts

You do not need to have known about math olympiads since childhood to begin. I discovered them in 2024, when I was starting from zero. Build your foundations, stay curious, and keep practising. Progress takes time, but every problem you work through can teach you something new.
