+++
title = 'Notes on Real Analysis and Probability (Ash)'
date = 2025-11-10T08:49:31+02:00
draft = false
+++

Following the recommendations[[1](https://terrytao.wordpress.com/career-advice/write-down-what-youve-done/)][[2](https://terrytao.wordpress.com/career-advice/ask-yourself-dumb-questions-and-answer-them/)] of one Terry Tao, I've started this set of notes (or journal?) for my own enjoyment while reading through "Real Analysis and Probability" by Robert Ash.

These notes will be split by chapter. I may jump to between chapters as the book is structured in such a way that one can jump from chapter two to chapter five.

# Chapter 1:

## Basic properties of sets:

0. If $A_1....A_k$ form an increasing sequence (in the sense  $A_{1}\subset{A_{2}}...\subset{A_k}$), than their complements form a _decreasing_ sequence - $A_{k}^c\subset{A_{i-2}^c}...\subset{A_1^c}$.

__Proof__: By induction. For $k=2$, $A_1\subset{}A_2$. Assume that $A_2^c\nsubseteq{}A_1^c$. We may conclude -

$$
A_2^c - A_1^c\neq\phi
$$

But than, $A_2^c\cap{}A_1\neq\phi.$ Contradicting our assumption $A_1\subset{}A_2$.

Fix arbitrary $k$. Let $A_{1}\subset{A_{2}}...\subset{A_k}$ be an increasing sequence. By induction - $A_{k-1}^c\subset{A_{i-2}^c}...\subset{A_1^c}$. All that remains to be proven is $A^c_{k}\subset{}A^c_{k-1}$. We may repeat the argument for $k=2$ to finish the proof. $\square$

1. $\bigcup{A_i} = \bigcup_{i=1}^{\infty}{(A_i\cap{A_{i-1}^c\cap...\cap{A_1^c}})}$

__Proof__: By induction. For $k=1$ the assertion is trivial (take $A_0=\phi$). Assume the assertion is correct for arbitrary $k$. We compute -

$$
\bigcup_{i=1}^{k+1}{A_i}=\bigcup_{i=1}^{k}{A_i}\cup{A_{k+1}}=\bigcup_{i=1}^{k}{(A_i\cap{A_{i-1}^c\cap...\cap{A_1^c}})}\cup{A_{k+1}} \\\
=\bigcup_{i=1}^{k}{(A_i\cap{A_{i-1}^c\cap...\cap{A_1^c}})}\cup{A_{k+1}}\cap{(A_{k-1}^c\cap...\cap{A_1^c})}\cup{A_{k+1}}\cap{(A_{k-1}^c\cap...\cap{A_1^c})^c} \\\
=\bigcup_{i=1}^{k}{(A_i\cap{A_{i-1}^c\cap...\cap{A_1^c}})}\cup{A_{k+1}}\cap{(A_{k-1}^c\cap...\cap{A_1^c})}\cup{A_{k+1}}\cap{(A_{k-1}\cup...\cup{A_1})} \\\
=\overbrace{\bigcup_{i=1}^{k}{(A_i\cap{A_{i-1}^c}\cap...\cap{A_1^c})}}^{(\star)}\cup{A_{k+1}}\cap{(A_{k-1}^c\cap...\cap{A_1^c})}\cup{A_{k+1}}\cap\overbrace{\bigcup_{i=1}^{k}{(A_i\cap{A_{i-1}^c\cap...\cap{A_1^c}})}}^{(\star)} \\\
=\bigcup_{i=1}^{k}{(A_i\cap{A_{i-1}^c}\cap...\cap{A_1^c})}\cup{A_{k+1}}\cap{(A_{k-1}^c\cap...\cap{A_1^c})} \\\
=\bigcup_{i=1}^{k+1}{(A_i\cap{A_{i-1}^c}\cap...\cap{A_1^c})}
$$

In my eyes, the above proof indeed highlights the intuitive part of this representation in which we can consider this union as "inductivly adding the 'missing' parts from each set in our sets".

2. In case the $A_i$'s are increasing one may write - $\cup{A_i}=(A_i-A_{i-1})$ in the previous formula (taking $A_0=\phi$).

__Proof__: If the $A_i$'s form an increasing sequence their complements form a decreasing sequence (i.e. $A_{i-1}^c\subset{A_{i-2}^c}...\subset{A_1^c}$) thus -

$$
A_{i-1}^c\cap..\cap{A_1^c}=A_{i-1}^c 
$$

Thus, each term in the union becoms - $A_i\cap{A_{i-1}^c}=A_i-A_{i-1}$.

### $\limsup$ and $\liminf$:
The concept of the above limits eluded me at first (and second) glance, firstly - I find the definitions given in the book slightly hard to parse, I hope that with some (naive?) examples intuition may be gained.

Let $A_1, A_2...\subset{\Omega}$ be a sequence of subsets. Define -

$\limsup = \bigcup_{n=1}^\infty \bigcap_{i=n}^\infty A_i$

$\liminf = \bigcap_{n=1}^\infty \bigcup_{i=n}^\infty A_i$

In the book these definitions are given with subscript $n$ which seems odd to me as the above definitions are independent of it (in the sense that the choice of letter $n$ in the outer operation can be replaced by any letter of the alphabet).

#### Examples:

There are several "canonical" examples to play with thought the one I prefer the most to
highlight the difference is to take two *disjoint sets* $A,B \subset{\Omega}$ and define:

$$A_n=\begin{cases}
   A &\text{if n is even}  \\
   B &\text{if n is uneven} 
\end{cases}$$

Than - $\limsup{A_n} = A \cup B$, while - $\liminf{A_n} = \phi$.

This example highlights the following properties that are presented in the book - 

 - $w\in \liminf{A_n}$ iff there exists $k$ such that for all $m\geq{k}$ we have - $w\in{A_m}$.

 - $w\in \limsup{A_n}$ iff w appears in infinitly many ${A_m}$.

10. $(\limsup{A_n})^c=\liminf A_n^c$

__Proof__: By definition - 
$$
(\limsup{A_n})^c = (\cap_{n=1}^{\infty}\cup_{i=n}^{\infty}{A_i})^c = \\\
(\cup_{i=1}^{\infty}{A_i} \cap...\cap \cup_{i=n}^{\infty}{A_i}\cap...)^c = \\\
((\cup_{i=1}^{\infty}{A_i})^c \cup...\cup (\cup_{i=n}^{\infty}{A_i})^c\cup...) = \\\
((\cap_{i=1}^{\infty}{A_i^c}) \cup...\cup (\cap_{i=n}^{\infty}{A_i^c})\cup...) = \\\
\liminf{A_n^c}
$$

11. $(\liminf{A_n})^c = \limsup{A_n^c}$

__Proof__: Similar reasoning to 10.

12. $\liminf{A_n} \subset \limsup{A_n}$

__Proof__: Let $w \in \cup_{n=1}^{\infty}\cap_{i=n}^{\infty}{A_i}$. Than, we deduce - 

$w \in \cap_{i=n}^{\infty}{A_i}$ for all $i\geq{N}$ for some $N$.

Therefor there exists some $N$ such that $w\in{A_i}$ for all $i\geq{N}$.

Thus, we may deduce, $w \in \cup_{i=n}^{\infty}{A_i}$ for *all* $n$. Meaning, $w\in\cap_{n=1}^{\infty}\cup_{i=n}^{\infty}{A_i} = \limsup{A_n}. \square$

13. If If $A_1....A_k$ form an increasing (or decreasing) sequence up to some limit set $A_n\uparrow{A}$ then $\liminf{A_n}=\limsup{A_n}=A$.

__Proof__: Assume $A_1....A_k$ form an increasing sequence. By definition - 

$$
\limsup{A_n} = \bigcap_{n=1}^{\infty}\bigcup_{i=n}^{\infty}{A_i} = \bigcap_{n=1}^{\infty}A=A
$$

On the otherhand - 

$$
\liminf{A_n} = \bigcup_{n=1}^{\infty}\bigcap_{i=n}^{\infty}{A_i} = \bigcup_{n=1}^{\infty}A_n=A.
$$

Concluding the proof. $\square$