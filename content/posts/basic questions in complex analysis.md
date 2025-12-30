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