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

But than - $A=\Omega-A^c\in{D'}$!

We than define $\frak{U}=\cup\set{\gamma_{\alpha}:\alpha<\beta}$

Where $\beta$ is the first uncountable ordinal.

We define $\mathcal{F}$ to be the smallest $\sigma$-field on $\gamma$.

__Question:__ if the cardinality of $\gamma$ is equal to the cardinality of the reals $2^{\aleph_0}$ (In the book it is assigned the letter **c**), prove that the cardinality of $\mathcal{F}$ is also $2^{\aleph_0}$.

__An initial line of reasoning:__

Since $\mathcal{F}$ is the smallest $\sigma$-field which contains $\gamma$, it also contains $\gamma_{\alpha}$ for every $\alpha$. It follows that $\frak{U}\subset\mathcal{F}$. If $\frak{U}$ is itself a $\sigma$-field on $\gamma$ (that is, containing $\gamma$) it would then imply from minimality that $\frak{U}=\mathcal{F}$.

Thus, it would suffice to *estimate the cardinality of $\frak{U}$* (since it, naively, has simpler structure) to conclude the cardinality of $\mathcal{F}$!

__Proof:__

Let $A_1,A_2,..\in{\frak{U}}$ than by definition, for each $i$ we have $A_i\in\gamma_{\alpha_i}$ for some $\alpha_i$. We define $\alpha=\sup_i{\alpha_i}$. Since $\gamma_0\subset\gamma_1\subset..$ we have $A_i\in{\alpha}$ for all $i$ implying (From our previous observations) $\cup_iA_i\in{\gamma_{\alpha+1}}$.

Let $A\in{\frak{U}}$ than $A\in\gamma_{\alpha}$ for some $\alpha$ implying $A^c\in\gamma_{\alpha+1}$

As we know the upper bound for the cardinality of a $\sigma$-field on a given collection of sets with cardinality $c$ is $2^c$. This bound is attained when the field contains **all** countable unions of intersections of the sets or complements in the collection.

If $|\gamma_{\alpha}| \leq 2^{\aleph_0}$ for all $\alpha$. Since this is true for all $\alpha<\beta$ were $\beta$ is the first uncountable ordinal than we have $|\cup^{\beta}_\alpha\gamma_{\alpha}|\leq\beta*c=c$.

If $D$ has cardinality $c$ than $|D'|\leq c^{\aleph_0}={2^{\aleph_0}}^{\aleph_0}=2^{\aleph_0}=c$. Implying $|\frak{U}|=c$. $\square$


