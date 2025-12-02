 +++
title = 'Yet another limit pf from Ash 😅'
date = 2025-12-02
draft = false
+++

__Problem:__
Suppose $\mu$ is a probability measure (or nonegative countably additive set function) and the following holds - $A_i\uparrow A$ and $A_i'\uparrow A'$ such that $A\subset{A'}$ than we have - $\lim_i\mu(A_i)\leq\lim_i\mu(A_i')$.

__The simplest proof possible:__
As we know from previous statements on countably additive set functions - $$\lim_i\mu(A_i)=\mu(\lim_i{A_i})=\mu(A)\leq\mu(A')=\mu(\lim_i{A_i'})=\lim_i\mu(A_i')$$

__A first attempt of a proof using elementary analysis:__
Naively, we may try to attack this question as purely a question on sequences of real numbers $\set{\mu(A_i)}_i$ and $\set{\mu(A_i')}_i$?

We already know that for {de/in}creasing collection of sets $\lim_i{\mu(A_i)}=\mu(\lim{A_i})$.
Since both collections are *increasing* we may assume there exists an $m_0,n_0$ such that for $m\geq{m_0},n\geq{n_0}$ we have - 
$$
\mu(A')-\mu(A_m')<\frac{\epsilon}{2} \\\\
\mu(A)-\mu(A_n)<\frac{\epsilon}{2}
$$

We remove the second inequality from the first to obtain - 

$$
\mu(A_n)-\mu(A_m')<\mu(A)-\mu(A')\implies\mu(A_n)<\mu(A_m')-\mu(A'-A)
$$

But since $\mu$ is nonegative we have - $\mu(A_n)\leq\mu(A_m)$. We take the limit $m,n\rightarrow\infty$  to conclude the proof. $\square$

__What is wrong with this proof?__
The proof above assumes that for the given indexes $n>n_0, m>m_0$ we have, $\mu(A_n)\leq\mu(A_m')$. Yet that might not be the case b/c it might be that $A_m'\subset{A_n}$ for a subset or all of these indexes which will break the proof. It may happen that the measure of the series $A_n$ increases very quickly wrt to the measure of the collection $A_m'$ so we cannot simply "substract" the second inequality from the first as described.

__A proof using properties of sets:__

From monotinicity, we may write - 

$$
\mu(A_n')\geq\mu(A_n'\cap{A_m})\xrightarrow[n\rightarrow\infty]{}\lim_{n\rightarrow\infty}\mu(A_n')\geq\mu(A'\cap{}A_m)=\mu(A_m)
$$

The second inequality is due to $A\subset{A'}$ and $\set{A_i}_i$ an increasing collection. We take the $m\rightarrow\infty$ to conclude the proof.$\square$



