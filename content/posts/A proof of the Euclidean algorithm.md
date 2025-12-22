+++
title = 'A proof of the Euclidean Algorithm'
date = 2025-12-22
draft = false
+++

__The Euclidean Algorithm:__

Let $m,n\in\mathbb{N}$ such that $m>n$. Then we define succesively -

$$
m = q_1n+r_1 \\
n = q_2r_1+r_2 \\
r_1 = q_3r_2+r_3 \\
.. \\
r_k = q_{k+2}r_{k+1} + 0
$$

than $\gcd(m,n)=r_{k+1}$

__Initial (wrong) proof:__
If $\gcd(m,n)=1$ than $m,n$ are foreign (or mutually prime). Otherwise, assume $\gcd(m,n)>1$. Define $r_0=n$ We prove by induction that $r_{i+1}|r_i$.

Base case - If $r_1\nmid{n}$ than we can deduce that $\gcd(m,n)=1$. Contradiction.

Assume the claim is correct up to $i$ and prove the claim for $i+1$:

We write $r_{i-1}=q_{i+1}r_i+r_{i+1}$. Using the same argument as before - if $r_{i+1}\nmid{r_i}$, than by "unrolling" the expression above we may find a constant $C$ such that $Cr_i=n$ implying - 
$$m=q_1n+r_1=Cr_i+r_{i+1}$$.

But than $\gcd(m,n)=1$. Contradiction.

Thus we conclude $r_{i+1}|{r_i}$ for all $i$. Since $m,n$ are finite and at each step the $r_i$ decrease we must reach after a finite number of steps at $r_i=0.$

**The basic idea is correct but the invariant is wrong.**

Why? b/c even for the base case the invariant is too strict! 
Take for example $m=18$ and $n=10$, than - 

$$
18 = 1*10+8
$$

But than $r_1=8\nmid{10}=r_0$ but $\gcd(18,10)=2>1$. Contradiction.

The correct invariant should be $\gcd(r_{i+1},r_i)=\gcd(r_i,r_{i-1})$.

And using the same conclusion as above we should reach a correct proof.

__A second attempt at a proof:__
If $\gcd(m,n)=1$ than $m,n$ are foreign (or mutually prime). Otherwise, assume $\gcd(m,n)>1$. We prove by induction that $\gcd(r_{i+1},r_i)=\gcd(r_i,r_{i-1})$.

Base case - If $\gcd(m,n)\neq\gcd(n,r_1)$ than $\gcd(m,r_1)=1$ implying we have $\gcd(m,n)=1$ by our initial condition of $m=q_1n+r_1$. Contradiction.

We assume the induction invariant is correct up to some $i$ and prove for $r_{i+1}$.

Using the same reasoning as before, if $\gcd(r_{i+1},r_i)\neq\gcd(r_i,r_{i-1})$

Than, using the transitivity of $\gcd$ we have $\gcd(n,r_i)\neq(n,r_{i+1})$

Than using the relation - 

$r_{i-1}=q_{i+1}r_{i}+r_{i+1}$ and plugging back in our equations we find $m=q_1n+Ar_i+Br_{i-1}$ for some constants $A,B$ implying $\gcd(m,n)=1$. Contradiction.

Thus, $\gcd(r_{i+1},r_i)=\gcd(r_i,r_{i-1})$.

Since $m,n$ are finite and at each step the $r_i$ decrease we must reach after a finite number of steps at $r_{i+1}=0.$
