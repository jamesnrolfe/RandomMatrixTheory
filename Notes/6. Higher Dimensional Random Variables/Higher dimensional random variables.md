#Notes 

If $X$ and $Y$ take values in $\mathbb{\mathbb{R}}$ then $\boldsymbol Z=(X,Y)$ takes values in $\mathbb{\mathbb{R}}\times\mathbb{\mathbb{R}}=\mathbb{\mathbb{R}}^2$. The probability that $\boldsymbol Z$ lies within some *area* $A$, with $A\subset \mathbb{\mathbb{R}}^2$, is 

$$
P\{\boldsymbol Z\in A\}=\mu(A)=\int_Ap(x,y)dxdy
$$

where $p(x,y)$ is well behaved and non-negative in $\mathbb{R}^2$. 

Here, $p(x,y)$ is the **joint** probability distribution function of $X$ and $Y$.
Sometimes, $p(x,y)$ has a property where we can split it into two one-dimensional functions

$$
p(x,y)=q(x)r(y)
$$

In this case, $X$ and $Y$ are *statistically independent.* 

The probability that $X\in I_x=[a,b]$ and $Y \in I_y =[c,d]$ is simply 

$$
\mu(I_x\times I_y)=\int^b_a\int^d_c q(x)r(y)dxdy=\mu(I_x)\mu(I_y)
$$

or in words, the two probabilities don’t depend on each other. The outcome of $Y$ is unaffected by the outcome of $X$, and vice versa. 

Not all real random variables live on the *full* real line. We might have a random variable that lives only in $[x_1,x_2]$, and so the limits of integration in the above need to reflect this. 

---

*Exercise*

We have a joint probability density function in $x,y\in \mathbb{R}$ defined as

$$
p(x,y)=\frac1\pi e^{-x^2-y^2}
$$

We want to find $p(r,\phi)$, where

$$
r^2=x^2+y^2, \quad \tan \phi=\frac yx
$$

First consider the probability that $(x,y)\in A$ where $A \subset \mathbb{R}^2$. This is given before as

$$
P\{(x,y)\in A\}=\mu(A)=\int_A \frac 1\pi e^{-x^2-y^2}dxdy
$$

If we change variables, this probability cannot change. In order to do this, we need to use the **Jacobian**, more specifically its absolute determinant. The Jacobian for a coordinate change $(x,y)\mapsto(r,\phi)$ is defined as

$$
J=\frac{\partial (x,y)}{\partial (r,\phi)}=\begin{pmatrix}x_r & x_\phi \\ y_r & y_\phi\end{pmatrix}
$$

where $x_r=\partial x/\partial r$ etc. We use the inverse transformation, which is 

$$
x=r\cos\phi, \quad y=r\sin\phi
$$

to compute this as

$$
J=\begin{pmatrix}\cos\phi & -r\sin\phi \\ \sin\phi & r\cos\phi \end{pmatrix}
$$

which gives us an *absolute* determinant of $|J|=r$. We then multiply the term inside the integration by this constant, and plug in $r^2$ in the exponent to find

$$
\mu(A)=\int_A\frac 1\pi r e^{-r^2}drd\phi
$$

which gives us our desired result (remember the term inside the integral is $p(r,\phi)$).

---
