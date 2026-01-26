+++
title = 'Basic Inequalities in Analysis'
date = 2026-01-26
draft = false
+++

### Young's Inequality

Let $a,b>0$ and $p,q\neq0,1$ be such that - $\frac{1}{q}+\frac{1}{p}=1$ than for $p>1$ we have - 
$$
a^{\frac{1}{p}}b^{\frac{1}{q}}\leq\frac{1}{p}a+\frac{1}{q}b
$$
Implying - 
$$
a(\frac{b}{a})^{\frac{1}{q}} \leq (1-\frac{1}{q})a+\frac{1}{q}b
$$

We note several observations:

First, we have $\frac{1}{p}=\frac{q-1}{q}$. Implying - $p=\frac{q}{q-1}=1+\frac{1}{q-1}$. This implies that $q>1$ if $p>1$.w

Second, we obtain by substituting $x-1$ to Bernouli's Inequality: $(1+\alpha)^n\geq{n\alpha+1}$ to obtain -
$$
x^n\geq{n(x-1)+1}
$$

To conclude, for $x\geq0$ and natural $n$ we have $x^n\geq{n(x-1)+1}$

We substitute to the above inequality, $n=q$ and $x=(\frac{b}{a})^{\frac{1}{q}}$ to obtain - 

$$
\frac{b}{a}\geq{q[(\frac{b}{a})^{\frac{1}{q}}-1]+1} = \\\
\frac{1}{q}b \geq a[(\frac{b}{a})^{\frac{1}{q}}-1+\frac{1}{q}] = \\\
\frac{1}{q}b \geq a(\frac{b}{a})^{\frac{1}{q}}-(1-\frac{1}{q})a = \\\
(1-\frac{1}{q})a+\frac{1}{q}b \geq a(\frac{b}{a})^{\frac{1}{q}}
$$

Concluding the proof. $\square$.

__An alternative proof__:

We use the convexity of the exponent function:

Let $e^u=a^p$, $e^t=b^q$. Implying, $a=e^{\frac{u}{p}}$, $b=e^{\frac{t}{q}}$. Thus,
$$
ab=e^{\frac{u}{p}}e^{\frac{t}{q}}=e^{\frac{u}{p}+\frac{t}{q}}=e^{u(1-\frac{1}{q})+\frac{t}{q}}\leq(1-\frac{1}{q})e^u+\frac{1}{q}e^t=(1-\frac{1}{q})a^p+\frac{1}{q}b^q
$$

### Holder's Inequality

We prove for $x_i,y_i>0$ for all $1\leq{i}\leq{n}$ and $p,q>1$ such that $\frac{1}{q}+\frac{1}{p}=1$:

$$
\sum_{i=1}^{n}x_iy_i \leq (\sum_{i=1}^{n}x_i^p)^{\frac{1}{p}}(\sum_{i=1}^{n}y_i^q)^{\frac{1}{q}}
$$

__Proof:__
We set $a_j=\frac{x_j}{(\sum_{i=1}^{n}x_i^p)^{\frac{1}{p}}}$, $b_j=\frac{y_j}{(\sum_{i=1}^{n}y_i^q)^{\frac{1}{q}}}$

By Young's inequality we have - 
$$
a_jb_j=\frac{x_jy_j}{(\sum_{i=1}^{n}x_i^p)^{\frac{1}{p}}(\sum_{i=1}^{n}y_i^q)^{\frac{1}{q}}} \leq
\frac{x_j^p}{p\sum_{i=1}^{n}x_i^p} + \frac{y_j^q}{q\sum_{i=1}^{n}y_i^q}
$$

We sum over $j$ to obtain - 
$$
\frac{\sum_{j=1}^n{x_jy_j}}{(\sum_{i=1}^{n}x_i^p)^{\frac{1}{p}}(\sum_{i=1}^{n}y_i^q)^{\frac{1}{q}}} \leq \frac{1}{p}+\frac{1}{q}=1
$$

Implying the result.

### Minkowski's Inequality

We prove for $x_i,y_i>0$ for all $1\leq{i}\leq{n}$ and $p,q>1$ such that $\frac{1}{q}+\frac{1}{p}=1$:

$$
(\sum_{i=1}^{n}(x_i+y_i)^p)^{\frac{1}{p}} \leq (\sum_{i=1}^{n}x_i^p)^{\frac{1}{p}} + (\sum_{i=1}^{n}y_i^p)^{\frac{1}{p}}
$$


__Attempts at a proof:__
We start by developing the left hand side - 

$$
(\sum_{i=1}^n(x_i+y_i)^p)^{\frac{1}{p}} =  (\sum_{i=1}^n(x_i+y_i)^{p-1}(x_i+y_i))^{\frac{1}{p}} = \\\
(\sum_{i=1}^n(x_i+y_i)^{p-1}x_i+(x_i+y_i)^{p-1}y_i)^{\frac{1}{p}} \leq \\\
((\sum_{i=1}^n(x_i+y_i)^{q(p-1)})^{\frac{1}{q}}(\sum_{i=0}^nx_i^p)^{\frac{1}{p}}+(\sum_{i=1}^n((x_i+y_i)^{q(p-1)})^{\frac{1}{q}}(\sum_{i=0}^ny_i^p))^{\frac{1}{p}})^{\frac{1}{p}} =  \\\
(\sum_{i=1}^n(x_i+y_i)^{p})^{\frac{1}{pq}}((\sum_{i=0}^nx_i^p)^{\frac{1}{p}}+(\sum_{i=0}^ny_i^p)^{\frac{1}{p}})^{\frac{1}{p}} \implies \\\
(\sum_{i=1}^n(x_i+y_i)^p)^{\frac{1}{p^2}} \leq ((\sum_{i=0}^nx_i^p)^{\frac{1}{p}}+(\sum_{i=0}^ny_i^p)^{\frac{1}{p}})^{\frac{1}{p}}
$$

After raising to the $p$th power we arive at the conclusion.