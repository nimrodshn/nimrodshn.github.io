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
\mu: F \rightarrow \mathbb{R}.
$$

Countably additive means that if $A_1,A_2..$ are any finite or countably infinite *disjoint* subsets of $F$ than:

$$
\mu(\bigcup_i{A_i}) = \Sigma_i\mu(A_i)
$$

If $\mu(\Omega)=1$ we call $\mu$ a probability measure.

**Important note**: What is the meaning of **countably** additive in the above definition? 

Take a countable collection of disjoint sets $A_1, A_2, ...$ and a *finitly* additive set function $\mu$ and define $S_n=\bigcup_{i=1}^{n}A_i$ than - 

$$
\lim_{n\rightarrow\infty}\mu(S_n) = \lim_{n\rightarrow\infty}\mu(\bigcup_{i=1}^{n}A_i) = \lim_{n\rightarrow\infty} \sum_{i=0}^n\mu(A_i)
$$

If limit of the partial sums on the right hand side *exists* (Admittedly, it may be $\infty$) and is equal to the measure of the limiting set on the left hand side for *any countable disjoint collection of sets* than we say that the set function is countably additive.

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
\mu(A) = \mu(A-B) + \mu(A\cap{B}) \\\
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
Indeed even the base case in the above proof may fall short as we can imagine a case were $\mu(A\cap{B})$ is negative and thus the right hand side may be smaller than the left hand side. For example; Lets take two sets $A, B$ such that the following holds - 
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

5. Let $A_1, A_2,... \rightarrow A$ be an increasing collection and $\mu$ be a measure, than $\lim_i \mu(A_i) \rightarrow \mu(A)$.

**Proof**:

Here again we need to be careful - what if, for some $i$, $\mu(A_i) = \infty$. By property 3, for any $k\geq{}i$ we have $\mu(A_k) = \infty$ and (from property 3 again) we have $\mu(A) = \infty$ and the statement holds.

Can we say something about the statement if we only knew $\mu(A) = \infty$? I am uncertain.

For the case $\mu(A_i)<\infty$ for all $i$ - Indeed - 

$$
\mu(A) = \mu(\bigcup_i^{\infty}A_i) =  \mu(\bigcup_i^{\infty}(A_i - A_{i-1})) =  \sum_i^\infty \mu(A_i-A_i-1)  =\sum_i^\infty \mu(A_i) - \mu(A_{i-1}) = \\
\mu(A_1) + \mu(A_2) - \mu(A_1) + ... = \lim_{i\rightarrow\infty}\mu(A_i)
$$

6. Let $A_1, A_2,... \rightarrow A$ be a decreasing collection and $\mu$ be a measure, than $\lim_i \mu(A_i) \rightarrow \mu(A)$.

Here is a **wrong proof** - 
Since $A_1,..$ is decreasing $A_1^c,..$ is increasing up to $A^c$, thus - 

$$
\mu(\Omega) - \mu(A) = \mu(\Omega - A) =\mu(A^c) = \\\
\lim_i\mu(A_i^c) = \lim_i\mu(\Omega-A_i) = \mu(\Omega) - \lim_i\mu(A_i)
$$

The statment follows. But the issue here is that $\mu(\Omega)$ may be $\infty$!

Thus, take in the previous proof $A_1$ instead of $\Omega$ (As $A_1-A_i$ is an increasing collection) assumed to be the largest finite measured set and the proof is fixed! (This is the proof given in the book).

### Problems

1. Let $\Omega$ be a countable infinite set and let $F$ consist of all subsets of $\Omega$. Define $\mu(A)=0$ if $A$ is finite and $\mu(A)=\infty$ if $A$ is infinite.
a. Show that $\mu$ is finitely additive but not countably additive.
b. Show that $\Omega$ is the limit of an increasing sequence of sets $A_n$ with $\mu(A_n)=0$ for all $n$ yet $\mu(\Omega)=\infty$

__Answer__:
1.

a. Indeed let $A_1,..,A_k$ be a finite collection of disjoint finite sets - their union must also be finite so we have - 
$$\mu(\bigcup_{i=1}^k{A_i}) = 0 = \sum_{i=1}^k{A_i}$$

Let $A_1,A_2..$ be a countably collection of disjoint finite sets. Define $B_n=\bigcup_{i=0}^nA_i$. Thus - 
$$\mu(\bigcup_{i=1}^{\infty}{A_i})=\lim_{n\rightarrow\infty}\mu(B_n) = \lim_{n\rightarrow\infty}\sum_{i=1}^n\mu(A_i)= \lim_{n\rightarrow\infty}\sum_{i=1}^n{0} = 0 * \infty = 0$$

b. Since $\Omega$ is countably infinite we may build the sequence inductivly - 

We set $A_0=\phi$. For each index $i>0$ we pick randomly an element from - $\omega\in\Omega-A_{i-1}$ and define $A_i=A_{i-1}\cup\{\omega\}$.

We may pick an elemnt in this manner as $\Omega$ is countably infinite.

We note that $|A_k|=k<\infty$ (since at each step we add a single element), implying $\mu(A_k)=0$ for any $k$, however $A_k\rightarrow\Omega$. 

2. Let $\mu$ be a counting measure on $\Omega$ (and infinite set). Show that there exists a sequence of sets $A_n\downarrow\phi$ with $\lim_{n\rightarrow\infty}\mu(A_n)\neq0$

__Answer__:

We define an increasing sequence of sets such as in 1.b - 

We set $A_0=\phi$. For each index $i>0$ we pick randomly an element from - $\omega\in\Omega-A_{i-1}$ and define $A_i=A_{i-1}\cup\{\omega\}$.

We may pick an elemnt in this manner as $\Omega$ is countably infinite.

We than define $B_i=\Omega-A_i$. Implying $B_0=\Omega$ and $B_n\downarrow\phi$ However - 

$$\lim_{n\rightarrow\infty}\mu(B_n)=\lim_{n\rightarrow\infty}\mu(\Omega-A_n)=\lim_{n\rightarrow\infty}\mu(\Omega)-\mu(A_n)=\infty$$

3. Let $\Omega$ be a countably infinite set and let $F$ be a field consisting of all finite subsets of $\Omega$ and their complements. Define the following - 

$$
\mu(A) = \begin{cases}
   0 &\text{A is finite} \\\
   1 &\text{$A^c$ is finite}
\end{cases}
$$

a. Show that $\mu$ is finitely additive but not countably additive on $F$.
b. Show that $\Omega$ is the limit of an increasing sequence of sets $A_n\in{F}$ with $\mu(A_n)=0$ for all $n$, but $\mu(\Omega)=1$.

__Answer__:
a.
We observe the following: 1. If $A^c$ is finite we deduce $A$ is infinite. 2. Take any finite collection of disjoint sets $A_1,...,A_k$ we cannot have two sets $A_i, A_j$ such that both have $\mu(A_i)= \mu(A_j) = 1$ for than both $A_i^c$ and $A_j^c$ are finite but since $A_i$ and $A_j$ are disjoint we have $A_i\in{A_j^c}$ (and vice versa) but $A_i$ is infinite. contradiction.

Now that we have established these key observations, Let $A_1,...,A_k$ be a disjoint collection. There are two cases:
1. $A_1,...,A_k$ contains a set $A_i$ with finite complement $A_i^c$ - In this case, by our first observation $A_i$ is infinite and thus the union $\cup_{i=1}^k{A_i}$ is infinite as well and its compliment is finite and its measure $\mu(\cup_{i=1}^k{A_i})=1=\sum_{i=1}^k{A_i}.$
2. $A_1,...,A_k$ contains no set $A_i$ with finite complement $A_i^c$ than the union is finite and again we have - $\mu(\cup_{i=1}^k{A_i})=0=\sum_{i=1}^k{A_i}$.
We have thus concluded with finite additivity.

b. See 1.b

5. Let $\mu$ be finitely additive nonnegative set function on $F$ prove - 
$$
\mu(\bigcup_{i=1}^{\infty}{A_i})\geq\sum_{i=1}^{\infty}\mu(A_i)
$$

__Answer__:

Assume otherwise, we would than have - 

$$
\mu(\bigcup_{i=1}^{\infty}{A_i})<\sum_{i=1}^{\infty}\mu(A_i) \implies 0 <\sum_{i=1}^{\infty}\mu(A_i) - \mu(\bigcup_{i=1}^{\infty}{A_i}) = \\\
\mu(A_1) + ... + \mu(A_k) + ... - \mu(\bigcup_{i=1}^{\infty}{A_i}) =  \\\
-\mu(\bigcup_{i=1}^{\infty}{A_i} - A_1) + \mu(A_2) + ... + \mu(A_k) +.. = \\\
-\mu(\bigcup_{i=1}^{\infty}{A_i} - A_1 - A_2 - A_3...) = \\\
-\mu(\phi)
$$

Contradiction.

Another proof, relying on similar ideas:
Since $\mu(\bigcup_{i=1}^{n}{A_i})\subset\bigcup_{i=1}^{\infty}{A_i}$ we have -
$$
\sum_{i=1}^{n}\mu(A_i)= \mu(\bigcup_{i=1}^{n}{A_i}) \leq \mu(\bigcup_{i=1}^{\infty}{A_i})
$$

This is true for any $n$. Take the limit $n\rightarrow\infty$.

6. Let $f: \Omega\rightarrow\Omega^\star $ and let $\gamma$ be a collection of subsets of $\Omega^*$. Show $\sigma(f^{-1}(\gamma)) = f^{-1}(\sigma(\gamma))$.

First we show that $f^{-1}(\sigma(\gamma))$ is a $\sigma$-field. 

For if it is - we have $f^{-1}(\gamma)\subset{f^{-1}(\sigma(\gamma))}$ and thus $\sigma(f^{-1}(\gamma)) \subset f^{-1}(\sigma(\gamma)) $.

Indeed, if $A, B\in f^{-1}(\sigma(\gamma))$, meaning there exists $A^\star, B^\star \in\sigma(\gamma)$ s.t. $f^{-1}(A^\star)=A$ and $f^{-1}(B^\star)=B$ we must have $A\cup{B}\in f^{-1}(\sigma(\gamma))$ otherwise -

$$
A\cup{B}=f^{-1}(A^\star)\cup{f^{-1}(B^\star)}=f^{-1}(A^\star\cup{B^\star}) \implies A^\star\cup{B^\star} \notin \sigma(\gamma) 
$$ 

Contradiction. We argue the same for the complements. Thus, we have proved that $f^{-1}(\sigma(\gamma))$ is a $\sigma$-field. (I've waived hands here a little bit but I am sure the reader can appreciate this line of logic can be extended to complements.)

We must now show that $f^{-1}(\sigma(\gamma))\subset\sigma(f^{-1}(\gamma))$. For that we will use the "Good Set" principle as suggested by Ash.

Define the following collection $M$ - 
$$
M = \set{ A \in \sigma(\gamma) | f^{-1}(A) \in \sigma(f^{-1}(\gamma)) }
$$
 
We claim that M is a $\sigma$-field. Indeed if $A^{\star},B^{\star}\in{M}$ by definition we $f^{-1}(A^{\star})=A$, $f^{-1}(B^{\star})=B \in \sigma(f^{-1}(\gamma))$.

Thus, $A\cup{B}\in\sigma(f^{-1}(\gamma))$. But as previously shown - $A\cup{B} = f^{-1}(A^{\star})\cup{f^{-1}({B^{\star}})}=f^{-1}(A^{\star}\cup{B^{\star}})$ Implying $A^{\star}\cup{B^{\star}}\in{M}$ as well. This same logic extends to complements as well. 

Now we note that $\gamma\in{M}$ as $f^{-1}(\gamma)\in{\sigma(f^{-1}(\gamma))}$. Implying, $\sigma(\gamma)\in{M}$ as M is a $\sigma$-field. Concluding our proof.

7. Let $A$ be a Borel set. Show that the $\sigma$-field of subsets of $A$ containing the open sets in $A$ is - $$\set{B\in{\mathbb{B}(\reals) | B\subset{A}}}=\mathbb{B}(\reals)\cap{A}$$

Before we give the answer -  a brief reflection:
This question, at first sight, appeared a little bit convoluted. Specifically, it took me a while to understand what *exactly* is "the $\sigma$-field of subsets of $A$ containing the open sets in $A$"? First its a $\sigma$-field (A collection of subsets with certain properties), but what are these subsets? Are they all subsets of $A$? The open sets in $A$? What is the right way to capture these sets formally but not too little sets such that when I take their $\sigma$-field I will be able to capture the entire Borel sets!.

I went back and re-read the example provided by Ash for the "Good Set" principle and there (I think) I've found a way which might be helpful in this case as well. We introduce the concept of $\sigma_A$ as the $\sigma$-field consisting of subsets of $A$.
With this definition we can formally define the sets in question -

__Answer__:
Let $\gamma$ be the collection of open sets in $\Reals$ and $A$ be the Borel set in question. We must show that $\sigma_A(\gamma\cap{A}) = \mathbb{B}(\reals)\cap{A}$.

First, we will show that $\mathbb{B}(\reals)\cap{A}$ is a $\sigma$-field. For if $a,b\in\mathbb{B}(\reals)$ we have $a\cap{A}, b\cap{A}\in\mathbb{B}(\reals)\cap{A}$, but since $\mathbb{B}(\reals)$ is a $\sigma$-field we have $(a\cap{A})\cup{}(b\cap{A})=(a\cup{b})\cap{A}\in\mathbb{B}(\reals)\cap{A}$ implying $\mathbb{B}(\reals)\cap{A}$ is indeed a $\sigma$-field.

Indeed, we have $\gamma\cap{A}\subset\mathbb{B}(\reals)\cap{A}\implies\sigma_A(\gamma\cap{A})\subset\mathbb{B}(\reals)\cap{A}$.

To show the converse, $\mathbb{B}(\reals)\cap{A}\subset\sigma_A(\gamma\cap{A})$, we will use the "Good Set" principle.

Define - $$M = \set{X\in\mathbb{B}(\reals) | X\cap{A} \in \sigma_A(\gamma\cap{A})}$$

We will show that $M$ is a $\sigma$-field. Indeed, let $U,V\in{M}$ meaning $U\cap{A},V\cap{A}\in \sigma_A(\gamma\cap{A})$ but then, by definition of $\sigma_A(\gamma\cap{A})$ we have $U\cap{A}\cup{}V\cap{A}=(U\cup{V})\cap{A}\in\sigma_A(\gamma\cap{A}) \implies U\cup{V}\in{M}$.

The same reasoning follows for complements.

We finish the proof by observing that $\gamma\in{M}$ but since $M$ is a $\sigma$-field we also have $\sigma(\gamma)=\mathbb{B}(\reals)\in{M}.\space \square$ 
