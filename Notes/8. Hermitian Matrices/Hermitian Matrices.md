---
dg-publish: true
---
#Notes 

A matrix $H=(h_{jk})$ is called **Hermitian** or **self-adjoint** if 

$$
H^\dagger=H \quad \text{or}\quad h_{jk}=h_{kj}^*
$$

If the elements of $H$ are real, then trivially $H=H^t$ or $h_{jk}=h_{kj}$ - i.e. $H$ is **symmetric**. As an example, we can write a general $3\times 3$ Hermitian matrix as

$$
\begin{pmatrix} a & x&y\\x&b&z\\y&z&c\end{pmatrix}
$$

where all terms here are *statistically independent*. 

We can see, and this will be important in a moment, that not all the elements of the array are independent. 

We will now look in depth at an example, the **Gaussian Orthogonal Ensemble (GOE)**. Let $X=(x_{jk})$ be an $N\times N$ *real, symmetric* matrix such that $x_{jk}=x_{kj}$. The number of *independent parameters* here will be ^90b71a

$$
\frac12 N(N+1)
$$

We can see in the $3\times 3$ example above, we have six independent parameters $a,b,c,x,y,z$. This matches the equation above as $\frac12 \times 3\times 4=6$. This means we can describe the matrix with a point in $\mathbb{R}^6$ with coordinate $(a,b,c,x,y,z)$. 

In general of course, a $N\times N$ matrix can be described by a point in $\mathbb{R}^{\frac12N(N+1)}$ with coordinates $(q_1,\dots ,q_{\frac{1}{2}N(N+1)})$.

We can also notice that these matrices are from a *subset* of the set of all Hermitian matrices - of course here only the ones with real entries. 

But what are these entries? Well, in the GOE, we define the variables as

$$
p(x_{jj})=\frac{1}{\sqrt{2\pi}}e^{-x_{jj}^2/2},\quad p(x_{jk})=\frac{1}{\sqrt{\pi}}e^{-x_{jk}^2} 
$$

In other words, the elements on the main diagonal are described by a normal distribution with variance $1$, and all other elements are described by a normal distribution with variance $1/2$.

This definition puts a probability measure on the space of all symmetric real matrices, or equivalently $\mathbb{R}^{\frac12N(N+1)}$. Thus we have made the set of all symmetric matrices into a **probability space**, called an **ensemble** in RMT. 

Since the terms are statistically independent from each other, we can just take the product of their individual p.d.f.s to find the joint p.d.f of the matrix elements.

$$
P(X)=\frac{1}{2^{N/2}\pi^{N(N+1)/4}}\prod^N_{j=1}e^{-x_{jj}^2/2}\prod_{1\leq j <k \leq N}e^{-x_{jk}^2}
$$


> [!help] Note
> The factor out the front comes from the factors in the original probability distribution. Clearly, we multiply by the $1/\sqrt{2\pi}$ a total of $N$ times, and we multiply by the $1/\sqrt{\pi}$ a total of $\frac{N+1}{2}$ times.
> The $j<k$ is important in the second product because we don’t want to overcount. The first product counts the main diagonal, and if we allowed $j=k$ then we would count this again in the second product.

We can then take this derivation a little bit further by noticing that

$$
\prod _{i=0}^{N}e^{\theta_i}=e^{\theta_0}e^{\theta_1}\dots e^{\theta_N}=e^{\theta_0 + \dots+\theta_N}=e^{\sum_{i=0}^N\theta_i}
$$

such that we can rewrite $P(X)$ as

$$
\begin{aligned}
P(X)&=\frac{1}{2^{N/2}\pi^{N(N+1)/4}}\exp\bigg[ -\sum^N_{j=1}\frac{x_{jj}^2}{2}-\sum_{1\leq j<k\leq N}x_{jk}^2\bigg ]
\\
&=\frac{1}{2^{N/2}\pi^{N(N+1)/4}}\exp\bigg[-\frac{1}{2}\bigg(\sum_{j=1}^Nx_{jj}^2+\sum^N_{j,k=1; j\neq k}x_{jk}^2\bigg )\bigg ]

\\
&= \frac{1}{2^{N/2}\pi^{N(N+1)/4}} \exp \bigg [-\frac{1}{2}\sum_{j,k=1}^Nx_{jk}x_{kj}\bigg ]\quad

\end{aligned}


$$


> [!help] Note
> In the second line, we have changed the limits of our integration, where we now count both sides of the symmetric matrix. To account for this, we include an extra factor of 1/2 outside the curved brackets. In the third line, we are exploiting the symmetry of the matrix to combine the two sums. Chose any $j,k$, you will see that it becomes part of either one of two sums above.

Now, recall that the **trace** of a $N\times N$ matrix is defined as the sum of its diagonal entries. For real symmetric matrices, we have the identity

$$
\text{Tr}X^2=\sum_{j,k=1}^Nx_{jk}x_{kj}
$$

which means that we can write $P(X)$ as

$$
P(X)=\frac{1}{2^{N/2}\pi^{N(N+1)/4}}\exp\Big (-\frac{1}{2}\text{Tr}X^2\Big )
$$

Whilst this j.p.d.f. does contain all the statistical information we need on the matrix $X$, it is not always convenient. We are after correlations of the spectrum (or rather the eigenvalues) of $X$, and how do we extract this information from $P(X)$? 

Well, a symmetric matrix has $N(N+1)/2$ independent parameters - why not choose them in a convenient way? In other words, we make a change of variables to a set of variables that *contains the eigenvalues*.