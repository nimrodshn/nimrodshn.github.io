+++
title = '$\sigma$-fields and Measures'
date = 2025-11-10T08:49:31+02:00
draft = false
+++

The section begins with the definition of a sigma field (algebra) $\textit{F}$:

A sigma field is a collection of subsets of a set $\Omega$ such that the following hold:

1. $\Omega \in \textit{F}$.
2. if $A \in \textit{F}$, so is $A^C \in \textit{F}$.
3. For any countable collection of sets $\{A_i\}_{i=0}^\infty$ in $\textit{F}$ their union  is in $\textit{F}$ as well.

### Some observations:
1. The empty set $\phi$ is also in F - since $\phi = \Omega^c \in \textit{F}$.
2. Finite intersections are also in F - Using De Morgan, we may write -
$(A^C \cup B^C)^C=A\cap B$
3. Using the same reasoning so is countable intersections.
