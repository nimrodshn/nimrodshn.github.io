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

__Question:__ Prove that a convergent sequence is bounded

__Answer:__ Let $\set{a_i}$ be a convergent sequence, ie having a finite limit $A$.
Let $\epsilon>0$, by definition, there exists $N\in{\mathbb{N}}$ such that for $n>N$ we have - $|a_n-A|<\epsilon$ implying $|a_n|<|A|+\epsilon$ for all $n>N$. Implying that the tail end of the terms are bounded.

On the other hand, the finite set if terms $\set{a_i}_{i\leq{N}}$ is also bounded as a finite set (simply take its maximum). Together, we have that the sequence is bounded.

__Question:__ (Cesaro) If $\lim_{n\rightarrow\infty}z_n=A$ prove that 
$$
\lim_{n\rightarrow\infty}\frac{1}{n}(z_1+...+z_n)=A
$$

__Answer:__

We define $S_n=\frac{1}{n}(z_1+...+z_n)$. We compute 
$$
|S_n-A| = |\frac{1}{n}((z_1-A)+...+(z_n-A))|
$$

Let $\epsilon>0$. From the convergence of $\set{z_i}$, there exists $N\in{\mathbb{N}}$ such that for $n>N$ we have - 

$$
|S_n-A| = |\frac{1}{n}((z_1-A)+...+(z_n-A))|\leq\frac{1}{n}(|z_1-A|+..+|z_n-A|)<\\\
\frac{1}{n}(|z_1-A|+..+|z_N-A|)+(1-\frac{N}{n})\epsilon
$$

We let $n\rightarrow\infty$ to conclude $\limsup_n|S_n-A|\leq\epsilon$, Since, $\epsilon$ is arbitrarily small we conclude $\lim{S_n}=A$.

__Question__: Investigate the convergence of the sequence $\set{nz^n}^{\infty}_{n=1}$.

__Answer__: Let $z\in{\mathbb{C}}$ such that $z\neq{0}$ .We compute - 

$$
|\frac{(n+1)z^{n+1}}{nz^n}|=(1+\frac{1}{n})|z|
$$

As $n\rightarrow\infty$ we have 

$$
|\frac{(n+1)z^{n+1}}{nz^n}|\rightarrow{|z|}
$$

Case $|z|<1$:

Thus, for sufficiently large $n$ we may pick $|z|<q<1$ such that-
$$
|a_n|=|nz^n|<n|z|^n<nq^n\rightarrow{0}
$$

Since $nq^n\rightarrow{0}$ for any $0<q<1$.

__Side quest Pf__: $nq^n\rightarrow{0}$ for any $0<q<1$.

Recall: $a_{n+1}/a_{n}=(1+\frac{1}{n})q\rightarrow{q}<1$. Implying there exists $N$ such that for $n\geq{N}$, the sequence is decreasing and as it is a sequence of positive numbers it is bounded. Moreover there is $q<s<1$ such that for all $n\geq{N}$ we have  

$$
\frac{|a_{n+p}|}{|a_n|}=\frac{|a_{n+p}|}{|a_{n+p-1}|}...\frac{|a_{n+1}|}{|a_n|}<s^p
$$

Implying for $p\geq{1}$ we have, $a_{N+p}<a_Ns^p=Nq^Ns^p<Ns^{N+p}$.
Than, from our previous analysis, since $s<1$, we may take $n$ to be arbitrarily large and make $|Ns^n|$ arbitrarily small. Implying $|a_n|<|Ns^{n}|$. Now let $\epsilon$, take $n$ such that $n>\log_s{\epsilon/N}$ to obtain $|a_n|<|Ns^{n}|<\epsilon$.

For $|z|>1$: The necessary conditions for convergence do not apply bc the terms do not tend to zero, and therefore the sequence diverges.

__Question__: Show that the sum of an absolute convergent series does not change if the terms are rearranged.

__Proof__: 

Let $S=\sum_{i=0}^\infty{a_i}$ be an absolutly convergent sequence.

Let $\pi:\N\rightarrow\N$ be a permutation of $\N$. 

Since the original sequence is absolutly convergent, let $\epsilon>0$, we find $n_0$ such the for $n>n_0$ we have $|a_n|+....+|a_{n+p}|<\epsilon$ for any $p\geq0$.

This implies there are only finitely many terms in the original series such that the Cauchy criteria does not apply.

For those finite set $\set{1,...,n_0}$, the permutation $\pi$ must place all of them in possibly large set therefore there exists $n_\pi$ such that all the indicies appears among them.

Thus, we may find the largest index $n_\pi$ such that for any $n>n_\pi$ we have $|a_{\pi(n)}+...+a_{\pi(n+p)}|<\epsilon$ for any $p>0$. (since for each $\pi(n)$ we have $\pi(n)>n_0$)

Implying the rearranged series converges from the Cauchy criteria. Moreover, for any $n>n_\pi$ we have

We have -
$$
|S-\sum_{i=0}^n{a_{\pi(i)}}|=|\sum_{i=n+1}^\infty{a_{\pi(i)}}|\leq \\\
\sum_{i=n+1}^\infty{|a_{\pi(i)}|} \leq \sum_{i=n_0+1}^\infty{|a_{i}}|=\epsilon
$$

Concluding the pf.


### Proofs in Complex Analysis:

__Question:__
If $g(z)$ and $f(z)$ are analytic functions show the $f(g(z))$ is analytic.

__Answer:__
Since $f,g$ are both analytic there exists $u_f,u_g$ and $v_f,v_g$ differentiable such that -
$$
f(s+it) = u_f(s,t)+iv_f(s,t) \\
g(x+iy) = u_g(x,y)+iv_g(x,y)
$$

$f,g$ satisfy the Cauchy-Riemann equations respectively.

Let $z\in{\mathbb{C}}$ we compute - 


$$
u_{f\circ{g}} = u_f(u_g(x,y),v_g(x,y)) \implies \\
d_xu_{f\circ{g}} = d_su_fd_xu_g+d_tu_fd_xv_g = \\
$$

Using the Cauchy-Riemann equations for both $f$ and $g$ in the last equality:

$$
d_su_f=d_tv_f \\
-d_tu_f=d_sv_f
$$ 

And - 
$$
d_xu_g=d_yv_g \\
-d_yu_g=d_xv_g
$$

We obtain - 
$$
d_su_fd_xu_g+d_tu_fd_xv_g = \\
d_tv_fd_yv_g+d_sv_fd_yu_g = d_yv_{f\circ{g}}
$$

Similarly, computing $d_yu_{f\circ{g}} = d_su_fd_yu_g + d_tu_fd_yv_g$ and applying Cauchy-Riemann equations yields $d_yu_{f\circ{g}}=-d_xv_{f\circ{g}}$.


__Question:__ Let $f$ be analytic function. If $|f|$ is constant then $f$ is constant.

__Answer:__

Since $|f|$ is constant so is $|f|^2=u^2+v^2$ and thus we may deduce - $d|f|^2=(d_x|f|^2,d_y|f|^2)=0$

$$
d_x|f|^2=2ud_xu+2vd_xv = 0 \\\
d_y|f|^2=2ud_yu+2vd_yv = 0
$$
Using the Cauchy-Riemann equations for $f$ we obtain -
$$
2ud_xu+2vd_xv=0 \\\
-2ud_xv+2vd_xu=0
$$

We obtain two linear equations in $d_xu,d_xv$ corresponding to the following matrix - 

$$
\begin{pmatrix}
   u & v \\\
   v & -u
\end{pmatrix}
$$

Which has a determinant, $-|f|^2=const$, by assumption.

If $|f|=0$ we have $u,v=0$. Otherwise, the matrix is invertible and $d_xu=0,d_xv=0$. 

We repeat, in the same manner for $d_yu=0,d_yv=0$

Implying that $f$ is constant.