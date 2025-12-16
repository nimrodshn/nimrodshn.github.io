+++
title = 'A question on the expansion of rational numbers in a q-ary number system'
date = 2025-12-22
draft = false
+++

__Question:__
A number $x\in{\mathbb{R}}$ has a periodic expansion (in any number system) $\iff$ $x$ is rational.

__Proof:__

$\impliedby$ Assume $x$ is rational, i.e. there are $m,n\in{\mathbb{Z}}$ such that, $x=\frac{m}{n}$ and $n\neq0$. Than, by way of long division we obtain deteministically the decimals of its expansion in some $q$-ary number system:

We define $r_0=m$. We define the following recursive relation obtained from the "long division" process - 

$d_i=\lfloor\frac{r_iq}{n}\rfloor$

$r_i = qr_{i-1}-d_in$

If at any step we obtain $r_i=0$ than the expansion therminates. Otherwise, the set of remainders obtained from dividing by $n$ is finite and equals $\set{0,...,n-1}$, Implying, by the "Pigeonhole Principle", that after at most $n-1$ steps the digits of the expansion would *repeat*, thus, obtaining a scaled remainder, implying, that the expansion is periodic.

__A first attempty at the harder direction:__

$\implies$ Let $x\in{\mathbb{R}}$ with periodic expansion. Assume by contradiction that $x$ is **irrational**.

By the recursive relation we have previously defined there exists $i<j$ such that $r_j = r_i=r$

Than, we can "unroll" the recursive relation to obtain - 

$$
r = q^{j-i}r-c
$$

for some rational constant $c$ implying - $r=\frac{c}{q^{j-i}-1}$.

Implying we can write the following - 
$$
x = q^0d_0+...+q^{-i}d_i+r = q^0d_0+...+q^{-i}d_i+\frac{c}{q^{j-i}-1}\in{\mathbb{Q}}
$$

Contradiction.

__Note:__ GPT claims the above pf is wrong as it **relies** on the recursive relation which in turn relies on the fact the $x$ is rational which breaks the pf.

__A second attempt at the harder direction:__

$\implies$ Let $x\in{\mathbb{R}}$ have a periodic base-$q$ expansion. Assume by contradiction that $x$ is **irrational**.

That is, there exists digits $d_1,..,d_j$ and indicies $i<j$ such that -
$$
x=0.d_1..d_{i-1}\overline{d_i..d_j}
$$
Hence -
$$
x = \sum_{k=1}^{i-1}q^{-k}d_k+\sum_{t=0}^{\infty}q^{-t(j-i)}\sum_{l=i}^{j}q^{-l}d_l=\\\\
\sum_{k=1}^{i-1}q^{-k}d_k+\sum_{t=0}^{\infty}(\frac{1}{q^{j-i}})^{t}\sum_{l=i}^{j}q^{-l}d_l=\\\\
\sum_{k=1}^{i-1}q^{-k}d_k+\frac{1}{1-\frac{1}{q^{j-i}}}\sum_{l=i}^{j}q^{-l}d_l
$$

Each term in the above sum is a finite sum of rationals and thus the entire sum is rational, implying $x$ is rational. Contradiction. $\square$.