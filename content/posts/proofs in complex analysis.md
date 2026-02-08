+++
title = 'Proofs in Complex Analysis'
date = 2026-02-08
draft = false
+++

### More proofs in analysis:

__Question (Composition of differentiable functions):__
Let $f,g$ be differentiable functions such that $g:X\rightarrow{Y}$ and $f:Y\rightarrow{Z}$ such that the image of $g$ is contained within the domain of $f$. 
Than, $f\circ{g}$ is a differentiable function and its derivative is given by $f(g(x))'=f'(g(x))g'(x)$.

__Answer:__
Let $t\in{X}$, implying by our assumption $g(t)\in{Y}$. Than differentiability of $f$ we may write - 
$$
f(g(t)+h)-f(g(t))=f'(g(t))h+o(h)
$$

We define $h(u)=g(t+u)-g(t)$ implying - 

$$
f(g(t+u))-f(g(t)) = \\
f(g(t)+h(u))-f(g(t)) = \\
f'(g(t))h(u)+o(h(u)) = \\
f'(g(t))(g(t+u)-g(t))+o(h(u))
$$

Since $h(u)=g(t+u)-g(t)=g'(t)u+o(u)$,

we have $h(u)=O(u)+o(u)=O(u)$, implying $o(h(u))=o(u).$

$$
f'(g(t))(g'(t)u+o(u))+o(u) = \\
f'(g(t))g'(t)u+f'(g(t))o(u)+o(u) = \\
f'(g(t))g'(t)u+o(u)+o(u) = \\
f'(g(t))g'(t)u+o(u)
$$


Concluding the proof.

### Proofs in Complex Analysis:

__Question:__
If $g(w)$ is analytic and $f(z)$ are analytic functions show the $f(g(z))$ is analytic.

__Answer:__
Let $z\in{\mathbb{C}}$ we compute - 

$$
\frac{d(f \circ g)}{dx}=\frac{d(f(g(z)))}{dx}=\frac{du_{f \circ g}(z)}{dx}+i\frac{dv_{f \circ g}(z)}{dx}=\frac{du_f(g(z))}{dx}+i\frac{dv_f(g(z))}{dx}= \\\
\frac{d(u_f(z))}{dx}(\frac{d(u_g(z))}{dx}+i\frac{d(v_g(z))}{dx})+i\frac{d(v_f(z))}{dx}(\frac{d(u_g(z))}{dx}+i\frac{d(v_g(z))}{dx})= \\\
\frac{d(v_f(z))}{dy}(-i\frac{d(u_g(z))}{dy}+\frac{d(v_g(z))}{dy})-i\frac{d(u_f(z))}{dy}(-i\frac{d(u_g(z))}{dy}+\frac{d(v_g(z))}{dy}) = \\\
\frac{d(v_f(z))}{dy}(-i\frac{dg(z)}{dy})-i\frac{d(u_f(z))}{dy}(-i\frac{dg(z)}{dy}) = \frac{d(v_f(z))}{dy}(-i\frac{dg(z)}{dy})-i\frac{d(u_f(z))}{dy}(-i\frac{dg(z)}{dy}) = \\\
\frac{d(v_{f \circ g}(z))}{dy}-i\frac{d(u_{f \circ g}(z))}{dy}
$$

Implying the Cauchy-Riemann equations are satisfied, implying $f \circ g$ is analytic.