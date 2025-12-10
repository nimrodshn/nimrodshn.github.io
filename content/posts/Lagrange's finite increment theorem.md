+++
title = 'A proof of Rolles Theorem and Lagranges finite increment Theorem'
date = 2025-12-09
draft = false
+++

__Theorem:__
A continous function on a closed interval $[\alpha,\beta]$ attains a maximum or a minimum in the closed interval.

__Proof:__
From the definition of continuity - for any point in $[\alpha,\beta]$ there *exists* a neighborhood such that the function is bounded in that environment.

[Side note: For that reason the function $f(x)=\frac{1}{x}$ is *not* continous on any interval containing 0, since it is unbounded at any environment of the point.]

Thus, we may cover $[\alpha,\beta]$ using a collection of open intervals. Using the Heine-Borel theorem we may extract a finite collection $A_1,..,A_k$ of open intervals covering $[\alpha,\beta]$ such that $f$ is bounded on each interval.

We define $M_i=\sup_{x\in{A_i}}{f(x)}$, the maximal value of $f$ for the interval $A_i$ - this value *exists and is finite* since $f$ is bounded on $A_i$ by definition and $m_i=\inf_{x\in{A_i}}{f(x)}$ similiarly.

Thus, $f$ is bounded on $[\alpha,\beta]$ - $m=\min_i{m_i} \leq f(x)\leq \max_i{M_i}=M$.

Assume $f$ does not attains the values $m$ or $M$. Indeed if $f(x)$ is continous so is $f(x)-M$ thus $f$ attains values arbitrarily close to $M$ in some interval (Otherwise, $M$ is not a supremum of some interval) implying $\frac{1}{f(x)-M}$ is unbounded on $[\alpha,\beta]$, contradicting what was just proved.

Thus there exists $x_M\in{[\alpha,\beta]}$ such that $f(x_M)=M$. Similarly for $m$. $\square$.

__Rolle's Theorem:__
Let $f$ be a continous function on $[\alpha,\beta]$ such that $f(\alpha)=f(\beta)$. Than, there exists $\xi\in(\alpha,\beta)$ such that $f'(\xi)=0$.

__Proof:__
If $f$ is constant on $[\alpha,\beta]$ than $f'(x)=0$ for all $x\in[\alpha,\beta]$.

Otherwise, there exists a maximum $x_M$ and a minimum $x_m$ in $[\alpha,\beta]$ - *at least* one of which is in $(\alpha,\beta)$ [perhaps both] - we mark it as $\xi$. $\square$

In other words - If $f$ represents the displacement of a particle over an interval of time $\beta-\alpha$. Than, in order to return to its starting point $f(\alpha)=f(\beta)$ the partical must have *stopped* (at least once) to return on its tracks! Implying - $v(\xi)=f'(\xi)=0$ for some $\xi\in(\alpha,\beta)$.


__Lagrange's finite increment Theorem:__
Let $f$ be continous function on a closed interval $[\alpha,\beta]$. Than there exists $\xi\in[\alpha,\beta]$ such that $$f(\beta)-f(\alpha)=f'(\xi)(\beta-\alpha)$$

In other words, if we regard $f$ as a particles location along a straign line in some time interval, than there exists a point on the line (perhaps more than one) such that the particle attains its average speed over the entire time interval.

__Proof:__
We define the following function - 
$$g(t)=f(t)-\frac{f(\beta)-f(\alpha)}{\beta-\alpha}(t-\alpha)$$

Simply put, $g$ is just $f$ minus the location of a particle with the average speed over time (the straight line between $f(\alpha)$ and $f(\beta)$). But since both our original partical as well as the "avg speed" particle have the same increment, than $g$ must start and finish at the same point!

Indeed $g(\alpha)=g(\beta)=f(\alpha)$. Thus, using Rolle's theorem, we conculde there exists a point $\xi\in{[\alpha,\beta]}$ such that $g'(\xi)=f'(\xi)-\frac{f(\beta)-f(\alpha)}{\beta-\alpha}=0$. $\square$
