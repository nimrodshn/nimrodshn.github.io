+++
title = '$\sigma$-fields and Measures'
date = 2025-11-10T08:49:31+02:00
draft = false
+++

### $\sigma$-fields:

The section begins with the definition of a sigma field (algebra) $F$:

__Definition__: A sigma field is a collection of subsets of a set $\Omega$ such that the following hold:

1. $\Omega \in F$.
2. if $A \in F$, so is $A^C \in F$.
3. For any countable collection of sets $\{A_i\}_{i=0}^\infty$ in $F$ their union  is in $F$ as well.

### Observations:
1. The empty set $\phi$ is also in F - since $\phi = \Omega^c \in F$.
2. Finite intersections are also in F - Using De Morgan, we may write -
$(A^C \cup B^C)^C=A\cap B$
3. Using the same reasoning so is countable intersections.


### Measures:

__Definition__: A measure $\mu$ is a *non-negative countably additive* set-function defined on a $\sigma$-field $F$ of a set $\Omega$:

$$
\mu: F \rightarrow \Bbb{R}.
$$

Countably additive in the sense that if $A_1,...,A_n$ are *disjoint* subsets of $F$ than:

$$
\mu(\bigcup_i{A_i}) = \Sigma_i\mu(A_i)
$$

If $\mu(\Omega)=1$ we call $\mu$ a probability measure.

### A note about Ash's $\sigma$-field vs field comment in the book.
Here Ash makes a rather peculiar decision to make the distinction between a field and a $\sigma$-field since if
$F$ contains no countable unions - it makes no sense to talk about countable additivity.
I assume that this allows him to make a generalization as a field can also be a $\sigma$-field if it contains countable unions
but the latter may not be the case.

According to Ash; if a measure is countably additive it is also finite bc one can simply take a collection such as - 

$$
A_1, A_2,...,A_k,\phi,\phi,\phi...
$$

And due to countable addativity we may also deduce finite additivity.

### Observations

For any countable additive set funcion the following holds -
1. $\mu(\phi) = 0$. Indeed, take and set $A$ in $F$ (At the very least $F$ contains $\Omega$ and $\phi$) and write - 
$$
\mu(A)= \mu(A\cup\phi) = \mu(A)+\mu(\phi).
$$

Here there is a very important assumption that there exists a set A on which $\mu(A) < \infty$

2. $\mu(A\cup{}B) = \mu(A)+\mu(B) - \mu(A\cap{}B)$ 

**Proof:** Take any two sets $A,B \in{F}$, than by additivity -

$$
\mu(A) = \mu(A-B) + \mu(A\cap{B}) \\
\mu(B) = \mu(B-A) + \mu(A\cap{B})
$$

Summing the two together - 
$$
\mu(A) +\mu(B) = \mu(A-B) + \mu(B-A) + 2\mu(A\cap{B}) = \\ 
[\mu(A-B) + \mu(B-A) + \mu(A\cap{B})] + \mu(A\cap{B}) = \\
\mu(A\cup{B}) + \mu(A\cap{B})
$$


3. If $A \subset B$, than - $\mu(B) = \mu(A) + \mu(B-A)$. (By additivity).

4. Assume $\mu$ is nonegative (countable or finite) additive. The following is called "union bound" in probability - $\mu(\cup_i{A_i}) \leq \Sigma_i \mu(A_i)$.

**Proof**:
$$
\mu(\cup_i{A_i}) = \mu(\cup_i (A_i \cap (A_1^c \cap ... \cap A_{i-1}^c))) = \Sigma_i \mu((A_i \cap (A_1^c \cap ... \cap A_{i-1}^c))) \leq \Sigma_i \mu(A_i)
$$

The second equality is due to the fact that the elemnts in the union are disjoint.

**A second proof for the finite case**: Take any $A,B\in{F}$, than -  
$$
\mu(A\cup{B}) \leq \mu(A\cup{B}) + \mu(A\cap{B}) = \mu(A) + \mu(B)
$$

By induction, assume the statement is correct up to some $n-1$, we prove -

$$
\mu(\cup_{i=1}^n{A_i}) = \mu(\cup_{i=1}^{n-1}{A_i}\cup{A_n}) \leq \mu(\cup_{i=1}^{n-1}{A_i}) + \mu(A_n) \leq \Sigma_{i=1}^{n-1} \mu(A_i) + \mu(A_n) = \Sigma_{i=1}^{n} \mu(A_i)
$$

Here we had used the induction hypothesis in both the inner inequalities.

Equality is given when the sets are disjoint due to countable additivity.

**Important note:** What is the importance of the nonegativity assumption in 4? 
Indeed even the base case may fall short as we can imagine a case were $\mu(A\cap{B})$ is negative and thus the right hand side may be smaller than the left hand side. For example; Lets take two sets $A, B$ such that the following holds - 
$$
\mu(A-B) = \mu(B-A) = 5 \\\
\mu(A\cap{B}) = -6
$$

By 2 we have - 
$$
\mu(A) = \mu(B) = 1 \\\
\mu(A\cup{B}) = \mu(A) + \mu(B) - \mu(A\cap{B}) = -1-1+6=4 
$$
While - 
$$
\mu(A) + \mu(B) = -1-1 = -2 
$$

5. Let $A_1, A_2,... \rightarrow A$ be an increasing collection and \mu be a measure, than $\lim_i \mu(A_i) \rightarrow \mu(A)$.

**Proof**:

Here again we need to be careful - what if, for some $i$, $\mu(A_i) = \infty$. By property 3, for any $k\geq{}i$ we have $\mu(A_k) = \infty$ and (from property 3 again) we have $\mu(A) = \infty$ and the statement holds.

Can we say something about the statement if we only know $\mu(A) = \infty$? I am uncertain.

For the case $\mu(A_i)<\infty$ for all $i$ - Indeed - 

$$
\mu(A) = \mu(\bigcup_i^{\infty}A_i) =  \mu(\bigcup_i^{\infty}(A_i - A_{i-1})) =  \sum_i^\infty \mu(A_i-A_i-1)  =\sum_i^\infty \mu(A_i) - \mu(A_{i-1}) = \\
\mu(A_1) + \mu(A_2) - \mu(A_1) + ... = \lim_{i\rightarrow\infty}\mu(A_i)
$$

6. Let $A_1, A_2,... \rightarrow A$ be a decreasing collection and $\mu$ be a measure, than $\lim_i \mu(A_i) \rightarrow \mu(A)$.

Here is a **wrong proof** - 
Since $A_1,..$ is decreasing than $A_1^c,..$ is increasing, thus - 

$$
\mu(\Omega) - \mu(A) = \mu(\Omega - A) = \lim_i\mu(\Omega-A_i) = \mu(\Omega) - \lim_i\mu(A_i^c)
$$

The statment follows. But the issue here is that $\mu(\Omega)$ may be $\infty$!

Thus, take in the previous proof $A_1$ instead of $\Omega$ (As $A_1-A_i$ is an increasing collection) assumed to be the largest finite measured set and the proof is fixed! (This is the proof given in the book).


