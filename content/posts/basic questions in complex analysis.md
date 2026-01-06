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