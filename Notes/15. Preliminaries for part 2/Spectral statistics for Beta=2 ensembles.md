---
dg-publish: true
---
#Notes 

In this section, we will review and generalise some results from the first part of the course. Then, we apply orthogonal polynomials to understand various spectral statistics (e.g. the expected value of the normalised counting measure, or occupation probabilities) for $\beta=2$ ensembles like the GUE. 

##### Joint eigenvalue probability density

Recall that the [[Hermitian Matrices#^90b71a|Gaussian Orthogonal Ensemble]], GOE. This is the collection of all $N\times N$ symmetric matrices $M_{N}=(m_{ij})_{1\leq i,j\leq N}$ whose upper triangular entires are independently

$$
m_{jj} \sim \mathcal{G}(0,1)\quad\quad m_{ij} \sim \mathcal{G}\left( 0, \frac{1}{2} \right)\quad\quad 1 \leq i<j\leq N
$$

where $\mathcal{G}$ represents a Gaussian/normal distribution. 

As $M_{M}$ is symmetric, it has $\binom{N+1}{2}$ independent parameters. We can view the GOE as a probability space on $\mathbb{R}^{N(N+1)/2}$, with entries distributed according to the jpdf

$$
\begin{align}
P^{(1)}_{N}(\lambda_{1},\dots,\lambda_{N}) & =Z^{(1)} _{N} \prod_{1 \leq j<k\leq N} |\lambda_{k}-\lambda_{j}| \exp\left( -\frac{1}{2} \sum_{j=1}^{N} \lambda_{j}^2 \right) \\
  \\
& = Z^{(1)} _{N} |\Delta_{N}(\lambda_{1},\dots,\lambda_{N})| \exp\left( -\frac{1}{2} \sum_{j=1}^{N} \lambda_{j}^2 \right)
\end{align}

$$

where $Z^{(1)}_{N}$ is a normalisation factor (the relevance of the $^{(1)}$ will be made clear soon), and $|\Delta_{N}(\lambda_{1},\dots,\lambda_{N})$ is the [[The joint probability density function for the eigenvalues#^1dbc40|Vandermonde determinant]]. 

We also saw the [[The joint probability density function for the eigenvalues#^15b039|Gaussian Unitary Ensemble]], GUE, which is essentially the complex version of the GOE. It is the set of all $N\times N$ matrices $M_{N}=(m_{ij})$ that are *Hermitian* i.e. $m_{ij}=\bar{m}_{ji}$ with entries independently distributed according to 

$$
m_{jj}=\mathcal G \left( 0, \frac{1}{2} \right)\quad\quad m_{ij}=\mathcal G\left( 0, \frac{1}{4} \right)+i \mathcal G\left( 0, \frac{1}{4} \right)\quad\quad i \leq j<k\leq N
$$

The distribution of the off-diagonal entires is a centered complex Gaussian random variable of variance $\frac{1}{2}$. The jpdf for the matrix entries is 

$$\begin{align}
P^{(2)} _{N} (M_{N}) & = \prod_{j=1}^{N} \frac{1}{\sqrt{ \pi }}e^{-m_{jj}^{2}} \prod_{1\leq j < k \leq N} \frac{2}{\pi} e^{-2|m_{jk}|^2} \\
 \\
 & =2^{\frac{N(N-1)}{2}}\pi^{\frac{-N^{2}}{2}} \prod_{j=1}^{N} e^{-m_{jj}^{2}} \prod_{1\leq j<k\leq N} e^{2 \text{Re}(m_{ij}^2)+\text{Im}(m_{ij}^2)} \\
 \\
 & =2^{\frac{N(N-1)}{2}}\pi^{\frac{-N^{2}}{2}} \exp(- \mathrm{Tr}(M_{N}^2))
\end{align}
$$

Since we are dealing with complex matrix entries, when we integrate the density we have to integrate against

$$
dM_{N}=\prod_{j=1}^{N} dm_{jj} \prod_{1 \leq j<k \leq N} d(\mathrm{Re} (m_{ij}))d(\mathrm{Im}(m_{ij}))
$$

Again, we can write the joint pdf of the eigenvalues explicitly as

$$
\begin{align}
P^{(2)}_{N} (\lambda_{1},\dots,\lambda_{N}) & = Z_{N}^{(2)} \prod_{1\leq j<k\leq N} |\lambda_{k}-\lambda_{j}|^{2}\exp\left( -\sum_{j=1}^{N} \lambda_{j}^2 \right) \\
 \\
 & = Z_{N}^{(2)} |\Delta_{N}(\lambda_{1},\dots,\lambda_{N})|\exp\left( -\sum_{j=1}^{N} \lambda_{j}^2 \right) 
\end{align}
$$

where again $Z^{(2)}_{N}$ is some normalisation constant. 

The thing we will now say is that these two cases are simply *particular cases* of a generalised framework of *invariant ensembles*. 

>[!info] Definition 15.7
> Let $V:\mathbb{R}\to \mathbb{R}_{\geq 0}$ be a sufficiently continuous function. Let $S_{N}$ be the set of real symmetric $N\times N$ matrices, and $H_{N}$ be the same but for Hermitian matrices. 
> The **invariant ensembles** are defined on the set of $S_{N}$ or $H_{N}$ as the sets of random matrices whose joint probability density function on the entries is 
> $$P^{(\beta)} _{N} (M_{N}) = C^{(\beta)}_{N} \exp \left( - \frac{\beta}{2} \mathrm{Tr} (V(M_{N})) \right)$$
> The normalisation constant $C^{(\beta)}_{N}>0$ changes depending on the function $V$ - for $V(x)=x^2$ the constant $C_{N}^{(\beta)}$ is shown above for $\beta=1$ (GOE) and $\beta=2$ (GUE).

A word of caution - invariant ensembles to not *in general* arise from constructions such as the two above i.e. by filling real symmetric / complex Hermitian matrices with families of i.i.d. random variables. 


> [!info] Proposition 15.8
> Consider the invariant ensembles i.e. $N\times N$ random matrices whose joint density is given by $$P^{(\beta)} _{N} (M_{N}) = C^{(\beta)}_{N} \exp \left( - \frac{\beta}{2} \mathrm{Tr} (V(M_{N})) \right)$$ with $\beta=1$ on $S_{N}$ and with $\beta=2$ on $H_{N}$. Then, the joint density for the eigenvalues can be written as
> $$P_{N} ^{(\beta)}(\lambda_{1},\dots,\lambda_{N})=Z_{N}^{(\beta)} \exp \left( -\frac{\beta}{2} \sum_{j=1}^{N} V(\lambda_{j}) \right)|\Delta (\lambda_{1},\dots,\lambda_{N})|^{\beta},\quad\beta=1,2$$
>

^580567

We saw, for example, in the first part of course via explicit calculation that for $V(x)=x^2$, $Z_{2}^{(1)}=\frac{1}{4\sqrt{ \pi }}$. 

As we will often deal with orthogonal invariant functions of real symmetric matrices or with unitary invariant functions of complex Hermitian matrices, we emphasize that such (class) functions will depend *only on eigenvalues*! These functions can always be extended from the set defined by 

$$
-\infty<\lambda_{1}(M_{N})\leq \dots \leq \lambda_{N}(M_{N})<\infty
$$

to the whole of $\mathbb{R}^N$ as symmetric functions. 


> [!example] Example 15.9
> Take the counting measure $\mathcal{N}_{2}([a,b]):S_{2}\to \mathbb{C}$ on an interval $[a,b]$ acting on the set
> $$S_{2}=\bigg\{ \begin{pmatrix} x & y \\ y & x \end{pmatrix} ; x,y\in \mathbb{R}\bigg\}$$
> Since this function only depends on the eigenvalues of a given matrix, it is orthogonally invariant. 
> > [!help] Why?
> > The eigenvalues of this matrix remain unchanged by a unitary/orthogonal transformation, and hence since the function only counts eigenvalues in $[a,b]$, it is invariant under these transformations.
> 
> Given $S\in S_{2}$ with eigenvalues $\lambda_{1},\lambda_{2}\in \mathbb{R}$ then for $S$ we have 
> $$\mathcal{N}_{2}([a,b])=\begin{cases} 
 0 & \lambda_{1},\lambda_{2} \not\in [a,b]  \\
1 & \text{either one of } \lambda_{1} \text{ or } \lambda_{2} \text{ is in }[a,b] \text{ but not both} \\
2  & \lambda_{1},\lambda_{2} \in [a,b]\end{cases}$$
Therefore, we could define some function $f:\mathbb{R}^2\to \mathbb{C}$ such that$$f(x,y)=\begin{cases} 
 0 & x,y \not\in [a,b]  \\
1 & \text{either one of } x \text{ or } y \text{ is in }[a,b] \text{ but not both} \\ 
2  & x,y \in [a,b]\end{cases}$$

This allows us to state the following version of [[Spectral statistics for Beta=2 ensembles#^580567|Proposition 15.8]].


> [!info] Corollary 15.10
> Let $\Phi:S_{N}\to \mathbb{C}$ be an orthogonal invariant function *or* let $\Phi:H_{N}\to \mathbb{C}$ be a unitary invariant function, integratabtle with respect to $$P^{(\beta)} _{N} (M_{N}) = C^{(\beta)}_{N} \exp \left( - \frac{\beta}{2} \mathrm{Tr} (V(M_{N})) \right)$$
> Denote by $f:\mathbb{R}^N\to \mathbb{C}$ the symmetric function whose restriction by $-\infty<\lambda_{1}(M_{N})\leq \dots \leq \lambda_{N}(M_{N})<\infty$ is $\Phi$. Also denote by $\mathbb{E}_{\beta,N}[\Phi]$ the expectation with respect to $P^{(\beta)} _{N} (M_{N})$. 
> >[!help] Note
> > Basically, what we are saying here is that since $\Phi$ is a function on the eigenvalues, and since it doesn't change under orthogonal/unitary transformations, knowing $\Phi$ for the diagonal matrix (which we denote $f$) is enough to know $\Phi$ *everywhere*. "The restriction of $\Phi$ is $f$" essentially just means that when we look at $\Phi$ on diagonal matrices, it becomes $f(\lambda_{1},\dots,\lambda_{N})$.
> 
> Then
> $$\mathbb{E}_{\beta,N}[\Phi]=\int_{R^{N}} f(x_{1},\dots,x_{N})P^{(\beta)}_{N}(x_{1},\dots,x_{N})dx_{1}\dots dx_{N}$$
> where we said that $$P_{N} ^{(\beta)}(\lambda_{1},\dots,\lambda_{N})=Z_{N}^{(\beta)} \exp \left( -\frac{\beta}{2} \sum_{j=1}^{N} V(\lambda_{j}) \right)|\Delta (\lambda_{1},\dots,\lambda_{N})|^{\beta},\quad\beta=1,2$$
> 

We re-emphasise that the choice of quadratic $V(x)=x^2$ corresponds to the Gaussian invariant ensembles. In these cases, the normalisation constant is known explicitly as

$$
Z_{N}^{(\beta)}=(2\pi)^{-\frac{N}{2}} \left( \frac{\beta}{2} \right) ^{\frac{1}{4} (2N+\beta N(N-1))} \prod_{j=1}^{N} \frac{\Gamma\left( \frac{\beta}{2} \right)}{j\Gamma\left( \frac{\beta j}{2} \right)}
$$

where $\Gamma(z)$ is the **Gamma function** i.e. $\Gamma(n)=(n-1)!$ for integer $n$ and otherwise it is defined for general $z\in \mathbb{C}$ with positive real part via

$$
\Gamma(z)=\int ^{\infty}_{0} e^{-t}t^{z-1}  dt,\quad\mathrm{Re}(z)>0 
$$

##### Orthogonal polynomial techniques

Recall that we are interested mostly in the asymptotic properties of the eigenvalue distribution of $N\times N$ random matrices as $N$ tends to infinity. This means that we need an efficient method to compute integrals of the form seen earlier:

$$
\int_{R^{N}} f(x_{1},\dots,x_{N})P^{(\beta)}_{N}(x_{1},\dots,x_{N})dx_{1}\dots dx_{N}$$

which we recall gave us the expected value of $\Phi$. It turns out it is easier to do this for $\beta=2$ (i.e. GUE). In both cases, however, techniques using orthogonal polynomials are useful. 

We saw before in [[Orthogonal polynomial techniques]] that given some weight function $w:\mathbb{R}\to \mathbb{R}$ there exists an infinite sequence $(p_{j})^{\infty}_{j=0} \subset \mathbb{R}[x]$ of polynomials with real coefficients that satisfy various properties. Here we collect some of the important ones:


> [!check] Property 1
> The polynomial $p_{j}(x)=\gamma_{j,j}x^j+\gamma_{j-1,j}x^{j-1}+\dots+\gamma_{0},j$ has degree $j$ with leading coefficient $\gamma_{j}=\gamma_{j,j}>0$. 


> [!check] Property 2
> The collection $(p_{j})^{\infty}_{j=0}$ is a sequence of *orthonormal* polynomials (before we used monic polynomials and they were just orthogonal - now we define them such that they are normalised as well!) with respect to the given weight such that
> $$(p_{j},p_{k})=\int_{\mathbb{R}}p_{j}(x)p_{k}(x)w(x)dx=\delta_{j,k}\quad\forall\: j,k \in \mathbb{Z}_{\geq 0}$$


> [!check] Property 3
> The function
> $$K_{N}(x,y):= \sqrt{ w(x)w(y) } \sum_{j=0}^{N-1} \frac{p_{j}(x)p_{j}(y)}{(p_{j},p_{j})}=\sqrt{ w(x)w(y) }\sum_{j=0}^{N-1} p_{j}(x)p_{j}(y)  $$
> satisfies the conditions for [[Gaudin's Lemma]] 
> $$\int _{\mathbb{R}}K_{N}(x,x)dx=N$$
> $$\int_{\mathbb{R}}K_{N}(x,z)K_{N}(z,y)dz=K_{N}(x,y)$$
> for all $x,y \in \mathbb{R}$, and hence both the joint eigenvalue density and corresponding correlation functions $R_{n}$ (and so also the marginals, remember they are related only by a factor) for a jpdf of a particular shape (i.e. $\beta=2$) 
> $$P_{N}(x_{1},\dots,x_{N})=\frac{1}{N!}\prod_{j=1}^{N} w(x_{j})|\Delta(x_{1},\dots,x_{N})|^2$$
> can be expressed as a determinant involving the kernel for $w$:
> $$P_{N}(x_{1},\dots,x_{N})=\frac{1}{N!}\det_{N\times N}(K_{N}(x_{j},x_{k}))$$
> $$\mathcal{P}_{N} \propto R_{n}(x_{1},\dots,x_{N})=\frac{N!}{(N-n)!} \int_{\mathbb{R}}\dots \int_{\mathbb{R}}P(x_{1},\dots,x_{N})dx_{n+1}\dots dx_{N}=\det _{n\times n}(K_{n}(x_{j},x_{k}))$$

^5023fb



> [!check] Property 4
> There exists a sequence $(b_{j})^{\infty}_{j=0}$ of real numbers and a sequence $(a_{j})^{\infty}_{j=0}$ of non-negative real numbers such that the following three-term recurrence relation is valid for $j\in \mathbb{Z}_{\geq 0}$
> $$xp_{j}(x)=a_{j+1}p_{j+1}(x)+b_{j}p_{j}(x)+a_{j}p_{j-1}(x)$$
> where 
> $$\begin{align}a_{0} & =0 \\
 \\
a_{j} & = \int_{\mathbb{R}}xp_{j-1}(x)p_{j}(x)w(x)dx,\quad j\in \mathbb{Z}_{\geq 1}\\
 \\
b_{j} & = \int_{\mathbb{R}}p_{j}^{2 }(x)w(x)dx,\quad j \in \mathbb{Z}_{\geq 0}\end{align}$$
The kernel similarly satisfies 
$$K_{N}(x,y)=a_{N}\sqrt{ w(x)w(y) } \frac{p_{N}(x)p_{N-1}(y)-p_{N-1}(x)p_{N}(y)}{x-y}$$
This last relation is known as the **Christoffel-Darboux identity**. On the "diagonal", we have 
$$K_{N}(x,x)=a_{N}\left( \sqrt{ w(x)p_{N}(x) } \frac{d}{dx} (w(x)p_{N-1}(x))-\sqrt{ w(x)p_{N-1}(x) }  \frac{d}{dx}(w(x)p_{N}(x))\right)$$
which makes sense as it sort of does look like a chain rule.

^23a96c


> [!example] Example 15.11
> In this example, we will see that we can use orthogonal polynomials to show that
> $$P_{N}(x_{1},\dots,x_{N})=\frac{1}{N!} \det_{N\times N}(K_{N}(x_{j},x_{k}))$$
> for the jpdf $P(\boldsymbol{x})$. Previously in the first part of the course, we proved this using [[The Transposing Lemma]]. Now, we will do it using orthogonality.
> Let $w:\mathbb{R}\to \mathbb{R}$ be a weight function and $(p_{j})^{\infty}_{j=0}$ be a corresponding family of orthonormal polynomials, so $p_j(x)=\gamma_{j}x^{j}+\dots+\gamma_{0}$. Then, we can recall from [[Spectral statistics for Beta=2 ensembles#^5023fb|Property 3]] that $$P_{N}(x_{1},\dots,x_{N})=\frac{1}{N!}\prod_{j=1}^{N} w(x_{j})|\Delta(x_{1},\dots,x_{N})|^2$$
> The Vandermonde determinant here can be manipulated as follows:
> $$\begin{align} \Delta(x_{1},\dots,x_{N})  & = \det \begin{pmatrix} 1 & 1 & \dots & 1 \\ x_{1} & x_{2} & \dots & x_{N} \\ \vdots & \vdots & \ddots & \vdots \\ x_{1}^{N-1} & x_{2}^{N-1} & \dots & x_{N}^{N-1}
\end{pmatrix} \\  & = \frac{1}{\prod_{j=0}^{N-1} \gamma_{j}}\begin{pmatrix} p_{0}(x_{1}) & p_{0}(x_{2}) & \dots & p_{0}(x_{N}) \\ p_{1}(x_{1}) & p_{1}(x_{2}) & \dots & p_{1}(x_{N}) \\ \vdots & \vdots & \ddots & \vdots \\ p_{N-1}(x_{1}) & p_{N-1}(x_{2}) & \dots & p_{N-1}(x_{N})
\end{pmatrix}
\end{align}$$
> Thus, plugging this into our equation above for $P_{N}$ we find 
> $$P(x_{1},\dots,x_{N})=\frac{1}{N!}\left[\prod_{j=0}^{N-1} \frac{1}{\gamma_{j}^{2}} \right] (\det_{N\times N}(\sqrt{ w(x_{k}) }p_{j-1}(x_{k})))^{2}=\frac{1}{N!}\left[ \prod_{j=0}^{N-1} \frac{1}{\gamma_{j}^{2}} \right]\det_{N\times N}(K_{N}(x_{j},x_{k}))$$
> using the definition of the reproducing kernel $K_{N}$. By [[Andreief's Identity]] with $\psi_{j}(x)=\phi_{j}(x)=\sqrt{ w(x) }p_{j-1}(x)$ we find
> $$\begin{align} \frac{1}{N!}\int_{\mathbb{R}^{N}}\det_{N\times N} (f_{j}(x_{k}))\det_{N\times N}(g_{j}(x_{k}))dx_{1}\dots dx_{N} & = \det_{N\times N}\left( \int_{\mathbb{R}} f_{j}(x)g_{k}(x)dx \right) \\
 \\
& = \det_{N\times N}\left( \int_{\mathbb{R}}w(x)p_{j-1}(x)p_{k-1}(x)dx \right)=1\end{align}$$
and therefore 
$$\int_{\mathbb{R}^{N}}P(x_{1},\dots,x_{N})dx_{1}\dots dx_{N}=\frac{1}{N!}\left[ \prod_{j=0}^{N-1} \frac{1}{\gamma_{j}^{2}} \right]\int_{\mathbb{R}^{N}} (\det_{N\times N}(\sqrt{ w(x) }p_{j-1} (x_{k})))^{2}dx_{1}\dots dx_{N}=\prod_{j=0}^{N-1} \frac{1}{\gamma_{j}^{2}}$$
Finally, we see that the left hand side of the last set of equations *is* the density function integrated over the whole sample space and therefore is equal to 1. Hence $\gamma_{0}\dots \gamma_{N-1}=1$ i.e. the product $\prod_{j=0}^{N-1} \frac{1}{\gamma_{j}^2}=1$ and so 
$$P(x_{1},\dots ,x_{N})=\frac{1}{N!}\det_{N\times N}(K_{N}(x_{j},x_{k}))$$

^f64df4

Next is the notion of the **Fredholm determinant** of a continuous kernel function.


> [!info] Definition 15.12
> Let $J \subset \mathbb{R}$ be a compact interval; let $K:J\times J\to \mathbb{C}$ be a continuous function (kernel), and let $K_{J}$ be the associated integral operator i.e.
> $$(K_{J}f)(x):= \int_{J} K(x,y)f(y)dy,\quad x \in J$$
> acting on functions $f:J\to \mathbb{C}$ that are square integrable i.e.
> $$\int_{J}|f(x)|^{2}dx < \infty$$
> Then, the **Fredholm determinant** of the operator $K_{J}$ (or the kernel $K$) is 
> $$\det(I-K_{J}):= 1 + \sum^{\infty}_{\ell=1} \frac{(-1)^{\ell}}{\ell!}\left[ \int_{J^{\ell}} \det(K(x_{j},x_{k}))^{\ell}_{j,k=1} dx_{1}\dots dx_{\ell} \right]$$

In the above, it is not clear that the sum converges (infinite sums are usually a big "no-no"). However, since we are usually using the Fredholm determinant of the reproducing kernel $K_{N}$ which has a sum up to $N$ in it, the infinite sum *truncates* at $\ell=N$ and hence it doesn't matter that this sum is infinite. However, in the general case, convergence must be verified, for instance by **Hadamard's inequality** (*see A.2 in lecture notes*).

The next proposition displays the utility of orthogonal polynomials in the study of unitary invariant matrix models i.e. when it comes to the calculation of the averages 

$$\mathbb{E}_{\beta,N}[\Phi]=\int_{R^{N}} f(x_{1},\dots,x_{N})P^{(\beta)}_{N}(x_{1},\dots,x_{N})dx_{1}\dots dx_{N}$$

for $\beta=2$. For example, as we will see, it will allow for another method of showing 

$$\mathcal{P}_{N} \propto R_{n}(x_{1},\dots,x_{N})=\frac{N!}{(N-n)!} \int_{\mathbb{R}}\dots \int_{\mathbb{R}}P(x_{1},\dots,x_{N})dx_{n+1}\dots dx_{N}=\det _{n\times n}(K_{n}(x_{j},x_{k}))$$

in [[Spectral statistics for Beta=2 ensembles#^5023fb|property 3]]. 


> [!info] Proposition 15.13
> Consider the invariant ensemble 
> $$P_{N}^{(\beta)}(M_{N})=C_{N}^{(\beta)}\exp\left( -\frac{\beta}{2}\mathrm{Tr}(V(M_{N})) \right)$$
> with $\beta=2$ and continuous $V:\mathbb{R} \to \mathbb{R}_{\geq 0}$. Let $(p_{j})^{\infty}_{j=0}$ be the family of orthonormal polynomials with respect to the weight $w(x)=\exp(-V(x))$. 
> $$\int_{\mathbb{R}}p_{j}(x)p_{k}(x)e^{-V(x)}=\delta_{i,j}$$
> for all $j,k \in \mathbb{Z}_{\geq 0}$ and all $n \in \mathbb{N}$.
> Then, the generating function of the marginal densities for $P^{(2)}_{N}$ 
> $$\mathbb{E}_{N}\left[ \prod^{N}_{j=1} (1-\varphi(\lambda_{j})) \right]$$
> can be expressed as a Fredholm determinant
> $$\mathbb{E}_{N}\left[ \prod^{N}_{j=1} (1-\varphi(\lambda_{j})) \right] = \det(I-K_{N,J}M_{\varphi})$$
> where $M_{\varphi}$ is the operator of multiplication by the test function $\varphi$ of compact support $J=\text{supp}(\varphi)$ and the integral operator $K_{N,J}$ is defined by the reproducing kernel.
> (*Proof in lecture notes pages 19-20*)

^919524


> [!example] Example 15.14
> Recall that in [[Spectral statistics for Beta=2 ensembles#^f64df4|example 15.11]] we saw a reproof using orthogonal polynomials that the jpdf for eigenvalues of $\beta=2$ invariant ensembles has a determinantal form
>  $$P(x_{1},\dots ,x_{N})=\frac{1}{N!}\det_{N\times N}(K_{N}(x_{j},x_{k}))$$
>  Earlier in the course, we have also seen via [[Gaudin's Lemma]] that the marginal densities and correlation functions can be expressed via determinants 
>  $$P_{N,\ell}(x_{1},\dots,x_{\ell})=\frac{(N-\ell)!}{N!}\det(K_{N}(x_{j},x_{k}))^{\ell}_{j,k=1}$$
>  $$R_{\ell}(x_{1},\dots,x_{\ell})=\det(K_{N}(x_{j},x_{k}))^{\ell}_{j,k=1}$$
>  for $\ell=1,\dots,N$. 
>  However, from [[Spectral Statistics#^d91146|Spectral Stastics]] we have 
>  $$\mathbb{E}_{N}\left[ \prod_{j=1}^{N} (1-\varphi(x_{j})) \right]=1+\sum^{N}_{\ell=1} \frac{(-1)^{\ell}}{\ell!}\int_{\mathbb{R}^{\ell}} R_{\ell} (x_{1,\dots,x_{\ell}})\prod_{j=1}^{\ell} \varphi(x_{j})dx_{j} $$
> Therefore the determinantal formula for $R_{\ell}(x_{1},\dots,x_{\ell})$ and hence $P_{N,\ell}$ also follows immediately upon comparison with 
>  $$\mathbb{E}_{N}\left[ \prod^{N}_{j=1} (1-\varphi(\lambda_{j})) \right] = \det(I-K_{N,J}M_{\varphi})$$
> which is underpinned by orthogonal polynomial structure.
>  

^6f152f

[[Spectral statistics for Beta=2 ensembles#^919524|Preposition 15.13]] allows us to express the quantities of primary interest:
- the expectation of the normalised counting measure $\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]$
- the occupation probabilities $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)$
- the gap probability $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=0)$
- the variance of the linear statistic $\text{Var}_{N}(\mathcal{N}_{N}(\phi))$
via the reproducing kernel. This is because, as we saw in [[Spectral Statistics]] all these quantities are connected via the generating function $\mathbb{E}_{N}\left[ \prod(1-\varphi(x_{j})) \right]$.


> [!tip] Notation
> Before we state the relationships properly, we record the following rescaling of the polynomials $$\psi_{j}(x) := \sqrt{ w(x) } p_{j}(x)$$ where $(p_{j})_{j \geq 0}$ are orthonormal with respect to the weight $w$. This rewriting is simply for convenience. 

There are three things to prove here, so we separate them out. For all of them, consider an invariant ensemble with $\beta=2$.

> [!info] Theorem 15.15 (a)
> For any bounded function $\varphi:\mathbb{R}\to \mathbb{C}$ the expectation of the linear statistic equals 
> $$\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)]=N \int_{\mathbb{R}} \varphi(x) \rho_{N}(x)dx$$
> where for any $x \in  \mathbb{R}$
> $$ \begin{align} \rho_{N}(x) := \frac{1}{N}K_{N}(x,x)  & = \frac{1}{N} \sum_{j=0}^{N-1} (\psi_{j}(x))^{2} \\
 \\
 & = \frac{a_{N}}{N}\left( \psi_{N-1}(x) \frac{d}{dx}\psi_{N}(x)-\psi_{N}(x) \frac{d}{dx}\psi_{N-1}(x) \right)\end{align}$$
 which comes from the [[Spectral statistics for Beta=2 ensembles#^23a96c|Christoffel-Darboux identity]] above. 
 In particular, the expectation of the normalised counting measure can be written as 
 $$ \mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=\int_{\Delta}\rho_{N}(x)dx$$
 Further, we have the inequality $|K_{N}(x,y)|^{2}\leq K_{N}(x,x)K_{N}(y,y)=N^{2}\rho_{N}(x)\rho_{N}(y)$.
 >> [!tldr] Proof of $\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)]=N \int_{\mathbb{R}} \varphi(x) \rho_{N}(x)dx$
 >> We can firstly note that $\mathcal{N}_{N}(\Delta)=\sum_{j=1}^{N}\varphi(\lambda_{j})$ from [[Spectral Statistics#^9cac02|definition 15.3]]. It follows, using linearity of the expectation value that 
 >> $$\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)] = \sum^{N}_{j=1} \mathbb{E}_{N}[\varphi(\lambda_{j})]$$
 >> All the eigenvalues here are *identically distributed* (although not independently for $\beta=2$ ensembles). The expectation value inside the sum can be written as 
 >> $$\mathbb{E}_{N}[\varphi(\lambda_{j})]=\int_{R^{N}} \varphi(x_{1})P_{N}(x_{1},\dots x_{N}) \prod_{j=1}^{N} dx_{j}$$
 >> >[!help] Note
 >> >This is just a usual way to find an expectation value - the integral over the function with respect to the distribution (for all variables here since it is a jpdf). We only use $x_{1}$ since all the $\varphi(\lambda_{j})$s should be distributed in the same way (identically distributed).
 >> 
 >> Notice how there is no $j$ dependence in this integral! So, it can be taken outside the sum above!
>> $$\begin{align}\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)] & =\int_{R^{N}} \varphi(x_{1})P_{N}(x_{1},\dots x_{N}) \prod_{j=1}^{N} dx_{j} \sum_{j=1}^{N} 1 \\
 & = N\int_{R^{N}} \varphi(x_{1})P_{N}(x_{1},\dots x_{N}) \prod_{j=1}^{N} dx_{j}\end{align}$$
 >We recall that $P_{N,1}$ is the 1-point marginal probability density 
 >$$P_{N,1}= \int_{\mathbb{R}^{N-1}}P_{N}(x,x_{2},\dots,x_{N})dx_{2}\dots dx_{N}$$
 >which we can essentially "factor out" of the integral, making it
 >$$\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)]=N\int_{\mathbb{R}}\varphi(x)P_{N,1}(x)dx$$
 > Recall from [[Spectral statistics for Beta=2 ensembles#^6f152f|example 15.14]] that 
 > $$P_{N,\ell}(x_{1},\dots,x_{\ell})=\frac{(N-\ell)!}{N!}\det(K_{N}(x_{j},x_{k}))^{\ell}_{j,k=1}$$
 > and in the case that $\ell=1$ as we have here
 > $$\mathcal{P}_{N,1} = \frac{1}{N} K_{N}(x,x)$$
 > and so
 > $$\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)]=\int_{\mathbb{R}} \varphi(x)K_{N}(x,x)dx$$
 > In the theorem, we define $\rho_{N}(x)=\frac{1}{N}K_{N}(x,x)$ and so this above statement is equal to the theorem, as required. 
 > The other stages of the theorem come directly from this. 
 > 


>[!info] Theorem 15.15 (b)
>The **variance** of the linear eigenvalue statistic is
>$$\text{Var}_{N}(\mathcal{N}_{N}[\varphi])=\frac{1}{2} \int_{\mathbb{R}^{2}} |\varphi(x)-\varphi(y)|^{2} K_{N}^{2}(x,y) dxdy$$
>(*proof in lecture notes page 23*)


> [!info] Theorem 15.15 (c)
> The probability $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)$ that the interval $\Delta$ contains exactly $\ell$ eigenvalues is
> $$\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)=\frac{(-1)^{\ell}}{\ell!} \frac{d^{\ell}}{da^{\ell}} \det (I-K_{N, \Delta}M_{\Phi_{a}})\Bigg |_{a=1}$$
> where $\det(I-K_{N,\Delta}M_{\Phi_{a}})$ is the [[Spectral statistics for Beta=2 ensembles#^919524|Fredholm determinant]] with $\Phi_{a}=a\chi_{\Delta}$ for $a \in \mathbb{R}$ and $\text{supp}(\varphi)=J=\Delta$, and $K_{N,\Delta}$ is the reproducing kernel. 
> In particular, the gap probability of the ensemble is 
> $$\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=0)=\det(I-K_{N,\Delta})=1+\sum_{\ell=1}^{N} \frac{(-1)^{\ell}}{\ell!}\int_{\Delta^{\ell}}\det(K_{N}(x_{j},x_{k}))^{\ell}_{j,k=1} \prod_{m=1}^{\ell} dx_{m} $$
> 
