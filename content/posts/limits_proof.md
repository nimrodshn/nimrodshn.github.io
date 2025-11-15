+++
title = 'A proof for $\mu(\lim_{n\rightarrow\infty}{A})=\lim_{n\rightarrow\infty}{\mu(A_n)}$'
date = 2025-11-30
draft = false
+++

__Definition__:
If $\liminf A_n = \limsup A_n = A^{\star}$ we define $\lim_n A_n = A^{\star}$.

__Problem__: Assume $\mu$ a finite measure and $A_n\in\mathcal{F}, \forall{n}\in\mathbb{N}$.
Show $\mu(\lim_{n\rightarrow\infty}{A})=\lim_{n\rightarrow\infty}{\mu(A_n)}$

__An initial idea__:

My initial idea was to use the following properties of $\liminf A_n$ and $\limsup A_n$:

1. $w\in\liminf{A_n} \iff \exist{n}$ such that $\forall{k\geq{n}}$ we have $w\in{A_k}$.

2. $w\in\limsup{A_n} \iff$ there are infinitely many $n$ such that $w\in{A_n}$.

However these propoerties do not reveal a connection between $\mu(\limsup{A_n})=\mu(\liminf{A_n})=\mu(A^{\star})$ and $\mu(A_n)$.

__Proof__: (Idea thanks to GPT)

Define the following: 
$$
C_k=\cup_{i=k}^{\infty}A_i \\\
B_k=\cap_{i=k}^{\infty}A_i
$$
We note the following -
1. $C_k$ is a decreasing collection ${C_{k+1}}\subset..\subset{C_1}$.
2. $B_k$ is an increasing collection $B_1\subset..\subset{B_k}$.

These imply the following statements - 

$$
\bigcap_{k=1}^{n}C_k = C_n \\
\bigcup_{k=1}^{n}B_k = B_n
$$

Now we are ready for a set of inequlities which will conclude the proof:

$$
\mu(\bigcup_{k=1}^{n}B_k) = \mu(B_k)\leq\mu(A_k)
$$ 

And in particular, since $B_k\subset{A_k}$ for all $i\geq{k}$ we have by monotinicity -

$$
\mu(\bigcup_{k=1}^{n}B_k) = \mu(B_n)\leq\inf_{i\geq{n}}\mu(A_i)\leq\sup_{1\leq{k}\leq{n}}\inf_{i\geq{k}}\mu(A_i)
$$

Using similar reasoning for $C_k$, we have - 
$$
\inf_{1\leq{k}\leq{n}}\sup_{i\geq{k}}\mu(A_i)\leq\sup_{i\geq{n}}\mu(A_i) \leq \mu(C_n)=\mu(\bigcap_{k=1}^{n}C_k)
$$ 

We put everything togther to obtain - 

$$
\mu(\bigcup_{k=1}^{n}B_k)\leq\sup_{1\leq{k}\leq{n}}\inf_{i\geq{k}}\mu(A_i)\leq\inf_{1\leq{k}\leq{n}}\sup_{i\geq{k}}\mu(A_i)\leq\mu(C_n)=\mu(\bigcap_{k=1}^{n}C_k)
$$

We let $n\rightarrow\infty$ and obtain -

$$
\mu(\liminf{A_n})\leq\liminf\mu(A_n)\leq\limsup\mu(A_n)\leq\mu(\limsup{A_n})
$$

But since - $\liminf{A_n}=\limsup{A_n}=\lim_{n\rightarrow\infty}{A_n}$, by our initial assumption. The two ends of the above inequality are equal and we get the desired result -

$$
\mu(\lim_{n\rightarrow\infty}{A_n})=\lim_{n\rightarrow\infty}\mu(A_n)
$$

$\square$.

__Alterantive proofs?__

I was struggling for a while to find alternative proofs before eventually abandoning the idea.. I will see if I find other alternative proofs relying on the basic properties of $\liminf$ and $\limsup$ if possible as this one was highly non trivial for me.
