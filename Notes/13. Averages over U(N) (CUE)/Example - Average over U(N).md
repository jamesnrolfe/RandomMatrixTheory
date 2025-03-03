---
dg-publish: true
---
#Example

**Question**

Compute the average

$$
\left\langle\left(\prod_{j=1}^N\cos\theta_j\right)\right\rangle_{\mathrm{U}(N)}=\frac{1}{(2\pi)^NN!}\int_{[0,2\pi)^N}\left(\prod_{j=1}^N\cos(\theta_j)\right)\prod_{1\leq j<k\leq N}\left|e^{i\theta_k}-e^{i\theta_j}\right|^2d\theta_1\cdots d\theta_N
$$

**Solution**

Let's first apply **Heine's identity** from [[Averages over U(N) as determinants]]. 

$$
\begin{align}
\left\langle\left(\prod_{j=1}^N\cos\theta_j\right)\right\rangle_{\mathrm{U}(N)}&=\frac{1}{(2\pi)^NN!}\int_{[0,2\pi)^N}\left(\prod_{j=1}^N\cos(\theta_j)\right)\prod_{1\leq j<k\leq N}\left|e^{i\theta_k}-e^{i\theta_j}\right|^2d\theta_1\cdots d\theta_N \\
&= \det_{N\times N} \left( \frac{1}{2\pi} \int_{0}^{2\pi} \cos \theta \, e^{i(j-k)\theta}d\theta \right)
\end{align}
$$

We want to construct a Toeplitz matrix for this integral. First, let's consider expanding $\cos \theta$ in terms of complex exponentials.

$$
\cos \theta=\frac{1}{2} (e^{i\theta}+e^{-i\theta})
$$

such that the term inside the integral becomes 

$$
\cos \theta \, e^{i(j-k)\theta}=\frac{1}{2} (e^{i\theta}+e^{-i\theta}) e^{i(j-k)\theta} =\frac{1}{2}( e^{i(1+[j-k])\theta}+e^{i([j-k]-1)\theta})
$$

For $j=k$ (i.e. the main diagonal of the Toeplitz matrix) we can see that this reduces to $\cos \theta$. We can then see that 

$$
\frac{1}{2\pi}\int^{2\pi}_{0} \cos \theta d\theta =0
$$

For $k=j+1$ (top diagonal), this reduces to

$$
\frac{1}{2}( e^{i(1+[j-k])\theta}+e^{i([j-k]-1)\theta}) = \frac{1}{2}( e^{i(1-1)\theta}+e^{i(-1-1)\theta})=\frac{1}{2} (1+e^{-2i\theta})
$$

We can then see that

$$
\frac{1}{4\pi}\int_{0}^{2\pi} 1+e^{-2i\theta} d\theta= \left[ \theta - \frac{1}{2i} e^{-2i\theta} \right]^{2\pi}_{0}=\frac{2\pi}{4\pi}=\frac{1}{2}
$$

For $j=k+1$ (bottom diagonal), we get the same result. 

For any other diagonal, we get zero. How can we see this? If we consider the term as a Fourier series i.e.

$$
\frac{1}{2} e^{i{(j-k)}\theta}e^{i\theta}+\frac{1}{2} e^{i(j-k)\theta}e^{-i\theta}
$$

then we can see that the coefficients of this series are the $e^{i(j-k)\theta}$. However, we only have terms $e^{+i\theta}$ and $e^{-i\theta}$ here, and so if $j-k \neq \pm 1$, then the coefficient must be zero! Hence we can deduce that our Toeplitz matrix is tridiagonal, and looks like

$$
A_{n}=\begin{pmatrix}
0 & \frac{1}{2} & 0 & \dots &0  & 0 & 0\\
\frac{1}{2} & 0 & \frac{1}{2} & \dots & 0   & 0 & 0\\
0 & \frac{1}{2} & 0 & \dots &0  & 0 & 0\\
\vdots & \vdots & \vdots & \ddots&\vdots  & \vdots & \vdots\\
0 & 0 & 0 & \dots & 0 & \frac{1}{2} & 0 \\
0 & 0 & 0 & \dots &  \frac{1}{2}  & 0 & \frac{1}{2}\\
0 & 0 & 0 & \dots & 0 & \frac{1}{2} & 0
\end{pmatrix}
$$

and hence in the tridiagonal form, we have $a=0$ and $b=\frac{1}{2}$. The recurrence relation then becomes

$$
x_{n}=-\frac{1}{4}x_{n-2}
$$

The initial conditions are $x_{1}=a=0$ and $x_{2}=a^2-b^2=- \frac{1}{4}$. Hence, if $n$ is odd, then $x_{n}=0$. If $n$ is even, we can consider the pattern

$$
x_{2}=-\frac{1}{4}, \quad x_{4}=-\frac{1}{4} \times -\frac{1}{4} = \left( -\frac{1}{4} \right)^{2},\quad x_{6}=-\frac{1}{4} \times \left( -\frac{1}{4} \right)^2=\left( -\frac{1}{4} \right)^{3},\quad\dots
$$

and hence we see for any $n$ even, 

$$
x_{n} = \left( -\frac{1}{4} \right)^{n/2}
$$

Since the determinants of the Toeplitz matrix solve our original equation (remember it is just the determinant of the integral that is inside the matrix), we can then say that

$$
\left\langle\left(\prod_{j=1}^N\cos\theta_j\right)\right\rangle_{\mathrm{U}(N)}=\begin{cases}
0 & \text{if } N \text{ odd} \\
\left( -\frac{1}{4} \right)^{m} & \text{if } N =2m \text{ with } m\geq 1
\end{cases}
$$
