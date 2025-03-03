#Notes 
Let’s say we are given the p.d.f. 

$$
P_1(H)=\frac{1}{2\pi^{3/2}}\exp\left(-\frac{1}{2}\operatorname{Tr}H^2\right)
$$

from [[The 2 by 2 Gaussian ensemble]]. Now, we want to know how the eigenvalues $\lambda _1$ and $\lambda_2$ are distributed.

We define $P_1(\lambda_1, \lambda_2)$ as the joint p.d.f., and then

$$
P_1(\lambda_1, \lambda_2) d\lambda_1d\lambda_2
$$

tells us that a random matrix drawn from our ensemble has eigenvalues lying within the small intervals $[\lambda_1, \lambda_1+d\lambda_1]$ and $[\lambda_2,\lambda_2+d\lambda_2]$.

For a $2\times 2$ matrix, we have three independent variables, $h_{11}, h_{22}$ and $h_{12}$. 

We can diagonalise $H$ (such that all non-main diagonal terms are zero) by multiplying it by orthogonal matrices.

$$
O^t HO=\begin{pmatrix} \lambda_1 & 0 \\ 0 & \lambda _2\end{pmatrix} = \text{diag}(\lambda_1, \lambda_2)
$$

where

$$
O=\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos \theta \end{pmatrix}
$$

Just like above we could also define $H$ in terms of other independent parameters - and we might chose $\lambda_1$, $\lambda_2$ and $\theta.$ Here, $\lambda_1$ and $\lambda_2$ define the eigenbasis of $H$, and $\theta$ describes the angle at which this eigenbasis is rotated. This is enough information to determine every possible $H$.

So, we want to change the variables we describe $H$ with from $h_{11}, h_{22}$ and $h_{12}$ to $\lambda_1$, $\lambda_2$ and $\theta$. 

In terms of independent parameters, we can rearrange the above expression for $\text{diag}(\lambda_{1},\lambda_{2})$. If we work out the right hand term, we can find that

$$
H=O\,\text{diag}(\lambda_1,\lambda_2) O^t
$$

$$
H=\begin{pmatrix} h_{11} & h_{12} \\ h_{12} & h_{22} \end{pmatrix} = \begin{pmatrix} \lambda_1 \cos^2\theta+\lambda_2\sin^2\theta & \frac{1}{2}\sin 2\theta(\lambda_1 - \lambda_2) \\ \frac{1}{2}\sin 2\theta(\lambda_1 - \lambda_2) & \lambda_1 \sin^2\theta + \lambda_2\cos^2\theta\end{pmatrix}
$$

and so we find 

$$
\begin{aligned}\mathrm{h_{11}}&=\lambda_1\cos^2\theta+\lambda_2\sin^2\theta\\h_{22}&=\lambda_1\sin^2\theta+\lambda_2\cos^2\theta\\h_{12}&=\frac{1}{2}\sin2\theta\left(\lambda_{1}-\lambda_{2}\right)\end{aligned}
$$

as our coordinate transform.

Now consider $\text{Tr}\, H^2$. We can note that $\text{Tr}\, ABA^{-1}=\text{Tr}\, B$. Hence

$$
\text{Tr}\, H^2=\text{Tr}\, (O\,\text{diag}(\lambda_1^2,\lambda_2^2)O^t)=\text{Tr}\,  \text{diag}(\lambda_1^2,\lambda^2_2)=\lambda_1^2+\lambda_2^2
$$

and so 

$$
P_1(H)=\frac{1}{2\pi^{3/2}}\exp\left(-\frac{1}{2}\operatorname{Tr}H^2\right)=\frac{1}{2\pi^{3/2}}\exp\left[-\frac{1}{2}\left(\lambda_1^2+\lambda_2^2\right)\right]
$$

When we change variables and integrate, we must remember the Jacobian. The Jacobian for this transformation is 

$$
\begin{aligned}J(\lambda_{1},\lambda_{2},\theta)&=\frac{\partial(h_{11},h_{22},h_{12})}{\partial(\lambda_{1},\lambda_{2},\theta)}\\&=\begin{pmatrix}\cos^2\theta&\sin^2\theta&\sin2\theta(\lambda_2-\lambda_1)\\\sin^2\theta&\cos^2\theta&-\sin2\theta(\lambda_2-\lambda_1)\\\frac{1}{2}\sin2\theta&-\frac{1}{2}\sin2\theta&-\cos2\theta(\lambda_2-\lambda_1)\end{pmatrix}\end{aligned}
$$

We then can show that

$$
\begin{aligned}&|\det J(\lambda_1,\lambda_2,\theta)|=|\lambda_2-\lambda_1|\times\begin{vmatrix}\cos^2\theta&\sin^2\theta&\sin2\theta\\\sin^2\theta&\cos^2\theta&-\sin2\theta\\\frac{1}{2}\sin2\theta&-\frac{1}{2}\sin2\theta&-\cos2\theta\end{vmatrix}\end{aligned}
$$

So we have separated out some variables - the term on the right depends only on $\theta$, and the term on the left depends only on $\lambda_1$ and $\lambda_2$. Interestingly, we can’t separate $\lambda_1$ and $\lambda_2$ further - they are *correlated*! This is expected in a way - we know there is some kind of repulsion which means that they must each know where the other one is!

It turns out that the $\theta$ term here is equal to one, but this is not the case generally. And so the absolute value of the determinate of the Jacobian is $|\lambda_2-\lambda_1|$. Remember we wanted to find $P_1(\lambda_1,\lambda_2)$, but we currently have an equation for 

$$
P_1(\lambda_1,\lambda_2,\theta)d\lambda_1 d\lambda_2d\theta  =\frac{1}{2\pi^{3/2}}\left|\lambda_{2}-\lambda_{1}\right|\exp\left[-\frac{1}{2}\left(\lambda_{1}^{2}+\lambda_{2}^{2}\right)\right]d\lambda_{1}d\lambda_{2}d\theta
$$

so we need to integrate over $\theta$ in some region to obtain our desired result. We restrict $\theta$ to $[0,\pi/2)$ here. This is because when rotating a symmetric $2\times 2$ matrix, we obtain the same value for $H$ four times in a full rotation, so convention states that we only consider the possible values once. 

Then, we can do the integration, and we obtain

$$
P_1(\lambda_1,\lambda_2)=\frac{1}{4\sqrt{\pi}}\left|\lambda_2-\lambda_1\right|\exp\left[-\frac{1}{2}\left(\lambda_1^2+\lambda_2^2\right)\right]
$$

We can see the repulsion here clearly. 

This procedure generalises to $N$ dimensions, but is just harder to do. 

A $N\times N$ symmetric matrix has $N(N+1)/2$ independent elements, as we’ve seen. 

In short, the Jacobian of the transformation from the $h_{jk}$ terms to the eigenvalues $\lambda_j$ and $N(N-1)/2$ real variables (like $\theta$ in the example above) which we label here $p_k$ that parametrize the degrees of freedom of the eigenvectors *factorises into the product* 

$$
\left(\prod_{1\leq j<k\leq N}|\lambda_k-\lambda_j|\right)f(p_1,\ldots,p_{N(N-1)/2})
$$

i.e. the product of the spacings of the eigenvalues multiplied by some function describing the real parameters. 

This allows us to easily integrate over the parameters $p_j$ to obtain 

$$
P_1(\lambda_1,\dots,\lambda_N)=C \prod_{1\leq j < k\leq N}|\lambda_k-\lambda_j| \exp \bigg ( -\frac{1}{2}\sum_{j=1}^N \lambda_j^2 \bigg )
$$

where we have noted that 

$$
\exp\left(-\frac{1}{2}\operatorname{Tr}X^2\right)=\exp\left(-\frac{1}{2}\sum_{j=1}^N\lambda_j^2\right)
$$

The exponential part of the joint probability density function  depends on the particular measure we have chosen (in this case Gaussian variables). However, the factor $\prod_{1\leq j < k\leq N}|\lambda_k-\lambda_j|$ comes from the Jacobian, and therefore only depends on the symmetries or geometry of the ensemble. 

The product 

$$
\Delta_N(x_1, \dots,x_N):= \prod_{1\leq j<k\leq N}(x_k-x_j)=\det V
$$

^1dbc40

is a **Vandermonde determinant**. That is, it is the determinant of the **Vandermonde matrix** 

$$
V=\begin{pmatrix}1&x_1&x_1^2&\cdots&x_1^{N-1}\\1&x_2&x_2^2&\cdots&x_2^{N-1}\\1&x_3&x_3^2&\cdots&x_3^{N-1}\\.&...&...&...&...\\1&x_N&x_N^2&\cdots&x_N^{N-1}\end{pmatrix}
$$

or equivalently $V=(x_{j}^{k-1})$, where $j$ parametises the rows and $k$ the columns. The product $\prod_{1\leq j < k\leq N}|\lambda_k-\lambda_j|$ is therefore the absolute value of the Vandermonde determinant. 

We will now define the **Gaussian Unitary Ensemble (GUE)** as the set of all *complex $N\times N$ Hermitian* matrices with the following joint probability distribution function for the matrix elements ^15b039

$$
\begin{aligned}P_{2}(H)&=\quad\frac{2^{N(N-1)/2}}{\pi^{N^{2}/2}}\prod_{j=1}^{N}\exp(-h_{jj}^{2})\prod_{1\leq j<k\leq N}\exp(-2|h_{jk}|^{2})\\&=\quad\frac{2^{N(N-1)/2}}{\pi^{N^{2}/2}}\exp(-\mathrm{Tr}H^{2})\end{aligned}
$$

We could do very similar calculations for the GUE as the GOE. We would find the j.p.d.f. of the eigenvalues to be

$$
P_2(\lambda_1,\lambda_2)=\frac{1}{\pi}(\lambda_1-\lambda_2)^2\exp\left(-\lambda_1^2-\lambda_2^2\right)
$$

This is similar to the GOE, however now the “repulsion term” is squared (amongst other things). This is down to complex numbers existing as two dimensional numbers, and so now there are more degrees of freedom in the eigenvalues. So, we would expect different repulsion behaviour.