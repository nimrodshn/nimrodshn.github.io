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