+++
title = 'A question on the cardinality of a $\sigma$-field'
date = 2025-12-01
draft = false
+++

Let $\gamma$ be a any class of subsets of $\Omega$ such that $\phi,\Omega\in\gamma$. We define $\gamma_0=\gamma$, and for any ordinal $\alpha>0$, inductively: 

$$\gamma_\alpha = (\cup\set{\gamma_\beta:\beta<\alpha})'$$

Where $D'$ is the class of all countable unions of differences of sets in $D$.

__What is $D'$?__
Assume $D = \set{\Omega, \phi}$ The difference $\Omega-\phi$ is the set $\Omega$.
Assume $A\in{D}$ than $D'$ contain $\phi-A$, $\Omega-A=A^c$, $\phi-A=\phi$, etc.

We than define $\frak{U}=\cup\set{\gamma_{\alpha}:\alpha<\beta}$

Where $\beta$ is the first uncountable ordinal.

We define $\mathcal{F}$ to be the smallest $\sigma$-field on $\gamma$.

__Question:__ if the cardinality of $\gamma$ is equal to the cardinality of the reals $2^{\aleph_0}$ (In the book it is assigned the letter **c**), prove that the cardinality of $\mathcal{F}$ is also $2^{\aleph_0}$.

__An initial line of reasoning:__

Since $\mathcal{F}$ is the smallest $\sigma$-field which contains $\gamma$, it also contains $\gamma_{\alpha}$ for every $\alpha$. It follows that $\frak{U}\subset\mathcal{F}$. If $\frak{U}$ is itself a $\sigma$-field (containing $\gamma$ as well) it would then imply that $\frak{U}=\mathcal{F}$.

Thus, it would suffice to *estimate the cardinality of $\frak{U}$* (since it, naively, has simpler structure) to conclude the cardinality of $\mathcal{F}$!
