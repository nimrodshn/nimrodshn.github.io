+++
title = 'A question from the 2025 UBC qualifying exam'
date = 2025-12-10
draft = false
+++

Let $f:(0,\infty)\rightarrow\mathbb{R}$ be a twice differentiable function. Further suppose There are constants $A,B,C$ such that - 

$A=\sup_{x>0}{|f(x)|}\newline B=\sup_{x>0}{|f'(x)|}\newline C=\sup_{x>0}{|f''(x)|}$

Prove that $B^2\leq{4AC}$:

a.  Use Taylor’s Theorem to expand $f(x)$ about $a$ and compute $f(a + 2h)$
for $h > 0$.

b. Rearrange the resulting expression to isolate $|f(a)|$ and bound it in terms of $A$, $C$ and $h$.

c. Now pick $h$ to minimise your bound on $|f(a)|$ and clean up.

__Answer:__

a. We expand $f$ around $a$ using Taylor's formula (with Lagrange's remainder):
$$
f(x) = f(a) + f'(a)(x-a) + \frac{f''(\xi)(x-a)^2}{2!}
$$

For some $\xi\in{[a,x]}$.

We plug in $x=a+2h$ - 
$$
f(a+2h) = f(a) + 2hf'(a) + \frac{f''(\xi)(2h)^2}{2} \\
$$

b. We re-arrange - 
$$
f(a+2h) - f(a) - f''(\xi)2h^2 = 2hf'(a) \\
\implies \frac{f(a+2h) - f(a)}{2h} - f''(\xi)h = f'(a) \\
\implies |\frac{f(a+2h) - f(a)}{2h} - f''(\xi)h| = |f'(a)|
$$

We bound the left hand side using $A,C$ and $h$ to obtain a bound on $|f'(a)|$ - 
$$
|f'(a)| = |\frac{f(a+2h) - f(a)}{2h} - f''(\xi)h| \leq |\frac{f(a+2h) - f(a)}{2h}| + |f''(\xi)h| \leq \frac{|f(a+2h)|+|f(a)|}{2h}+Ch
$$

We obtain - 
$$
|f'(a)|\leq{\frac{|f(a+2h)|+|f(a)|}{2h}+Ch}\leq{\frac{2A}{2h}+Ch}=\frac{A}{h}+Ch
$$

c. We attempt to find $h$ to minimize the left hand side bound - 

$$
-\frac{A}{h^2}+C=0 \implies h^2=\frac{A}{C} \implies h=\sqrt{\frac{A}{C}}
$$

We plug back the value to obtain -

$$
|f'(a)|\leq{A\sqrt{\frac{C}{A}}+C\sqrt{\frac{A}{C}}}=2\sqrt{AC}
$$

Since both sides are non-negative we obtain - 
$$
|f'(a)|^2\leq{4AC}
$$

Since $a$ was chosen at random this bound applies to all points in our domain, concluding the proof. $\square$