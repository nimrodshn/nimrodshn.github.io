+++
title = 'Proofs in Topology and Metric Spaces (from Mathematical Analysis 2 by Zorich)'
date = 2026-02-04
draft = false
+++

### A criteria for compactness in a Metric space.

A metric space $(X,d)$ is compact if and only if for every sequence of elements one can extract a convergent subsequence.

__Proof:__

$\implies$ Let $\set{x_i}_{i\in{\mathbb{N}}}$ be a sequence of elements in $X$. If the sequence contains only a finite set of distinct elements than [by  "the pigeonhole principle"] some element repeats infinitly many times implying the result. Thus, we assume there are infinitly many distinct elements in the sequence. Since $X$ is compact it has a finite $\epsilon$-net for any $\epsilon>04$. Thus we may pick a 1-net covering $X$. In this finite 1-net $E_1$ there exists an element $a_1$ such that there are infinitly many elements in the sequence in $\overline{B(a_1,1)}$ otherwise the sequence itself is finite.

Since the closed ball $\overline{B(a_1,1)}$ is compact we may find a $\frac{1}{2}$-net in the ball and in the same manor a closed ball $\overline{B(a_2,\frac{1}{2})}$ such that there are infinitly many point in the sequence inside this ball. In this mannor we find a series of closed balls $.. \subset \overline{B(a_n,\frac{1}{n})} \subset .. \space \overline{B(a_1,1)}$ such that there are elemnts of the sequence in each closed ball and by the nested compactness of each closed ball there exists an element in their intersection. These elemnts form a convergents subsequence of the original sequence.


$\impliedby$ Since any sequence has a convergent subsequence we can find a finite $\epsilon$-net for any $\epsilon>0$. This net $E$ forms a finite covering of $K$ implying $K$ is compact.


__Question__:
A subset $Y$ of a metric space $X$ is totally bounded if for any $\epsilon>0$ it has a finit $\epsilon$-net.

Show that the property of total boundeness is independent of the $\epsilon$-net elements belonging to $Y$ or its ambient space.

__Proof:__  Let $Y\subset{X}$, and assume $Y$ admits an $\epsilon$-net for some $\epsilon>0$ formed from elements in $X$. Than for any element $x_i$ in the set $E$ forming the $\epsilon$-net, such that $Y\cap{B(x_i,\epsilon)}\neq\emptyset$, we may pick $y_i\in{Y}$ such that $y_i\in{Y\cap{B(x_i,\epsilon)}}$. 

Let $y\in{Y}$ than, by definition $y\in{{Y\cap{B(x_i,\epsilon)}}}$ for some $i$.

We have by the triangle inequality, $d(y_i,y)\leq d(y_i,x_i)+d(x_i,y)=\epsilon+\epsilon=2\epsilon$. Implying that our choice of $y_1$,..,$y_N$ form an $2\epsilon$-net.

Implying we may form an $\epsilon$-net from elements of $Y$ or $X$ of arbitrarily small $\epsilon$.

__Question__:
Having a metric space $d$ on a set $X$ one may attempt to define the distand $\bar{d}(A,B)$ over sets $A,B\subset{X}$:

$$
\bar{d}(A,B)=\inf_{a\in{A},b\in{B}}d(a,b)
$$

Intuitivly, that is the minimal distances between $A,B$.
Naviely, if $A\cap{B}\neq\phi$ then $\bar{d}(A,B)=0$. But this is not a necessary condition for one may take $A=[-\infty,0)$ and $B=[0,\infty]$ than $\bar{d}(A,B)=0$ but $A\cap{B}=\phi$. (this is question a, in Zorich.)

We now define a distance over *closed sets* in $X$, take 

$$
D(A,B)=\max{(\sup_{a\in{A}}\bar{d}(a,B), \sup_{b\in{B}}\bar{d}(b,A))}
$$

Prove this function is a metric over closed sets.

__Proof__
At first glance, the importance of *closed sets* is not entirely clear in the above definition.

We first proove $D(A,A)=0$.

Assume by contradiciton the $A\neq{B}$ yet $D(A,B)=0$.

Than, by definition $D(A,B)=\max{(\sup_{a\in{A}}\bar{d}(a,B), \sup_{b\in{B}}\bar{d}(b,A))}=0$

We must have $\sup_{a\in{A}}\bar{d}(a,B)=\sup_{b\in{B}}\bar{d}(b,A)=0$.

Without loss of generality we consider the first case of $\sup_{a\in{A}}\bar{d}(a,B)=0$, we must have $\bar{d}=0$ since $\bar{d}$ is infimum over a metric, implying $\forall{a}\in{A}$ either $a$ is a limit point of $B$ or it is in $B$ but since B is closed it must contain all of its limit points thus we must have $A\subset{B}$.

The case for $B\subset{A}$ is symmetric.

The symmetry condition for distance functions apply for D from its definition.

We are left to derive the triangles inequality:

We write $D(A,C)=\max{(\sup_{a\in{A}}\bar{d}(a,C), \sup_{c\in{C}}\bar{d}(c,A))}$

Let, $a\in{A},b\in{B}$ be arbitrary points. From the definition of $\bar{d}$ and the triangle inequality we have - 
$$
\bar{d}(a,C) \leq d(a,b)+ \bar{d}(b,C) \leq \\\
\bar{d}(a,B)+\sup_{b\in{B}}\bar{d}(b,C) \leq
$$
We take the supremum over $a$ to obtain - 
$$
\sup_{a\in{A}}\bar{d}(a,C) \leq \sup_{a\in{A}}\bar{d}(a,B)+\sup_{b\in{B}}\bar{d}(b,C)
$$

The same applies for the symmetric inequelity (i.e "from C to A through B").

We take the maximum over both to obtain - 

$$
D(A,C)=\max(\sup_{a\in{A}}\bar{d}(a,C), \sup_{c\in{C}}\bar{d}(c,A)) \leq \\\
\max(\sup_{a\in{A}}\bar{d}(a,B)+\sup_{b\in{B}}\bar{d}(b,C),\sup_{c\in{C}}\bar{d}(c,B)+\sup_{b\in{B}}\bar{d}(b,A)) \leq \\\
\max(\sup_{a\in{A}}\bar{d}(a,B),\sup_{b\in{B}}\bar{d}(b,A)) + \max(\sup_{b\in{B}}\bar{d}(b,C),\sup_{c\in{C}}\bar{d}(c,B)) = \\\
D(A,B)+D(B,C)
$$

$\square$.

__Question__:
Verify that if $(X,d)$ is a metric space then $(X,\frac{d}{1+d})$ is also a metric space and the metrics  $d,\frac{d}{d+1}$ induce the same topology.

__Proof__:
Indeed, for any $x\in{X}$, from $d$ as a metric, we have $\frac{d(x,x)}{1+d(x,x)}=0$.

And for any $x,y\in{X}$ from having $d$ as a metric - 
$$
\frac{d(x,y)}{1+d(x,y)}=\frac{d(y,x)}{1+d(y,x)}
$$ 

Now we must show that for any $x,y,z\in{X}$

$$
\frac{d(x,y)}{1+d(x,y)}+\frac{d(y,z)}{1+d(y,z)}\geq\frac{d(x,z)}{1+d(x,z)}
$$

Indeed, 
$$
\frac{d(x,y)}{1+d(x,y)} + \frac{d(y,z)}{1+d(y,z)}\geq \\\
\frac{d(x,y)}{1+d(x,y)+d(y,z)} + \frac{d(y,z)}{1+d(x,y)+d(y,z)}\geq \\\
\frac{d(x,y)+d(y,z)}{1+d(x,y)+d(y,z)}\geq \\\
\frac{d(x,z)}{1+d(x,z)}
$$

To show that they define the same topology, we must show that if $A$ is open in $(X,d)$ it is also open in $(X,\frac{d}{1+d})$

