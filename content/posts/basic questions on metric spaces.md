+++
title = 'Basic properties of Metric Spaces (from Mathematical Analsys 2 by Zorich)'
date = 2025-12-24
draft = false
+++

### Proposition 1:
Let $(X,d)$ be a metric space.
a. The union $\bigcup_{\alpha\in{A}}G_{\alpha}$ of the sets in any system $\set{G_{\alpha}, \alpha\in{A}}$ of sets that are open in $X$ is and open set in $X$.
b. The intersection $\bigcap_{i=1}^nG_i$ of any *finite* number  of sets that are open in $X$ is an open set in $X$.
c. The intesection $\bigcap_{\alpha\in{A}}F_{\alpha}$ of the sets in any system $\set{F_{\alpha}, \alpha\in{A}}$ of sets $F_{\alpha}$ that are closed in $X$ is a closed set in $X$.
d. The union $\bigcup_{i=1}^nF_i$ of any *finite* number of sets that are closed in $X$ is a closed set in $X$.

__Proof:__
a. Let $G=\bigcup_{\alpha\in{A}}G_{\alpha}$ be a union of open sets in $X$. Let $x\in{G}$ be an arbitrary point, than by definition there exists some $\alpha_0\in{A}$ such that $x\in{G_{\alpha_0}}$, an open set. thus there exists $r\in{\mathbb{R}}$ such that $B(x,r)\subset{G_{\alpha_0}}$ implying $B(x,r)\subset{G}$. $\square$

b. Let $G=\bigcap_{i=1}^n{G_i}$ be the intersection of a finite number of sets that are open in $X$. Let $x\in{G}$ be an arbitrary point. Than, there exists $r_1,..,r_n$ such that $\forall{i}\in{[n]}$ we have $B(x,r_i)\subset{G_i}$. Thus, we may take $r=\min_ir_i$ and deduce $B(x,r)\subset{G_i},$ for all ${i}\in{[n]}$ implying $B(x,r)\subset{G}$. $\square$

c. Let $F=\bigcap_{\alpha\in{A}}F_{\alpha}$ be an intersection of closed sets in $X$. By De-Morgan, we compute $F^c$: 
$$
F^c = (\bigcap_{\alpha\in{A}}F_{\alpha})^c=\bigcup_{\alpha\in{A}}F_{\alpha}^c
$$
An open set by a. $\square$

d. Again using, De-Morgan, we compute $F^c$ - 
$$
F^c=(\bigcup_{i=1}^nF_i)^c=\bigcap_{i=1}^nF_i^c
$$

An open set by b. $\square$


### Proposition 2:
Let $(X,d)$ be a metric space. A set $F\subset{X}$ is closed in $X$ $\iff$ $F$ contains all of its limit points. That is, $F=\bar{F}$.

__Proof:__
$\implies$ Let $F$ be closed in $X$. Assume by contradiction there exists a limit point $x$ such that $x\notin{F}$. Implying any neighborhood of $x$ contains points in $F$. Thus, for any $\epsilon>0$ the ball $B(x,\epsilon)$ contains point in $F$ and thus $F^c$ is not open. Contradiction.

$\impliedby$ Assume $F=\bar{F}$. By contradiction, assume $F$ is not closed in $X$. Thus, there exists a point in $x\in{F^c}$ such that any neighborhood of $x$ contains pts in $F$ (Otherwise, $F^c$ is open implying $F$ is closed.) But then $x$ is a limit point of $F$ in $F^c$. Contradiction.


### Questions:

a. Is it true that the union of any family of closed sets is a closed set?

Answer: Take the the following a countable collection of closed sets: $A_i=[\frac{1}{i},1]$. Than, $\cup_i^{\infty}A_i=(0,1]$ is not closed since it does not contain $0$.

b. Is every boundry point of a set a limit point of a set?

Answer: Yes, otherwise, let $x$ be a boundry point of a set $E$ and assume by contradiction $x$ is not a limit point of $E$ than, by definition, there exists a neighborhood of $x$, $O(x)$ such that $O(x)\cap{E}$ is finite, implying there exists $\set{r_1,..,r_n}$ such that $x_i\in{B(x,r_i)}\cap{E}$. We take $r=\min_i\set{\frac{1}{2}r_i}$ implying that $B(x,r)\cap{E}=\phi$. But $B(x,r)\subset{O(x)}$. Contradiction.

**Correction**: This is **incorrect**. We may take an **isolated point**. Here is a counter-example -
$$
E = \set{0}
$$
Than every neighborhood of 0 contains both $E$ and $E^c$ yet ite is not a limit point since any neighborhood of 0 contains only itself in $E$ meaning its is not a limit point.