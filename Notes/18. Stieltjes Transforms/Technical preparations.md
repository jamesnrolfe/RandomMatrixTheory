#Notes 

For $f:\mathbb{R} \to \mathbb{C}$ integrable, its **Fourier transform** is $\hat{f}:\mathbb{R}\to \mathbb{C}$ defined by
$$
\hat{f}(x)=\int_{\mathbb{R}}f(y)e^{-2\pi ixy}dy
$$
>[!example] Example 18.1
>Consider the function $f(x)=e^{-x^{2}}$. Then, its Fourier transform is
>$$\hat{f}(x)=\int_{\mathbb{R}}e^{-y^{2}-2\pi ixy}dy=\sqrt{ \pi }e^{-\pi^{2}x^{2}}$$
>so for this choice of function, the transform is nearly identical (just scaled a bit). 

Compare this to the *characteristic function* of a random variable $Y$ with density function $\rho:\mathbb{R}\to [0,1]$:
$$\mathbb{E}[e^{i\lambda Y}]=\int_{\mathbb{R}}\rho(y)e^{i\lambda y}dy$$
and see that this looks similar to taking a Fourier transform.

>[!example] Example 18.2
>Take a Gaussian random variable $Y \sim \mathcal G\left( 0, \frac{1}{2} \right)$. Then, its *characteristic function* is 
>$$\mathbb{E}[e^{i\lambda Y}]=\int_{\mathbb{R}}e^{-y^{2}+i\lambda Y} \frac{dy}{\sqrt{ \pi }}=e^{-\lambda^{2}/4}$$

Our main tool in this section is, in many ways, an analogue of the Fourier transform/characteristic function. 

>[!info] Definition 18.3
>Let $\rho:\mathbb{R}\to \mathbb{R}_{\geq 0}$ be a non-negative integrable function. The function 
>$$S(z):= \int_{\mathbb{R}} \frac{\rho(\lambda)}{\lambda-z}d\lambda$$
>for $z$ *not purely real* i.e. $z \in \mathbb{C} \setminus \mathbb{R}$ is called the **Stieltjes transform** of $\rho$. 

^f1358f

Note that for fixed $z=x+iy$ with $y \neq 0$, we have the function $R \equiv R_{z}:\mathbb{R}\to \mathbb{C}$ defined by 
$$
R(\lambda)=\frac{1}{\lambda-z}= \frac{\lambda-x+iy}{(\lambda-x)^{2}+y^{2}}
$$
is a *bounded continuous* function. 

Hence, since $\rho$ is integrable, the Stieltjes transform exists for any $z \not\in \mathbb{R}$. We have some other properties of interest in the following propositions.

>[!info] Proposition 18.4 (a)
>$S$ is analytic in $\mathbb{C} \setminus \mathbb{R}$, and $(S(z))^{*}=S(z^{*})$ on the same domain.

>[!info] Proposition 18.4 (b)
>$$\mathrm{Im}(S(z))\times \mathrm{Im}z >0\quad \text{ for }\mathrm{Im}z \neq 0$$

>[!info] Proposition 18.4 (c)
>$$|S(z)| \times |\mathrm{Im}z| \leq \int_\mathbb{R} \rho(\lambda)d\lambda$$
>for $\mathrm{Im}z\neq {0}$, in particular
>$$\lim_{ \eta \to +\infty } \eta|S(i\eta)|=\int_{\mathbb{R}}\rho(\lambda)d\lambda$$

^ec1e42

>[!info] Proposition 18.4 (d)
>If for some $\lambda \in \mathbb{R}$ there exists the non-tangential limit from the upper half plane, 
>$$\mathrm{Im} S_{+}(\lambda):= \lim_{ \varepsilon \downarrow 0 } \mathrm{Im}(S(\lambda+i\varepsilon))$$ 
>then we have the inversion idenitity
>$$\rho(\lambda)= \frac{1}{\pi}\mathrm{Im}S_{+}(\lambda)$$

^ad512d

We can think of $S$ as a kind of *moment-generating function*. Suppose that $\rho$ is [[Definitions#^05b4ac|compactly supported]], and let
$$
m_{k}(\rho) := \int_{\mathbb{R}} \lambda^{k} \rho(\lambda)d\lambda
$$

^f53f81

denote its moments (similar to before i.e. [[Real Wigner matrices - traces, moments and combinatorics#^moments|moments]] here). Then, if $\text{supp}(\rho)\subset[-R,R]$ (i.e. it is [[Definitions#^05b4ac|compactly supported]]) with $R>0$, then we have
$$
|m_{k}(\rho)| \leq R^{k}\int_{\mathbb{R}}\rho(\lambda)d\lambda
$$
>[!help] Note
> To see this, consider that if $\rho$ is non-zero everywhere outside $[-R,R]$, then the integral can be over the limits $\int^{R}_{-R}$ and return the same result. Hence, the maximum and minimum values of $\lambda$ are $R$ and $-R$, and so $|\lambda|\leq R$ always, and so we get the above relation. 

Then the generating function
$$
z \mapsto \sum_{k=0}^{\infty}m_{k}(\rho)z^{k},\quad|z|< \frac{1}{R}
$$

^230a8f

has a positive radius of convergence.
>[!help] Note
>Think of this as a power series where the coefficients are the moments. Since all the moments must be less than $R^{k}$, we can write the inner term as 
>$$m_{k}(\rho)z^{k}\leq (Rz)^{k}$$
>and hence $|z|< \frac{1}{R}$ for convergence.

In this case, using the geometric series expansion, we have
$$
S(z)=\int_{-R}^{R} \frac{\rho(z)}{\lambda-z}d \lambda = - \frac{1}{z}\int_{-R}^{R} \sum_{k=0}^{\infty} \left( \frac{\lambda}{z} \right)^{k}\rho(\lambda)d\lambda 
$$
and as long as $|z|>R$, the sum inside the integral is uniformly convergent, i.e. we can interchange the integral with the sum.
>[!help] Note
>To see this, remember we defined 
>$$S(z)= \int_{\mathbb{R}} \frac{\rho(\lambda)}{\lambda-z}d\lambda$$
>and we expand this out. Consider the term
>$$\frac{1}{\lambda-z}=-\frac{1}{z} \frac{1}{1-\frac{\lambda}{z}}$$
>Then, the standard geometric expansion is
>$$\frac{1}{1-x}=\sum_{k=0}^{\infty}x^{k}$$
>for $|x|<1$ and so
>$$\frac{1}{\lambda-z} = - \frac{1}{z} \sum^{\infty}_{k=0} \left( \frac{\lambda}{z} \right)^{k}$$
>which we see in the above. 

What then results is 
$$
S(z)=- \frac{1}{z} \sum_{k=0}^{\infty} \frac{1}{z^{k}} \int_{-R}^{R} \lambda^{k}\rho(\lambda)d\lambda= -\frac{1}{z} \sum_{k=0}^{\infty} \frac{m_{k}(\rho)}{z^{k}}$$
where we used the [[Technical preparations#^f53f81|definition of the moments]] from above. This is a convergent Laurent series expansion of $S(z)$ in a neighbourhood of $z=\infty$, in the variable $\frac{1}{z}$, whose coefficients are *almost* moments of $\rho$ (they are the moments with an extra factor of $-\frac{1}{z}$). This observation can be useful in calculating Stieltjes transforms. We will also use the following facts.

>[!info] Proposition 18.5
>If $X \sim \frac{1}{2}(N(0,1)+iN(0,1))$ denotes the complex Gaussian random variable whose real and imaginary parts are independent $N\left( 0, \frac{1}{4} \right)$ copies, then for any differentiable function $\varphi:\mathbb{C}^{2}\to \mathbb{C}$ that grows *at worst* polynomially at infinity with the same property for its derivative, then 
>$$\mathbb{E}[\varphi(X, X^{*})X]=\mathbb{E}[|X|^{2}]\mathbb{E}\left[  \frac{\partial}{\partial z^{*}}\varphi(z,z^{*}) \bigg|_{z=X}\right]$$
>>[!tldr]- Proof
>>The left hand side in the above equation equals, after integrating by parts in the complex plane $\mathbb{C}$,
>>$$\begin{align} \mathbb{E}[\varphi(X,X^{*})X] & = \frac{2}{\pi} \int _{\mathbb{R}}\int_{\mathbb{R}}\varphi(z,z^{*})ze^{-2|z|^{2}}d\mathrm{Re}(z)d\mathrm{Im}(z) \\& = \frac{1}{2} \frac{2}{\pi} \int_{\mathbb{R}}\int_{\mathbb{R}} \left[  \frac{\partial}{\partial z^{*}}\varphi(z,z^{*}) \right]e^{-2|z|^{2}}d\mathrm{Re}(z)d\mathrm{Im}(z) \end{align}$$
>>But, since $\mathbb{E}[|X|^{2}]=\frac{1}{2}$, the result follows readily. 

>[!info] Proposition 18.6
>Let $M \in \mathcal{H}_{N}$ be a complex Hermitian matrix of size $N\times N$ and let $R_{M}(z)$ denote its **matrix resolvent** i.e. the mapping
>$$R_{M}:\mathbb{C}\setminus \mathbb{R} \to \mathbb{C}^{N\times N}; z \mapsto (M-zI)^{-1}$$
> where $I=I_{N}$ is the $N\times N$ identity matrix. 
> We then have the following two properties.
> 1. For any $A,B \in \mathcal{H}_{M}$, and $z \not\in \mathbb{R}$, $$R_{B}(z)=R_{A}(z)-R_{B}(z)(B-A)R_{A}(z)$$
> 2. For any $M \in \mathcal{H}_{N}$ and $z \not\in \mathbb{R}$, with $R_{M}(z)=(R_{j,k}(z))^{N}_{j,k=1}$, $$||R_{M}(z)|| \leq \frac{1}{\mathrm{Im}(z)},\quad|R_{j,k}(z)| \leq \frac{1}{\mathrm{Im}(z)}\quad\text{for}\quad j,k = 1,\dots,N$$

^636d23

 
>[!example] Example 18.7
>Let $M= \begin{pmatrix}1 & i \\ -i & 2\end{pmatrix}$. Then, its matrix resolvent, given by $R_{M}(z)=(M-zI)^{-1}$ is
>$$R_{M}(z)= \begin{pmatrix}1-z & i \\ -i & 2-z\end{pmatrix}^{-1}$$
>This inverse always exists since $M$ is Hermitian, and so has real eigenvalues, and so if $z \not\in \mathbb{R}$ then $M-zI$ must have non-zero determinant and the corresponding matrix must be invertible. 

^31a73c

On the operator norm, if $M$ is a matrix with eigenvalue $\lambda$ and corresponding eigenvector $\boldsymbol{x}$, chosen with normalisation such that $||\boldsymbol{x}||=1$ (i.e. it is a unit vector), then for any eigenvalue of $M$ 
$$
||\lambda|| = |M \boldsymbol{x}|\leq \sup_{||\boldsymbol{v}||=1}=: ||M||
$$
which uses the [[Definitions#^bab57f|definition of the operator norm]]. So, the operator norm of a matrix is *always* at least as large as the modulus of its maximum eigenvalue (this is the **spectral radius**). However, if we can diagonalise $M$ by a unitary matrix $U$ (as we can if $M$ is Hermitian), then also $||M \boldsymbol{v}||=|| \bar{U}^{T} DU \boldsymbol{v}||=||\Lambda U \boldsymbol{v}||$ where $\Lambda$ is the diagonal matrix comprising the eigenvalues of $M$ i.e. $(\Lambda_{j,k})_{j,k=1}^{N}=\lambda_{j}\delta_{j,k}$. 

Hence, we can say that $||\Lambda U \boldsymbol{v}|| \leq |\lambda^{*}| ||\boldsymbol{v}||$ where $\lambda^{*}$ is the maximal (in modulus, so positive or negative) eigenvalue, using again that matrices preserve vector length. Thus in the case of a Hermitian $M$, the operator norm *equals* the spectral norm.

The utility of the [[Technical preparations#^f1358f|Stieltjes transform]] in RMT stems from the following observation which allows us to derive *global scaling results*.

Let $\bar{\mathcal{N}}_{N}$ denote the [[Spectral Statistics#^caaef8|normalised counting measure]] of the eigenvalues $\lambda_{1},\dots,\lambda_{N}$ of some Hermitian random matrix $M \in \mathcal{H}_{N}$. We may write
$$
\bar{\mathcal{N}}_{N}(\Delta)= \frac{1}{N} \sum_{j=1}^{N}\chi_{\Delta}(\lambda_{j})=\int_{\mathbb{R}}\chi_{\Delta}(x) \left[  \frac{1}{N} \sum_{j=1}^{N} \delta_{\lambda_{_{j}}}(x) \right]dx
$$
for $\Delta \subset \mathbb{R}$. We defined here the "delta mass" $\delta_{a},a \in \mathbb{R}$ with $\int_{\mathbb{R}}\delta_{a}(x)dx=1$ and $\int_{\mathbb{R}}f(x)\delta_{a}(x)dx=f(a)$ (essentially $\delta_{a}$ puts all the "mass" of a function at $a$ and nowhere else).

We can use this to say that we can view 
$$
\varrho_{N}=\sum_{j=1}^{N} \frac{\delta_{\lambda_{j}}}{N}
$$
as the density of the random variable $N_{n}$ and thus compute the Stieltjes transform
$$
S_{N}(z):= \int_{\mathbb{R}} \frac{\varrho_{N}(x)}{x-z}dx = \frac{1}{N}\sum_{j=1}^{N} \frac{1}{\lambda_{j}-z}= \frac{1}{N}\mathrm{Tr}(R_{M_{N}}(z))
$$

^4247d5

where in the last equality, we have used the [[Technical preparations#^636d23|definition of the matrix resolvent]]. Since $S_{N}(z)$ is then essentially a moment generating function for the normalised counting function, we can try to study it to infer information back about the distribution of $\bar{N}_{N}$. For example, we can study convergence properties of the random variable $S_{N}(z)$ in some domains of the complex plane, prove a limit theorem, show that the limit is again a Stieltjes transform of some density and ultimately compute the same density via the inversion identity in [[Technical preparations#^ad512d|Proposition 18.4 (d)]]. In the next section, we will carry out the necessary steps for the GUE, recovering similar results to those in chapter 16.
