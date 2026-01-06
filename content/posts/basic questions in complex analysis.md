+++
title = 'Basic questions in Complex Analysis (From Ahlfors)'
date = 2025-12-30
draft = false
+++

### Algebra of Complex numbers

1. Prove the isomorphism between the system of matrices (wrt matrix multiplication and addition) of the following form and the field of complex numbers -

$$
\begin{pmatrix}
   \alpha & \beta \\\\
   -\beta & \alpha
\end{pmatrix}
$$

__Proof:__
Given a complex number $x=\alpha+i\beta$ we define the correspondence $\phi(x)=\phi(\alpha+i\beta)=$

$$
\begin{pmatrix}
   \alpha & \beta \\\\
   -\beta & \alpha
\end{pmatrix}
$$

Let $y=\gamma+i\delta$. Thus, $\phi(x+y)=\phi(\alpha+\gamma+i(\beta+\delta))$ = 

$$
\begin{pmatrix}
   \alpha+\gamma & \beta+\delta \\\\
   -(\beta+\delta) & \alpha+\gamma
\end{pmatrix} =
\begin{pmatrix}
   \alpha & \beta \\\\
   -\beta & \alpha
\end{pmatrix} +
\begin{pmatrix}
   \gamma & \delta \\\\
   -\delta & \gamma
\end{pmatrix} = \phi(x)+\phi(y)
$$

We compute $\phi(x)\phi(y)=$
$$
\begin{pmatrix}
   \alpha & \beta \\\\
   -\beta & \alpha
\end{pmatrix}
\begin{pmatrix}
   \gamma & \delta \\\\
   -\delta & \gamma
\end{pmatrix} =
\begin{pmatrix}
   \alpha\gamma-\beta\delta & \alpha\delta+\beta\gamma \\\\
   -(\alpha\delta+\beta\gamma) & \alpha\gamma-\beta\delta
\end{pmatrix} =
\phi(\alpha\gamma-\beta\delta+i(\alpha\delta+\gamma\beta)) =
\phi(xy)
$$

2. Verify by calculation that the values of $\frac{z}{z^2+1}$ for $z=x+iy$ and $z=x-iy$ are conjucate.

Indeed - 
$$
\frac{\overline{x+iy}}{\overline{(x+iy)^2+1}} = 
\frac{\overline{x+iy}}{\overline{(x+iy)(x+iy)}+1} = 
\frac{{x-iy}}{\overline{(x+iy)}\space\overline{(x+iy)}+1} = 
\frac{{x-iy}}{(x-iy)(x-iy)+1} = 
\frac{{x-iy}}{(x-iy)^2+1}
$$

3. We Prove "Lagrange's Identity" - $|\sum_{i=1}^{n}a_ib_i|^2=\sum_{i=1}^{n}|a_i|^2\sum_{i=1}^{n}|b_i|^2-\sum_{1\leq{i}<j\leq{n}}|a_i\bar{b_j}-a_j\bar{b_i}|^2$

We prove by induction on $n$. For the case of $n=1$ we have, by definition of the absolute value - 

$$
|ab|=ab\bar{ab}=ab\bar{a}\bar{b}=a\bar{a}b\bar{b}=|a||b| \implies |ab|^2=|a|^2|b|^2
$$

We assume the statement is correct for $n\in{\mathbb{N}}$ and prove for $n+1$:
$$
|\sum_{i=1}^{n+1}a_ib_i|^2=|\sum_{i=1}^{n}a_ib_i+a_{n+1}b_{n+1}|^2=|\sum_{i=1}^{n}a_ib_i|^2+|a_{n+1}b_{n+1}|^2+2Re(\overline{a_{n+1}b_{n+1}}\sum_{i=1}^{n}a_ib_i) = \\\
\sum_{i=1}^{n}|a_i|^2\sum_{i=1}^{n}|b_i|^2-\sum_{1\leq{i}<j\leq{n}}|a_i\bar{b_j}-a_j\bar{b_i}|^2+|a_{n+1}b_{n+1}|^2+2Re(\overline{a_{n+1}b_{n+1}}\sum_{i=1}^{n}a_ib_i) = \\\
\sum_{i=1}^{n}|a_i|^2\sum_{i=1}^{n}|b_i|^2-[\sum_{1\leq{i}<j\leq{n}}|a_i\overline{b_j}|^2+|a_j\overline{b_i}|^2-2Re(a_i\overline{b_j}\overline{a_j}b_i)] + |a_{n+1}b_{n+1}|^2+2Re(\overline{a_{n+1}b_{n+1}}\sum_{i=1}^{n}a_ib_i)
$$
Next we note the following two statements - 
1. $2Re(\overline{a_{n+1}b_{n+1}}\sum_{i=1}^{n}a_ib_i)=2Re(a_1\overline{b_{n+1}}\overline{a_{n+1}}b_1+\dots+a_n\overline{b_{n+1}}\overline{a_{n+1}}b_n)=\sum_{i=1}^n2Re(a_i\overline{b_{n+1}}\overline{a_{n+1}}b_i)$

2. Next, we add and subtract the following sums $\sum_i^n|a_ib_{n+1}|^2$ and $\sum_i^n|b_{i}a_{n+1}|^2$ to obtain the final result - 
$$
\sum_{i=1}^{n+1}|a_i|^2\sum_{i=1}^{n+1}|b_i|^2-[\sum_{1\leq{i}<j\leq{n+1}}|a_i\overline{b_j}|^2+|a_j\overline{b_i}|^2-2Re(a_i\overline{b_j}\overline{a_j}b_i)] = \\\
|\sum_{i=1}^{n+1}a_ib_i|^2=\sum_{i=1}^{n+1}|a_i|^2\sum_{i=1}^{n+1}|b_i|^2-\sum_{1\leq{i}<j\leq{n+1}}|a_i\bar{b_j}-a_j\bar{b_i}|^2
$$
$\square$.

Going back to the question of $\overline{a}\overline{b}=$
$$
(\alpha-i\beta)(\gamma-i\delta) = (\alpha\gamma-\beta\delta)-i(\alpha\delta+\gamma\beta)=\overline{ab}
$$

3. A proof of Cauchy's inequality -
$$
|\sum_{i=1}^na_i\overline{b_i}|^2\leq\sum_{i=1}^n|a_i|^2\sum_{i=1}^n|b_i|^2
$$
This line of proof is taken from Ahlfors (p. 11) with details introduced by myself:
Let $\lambda\in\mathbb{C}$. We write -
$$
0\leq\sum_{i=1}^n|a_i-\lambda\overline{b_i}|^2=\sum_{i=1}^n|a_i|^2+|\lambda|^2\sum_{i=1}^n|b_i|^2-\sum_{i=1}^n2Re(a_i\overline{\lambda}b_i)
$$
We plug in $\lambda=\frac{\sum_{i=1}^na_i\overline{b_i}}{\sum_{i=1}^n|b_i|^2}$ -
$$
\sum_{i=1}^n|a_i|^2+\frac{|\sum_{i=1}^na_i\overline{b_i}|}{(\sum_{i=1}^n|b_i|^2)^2}^2\sum_{i=1}^n|b_i|^2-2Re(\overline{\lambda}\sum_{i=1}^na_ib_i) = \\\
\sum_{i=1}^n|a_i|^2+\frac{|\sum_{i=1}^na_i\overline{b_i}|}{(\sum_{i=1}^n|b_i|^2)^2}^2\sum_{i=1}^n|b_i|^2-2Re({\frac{\overline{\sum_{i=1}^na_i\overline{b_i}}}{\overline{\sum_{i=1}^n|b_i|^2}}}\sum_{i=1}^na_i\overline{b_i}) = \\\
\sum_{i=1}^n|a_i|^2+\frac{|\sum_{i=1}^na_i\overline{b_i}|}{\sum_{i=1}^n|b_i|^2}^2-2Re(\frac{{|\sum_{i=1}^na_i\overline{b_i}|^2}}{\overline{\sum_{i=1}^n|b_i|^2}}) = \\\
\sum_{i=1}^n|a_i|^2+\frac{|\sum_{i=1}^na_i\overline{b_i}|}{\sum_{i=1}^n|b_i|^2}^2-2\frac{{|\sum_{i=1}^na_i\overline{b_i}|^2}}{\sum_{i=1}^n|b_i|^2} = \\\
\sum_{i=1}^n|a_i|^2-\frac{{|\sum_{i=1}^na_i\overline{b_i}|^2}}{\sum_{i=1}^n|b_i|^2} = \\\
\sum_{i=1}^n|a_i|^2-\frac{{|\sum_{i=1}^na_i\overline{b_i}|^2}}{\sum_{i=1}^n|b_i|^2} \geq{0}
$$

Implying the inequality. $\square$.

__A different perspective:__

Let $u,v\in{\mathbb{C^n}}$. Define $\braket{u,v}=\sum_{i=0}^na_i\overline{b_i}$. Implying - $\|u\|^2=\sum_{i=0}^na_i\overline{a_i}=\sum_{i=0}^n|a_i|^2$

Implying we are to prove the *Cauchy-Schwarz* inequality - $|\braket{u,v}|^2\leq{\|u\|^2\|v\|^2}$.
Thus we can use the fact that $\frac{\braket{u,v}}{\|v\|^2}$ represents the ortogonal projection of $u$ onto $v$ to minimize $\lambda$ in the expression $\|a-\lambda \bar{b}\|^2$.

We choose $\lambda=\frac{\braket{a,b}}{\|b\|^2}$ to minimize the orthogonal projection and attain an expression with $\braket{a,b}$ - 

$$
0\leq\|a-\lambda b\|^2=\|a-\frac{\braket{a,b}}{\|b\|^2}b\|^2 = \\\
 \braket{a-\frac{\braket{a,b}}{\|b\|^2}b,a-\frac{\braket{a,b}}{\|b\|^2}b} = 
 \|a\|^2+\frac{|\braket{a,b}|^2}{\|b\|^4}\|b\|^2-2\frac{|\braket{a,b}|^2}{\|b\|^2} = \\\
\|a\|^2+\frac{|\braket{a,b}|^2}{\|b\|^2}-2\frac{|\braket{a,b}|^2}{\|b\|^2}=\|a\|^2-\frac{|\braket{a,b}|^2}{\|b\|^2}
$$

Concluding the proof. $\square$


### Analytical Geometry in the Complex plane

A line in the complex plan is define by $f(t)=a+bt$ for $t\in{\mathbb{R}}$.

__Theorem:__ Two lines $f(t)=a+bt$ and $g(t)=a'+b't$ are identical $\iff$ $a-a'$ and $b'$ are both multiple of $b$.

$\implies$ Assume $g=f$. If $a=a'$ we are done, otherwise there exists $t_0$ such that $g(0)=f(t)$ implying $a'=a+bt_0$ implying $a-a'=-bt_0$.

Similarly, there exists $t_1$ such that $g(1)=f(t_1)$ implying, $a'+b'=a+bt_1 \implies b'=b(t_1-t_0)$

$\impliedby$ Assume $a-a'$ and $b'$ are both multiples of $b$. Let $t\in{\mathbb{R}}$. Than, by assumption there exists constants $q,c\in{\mathbb{R}}$ such that $f(t)=a+bt=(a'+qb)+cb't=a'+b'c(q+t)=g(c(q+t))$. $\square$

__Question:__ Prove that the two diagonals of a parallelogram bisect each other. 

__Answer:__
Let $a,b\in{\mathbb{C}}$. We assume $|a|\neq0$, $|b|\neq0$

We consider the following real function - $g(t)=|(a+b)t|^2-|(a(1-t)+bt)|^2$

Than $g(0)=-|a|^2$ while $g(1)=|a+b|^2-|b|^2\geq{0}$ than by the intermediate value theorem there exists a point $p\in{[0,1]}$ such that $g(p)=0$ implying the result.

While the above result only shows existance we may also prove the following - Define $f(t)=(a+b)t$ and $g(t)=a(1-t)+bt$. Then -

$f(1/2)=\frac{a+b}{2}=g(1/2)$ concluding the pf.