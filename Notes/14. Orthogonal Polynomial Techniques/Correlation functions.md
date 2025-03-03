---
dg-publish: true
---
#Notes 

The next important fact we will demonstrate is that the **kernel** $K_{N}(\lambda,\mu)$ from [[The joint probability density function as a determinant]] satisfies the conditions for [[Gaudin's Lemma]], where

$$
K_{N}(\lambda,\mu)= (w(\lambda)w(\mu))^{\frac{1 }{ 2}} \sum^{N-1}_{j=0} \frac{p_{j}(\lambda) p_{j}(\mu)}{(p_{j},p_{j})}

$$

We want to show that 

1. $$\int_{J}f(x,y)f(y,z)dy=Kf(x,z)$$
2. $$\int_{J}f(y,y)dy=D$$

Let's first attempt condition 1. We have

$$
\begin{align}
\int_{J}K_{N}(\lambda,\mu)K_{N}(\mu,\nu)d\mu &=\int_{J}(w(\lambda)w(\mu))^{\frac{1}{2}} \sum^{N-1}_{j=0} \frac{p_{j}(\lambda)p_{j}(\mu)}{(p_{j},p_{j})}\times(w(\mu)w(\nu))^{\frac{1}{2} } \sum^{N-1}_{k=0} \frac{p_{k}(\mu)p_{k}(\nu)}{(p_{k},p_{k}) }d\mu \\ \\

&=\int_{J}(w(\lambda)w(\nu))^{\frac{1}{2} } w(\mu ) \sum_{j,k=0}^{N-1} \frac{p_{j}(\lambda)p_{k}(\nu)}{(p_{j},p_{j})(p_{k},p_{k}) }p_{j}(\mu),p_{k}(\mu)d\mu \\ \\

&=(w(\lambda)w(\mu))^{\frac{1}{2}} \sum_{j,k=0}^{N-1} \frac{p_{j}(\lambda)p_{k}(\nu)}{(p_{j},p_{j})(p_{k},p_{k}) } \int_{J} w(\mu)p_{j}(\mu)p_{k}(\mu)d\mu \\ \\

&=(w(\lambda)w(\mu))^{\frac{1}{2}} \sum_{j,k=0}^{N-1} \frac{p_{j}(\lambda)p_{k}(\nu)}{(p_{j},p_{j})(p_{k},p_{k}) } (p_{j},p_{j})\delta_{jk} \\ \\

&= (w(\lambda)w(\mu))^{\frac{1}{2}} \sum_{j,k=0}^{N-1} \frac{p_{j}(\lambda)p_{k}(\nu)}{(p_{j},p_{j})(p_{k},p_{k}) } = K_{N}(\lambda,\nu)
\end{align}
$$

> [!help] Note
> Here we use a classic case of taking the integral inside the sum. From the third to the fourth line, we use $\int_{J}w(\mu)p_{j}(\mu)p_{k}(\mu)d\mu=(p_{j},p_{j})\delta _{jk}$ which essentially states that the integral vanishes if $j \neq k$, but if $j=k$ then the integral is equal to $(p_{j}, p_{j})$ which is obvious when you remember that $(p_{j}, p_{k})=\int _{J} w(\lambda)p_{j}(\lambda)p_{k}(\lambda)d\lambda=N_{k} \delta_{jk}$. We also recall from [[Introducing orthogonal polynomials]] that $(p_{j},p_{j})=1$ for monic polynomials (which we use here).


as we require, and hence $K=1$ in Gaudin's lemma.

Now for condition 2. This is much simpler.

$$
\int_{J}K_{N}(\lambda,\lambda)d\lambda=\sum^{N-1}_{j=0} \frac{1}{(p_{j},p_{j})} \int_{J} w(\lambda)p_{j}(\lambda)p_{j}(\lambda)d\lambda=\sum^{N-1}_{j=0} 1=N
$$

and so $D=N$ in Gaudin's lemma. 

Let's assume that our j.p.d.f. is of the form of a normalisation constant multiplying our identity in [[The joint probability density function as a determinant]] i.e.

$$

P(\lambda_{1},\dots,\lambda_{N}) = C\prod^{N}_{l=1} w(\lambda_{l})\prod_{1\leq j<k\leq N} |\lambda_{k}-\lambda_{j}|^{2}

$$

Then, similar to how we approached this for in [[n-point correlation function as a determinant]], by repeatedly applying Gaudin's lemma we obtain 

$$
\begin{align}
\int_{J}\dots \int_{J} P(\lambda_{1},\dots,\lambda_{N})d\lambda_{n-1}\dots d\lambda _{N} &= C\left( \prod^{N-1}_{l=0} (p_{l},p_{l}) \right) \int_{J}\dots \int_{J} \det_{N\times N} (K_{N}(\lambda_{j},\lambda_{k}))d\lambda_{n+1}\dots d\lambda_{N} \\
&=C\left( \prod^{N-1}_{l=0}(p_{l},p_{l}) \right)(N-n)! \det_{n\times n} (K_{N}(\lambda_{j},\lambda_{k}))
\end{align}

$$

We can obtain the normalisation constant by integrating over $N$ variables (i.e. setting $n=0$).

$$
\int_{J}\dots \int_{J}P(\lambda_{1},\dots ,\lambda_{N})d\lambda_{1}\dots d\lambda_{N}=C\left( \prod^{N-1}_{j=0}(p_{j},p_{j}) \right)N!= 1
$$

> [!help] Note
> Remember the 1 at the end here comes from the fact that all the probabilities must sum to one.


which leads to 

$$
C=\left( \left( \prod^{N-1}_{j=0}(p_{j},p_{j}) \right)N! \right)^{-1}
$$

From the [[Spectral Correlation Functions|definition of the spectral correlation function]] we have 

$$
R_n(\lambda_1,\dots,\lambda_n)=\frac{N!}{(N-n)!}\int_{J}\dots \int_{J}P(\lambda_1,\dots,\lambda_N)d\lambda_{n+1}\dots d\lambda_N
$$

and so, combining what we have, we find that 

$$
\begin{align}
R_{n}(\lambda_{1},\dots,\lambda_{N})&=\frac{N!}{(N-n)!} C\left( \prod^{N-1}_{l=0}(p_{l},p_{l}) \right)(N-n)! \det_{n\times n}(K_{N}(\lambda_{j},\lambda_{k})) \\
&= N! \frac{1}{N!\prod^{N-1}_{j=0}(p_{j},p_{j})} \left( \prod^{N-1}_{l=0}(p_{l},p_{l}) \right) \det_{n\times n}(K_{N}(\lambda_{j},\lambda_{k})) \\
&=\det_{n\times n}(K_{N}(\lambda_{j},\lambda_{k}))
\end{align}

	$$

As eluded to before, this is not dissimilar to our CUE calculations. Actually, this is not a coincidence. We can put this in the setting of orthogonal polynomials on a circle. 

Let $w(\theta)$ be a positive periodic function, integrable in $[0,2\pi)$. We call it a weighting function on the circle. 

A polynomial of degree $k$ on the unit circle is defined by 

$$
\phi_{k}(z)=a_{k}z^k+a_{k-1}z^{k-1}+\dots+a_{0}
$$

where $z=e^{i\theta}$. It turns out that we can define orthogonal polynomials on the circle in an analogous way as on the line. 

We have the following theorem. 

Given an arbitrary weighting function $w(\theta)$, there exists a unique sequence of polynomials on the circle $\{\phi_{k}(\lambda)\}$ with the following properties:
1. the coefficient of $z^k$ in $\phi_{k}(z)$ is real and positive. 
2. the system $\{\phi_{k}(z)\}$ is orthonormal, i.e. 

$$
(\phi_{j},\phi_{k})=\frac{1}{2\pi}\int_{0}^{2\pi} w(\theta) \phi_{j}(\theta)\phi_{k}^*(\theta)d\theta=\delta_{jk}
$$

The techniques that led to 

$$
R_{n}(\lambda_{1},\dots,\lambda_{N})=\det_{n\times n}(K_{N}(\lambda_{j},\lambda_{k}))
$$

are identical if we replace the interval $J$ with the unit circle $\mathbb{R}$ or $\mathbb{Z}$.

The orthogonal polynomials for the CUE have $w(\theta)=1$.