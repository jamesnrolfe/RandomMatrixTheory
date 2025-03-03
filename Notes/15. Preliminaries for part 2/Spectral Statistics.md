#Notes 

In the first part of the course, we saw exact results - i.e. those that are valid for matrices with fixed dimensions. Whilst it would be nice to think about matrices of finite size, in reality, it is often a lot simpler to talk about matrices that are *infinite* in dimension.
##### Quantities
Here we will collect some quantities that are widely studied in RMT. 

To begin with, it turns out that a number of spectral properties of random matrices can be formulated and studied in therms of the **counting measure** of their eigenvalues.

Given a matrix (random or deterministic) of dimension $N$, say $M_{N}$, we write $\lambda_{j}(M_{N}),j=1,\dots,N$ for its eigenvalues. This is often simplified to just $\lambda_{j}$ when context is sufficient. 


> [!info] Definition 15.1: Counting measure
> Let $(\lambda_{1},\dots,\lambda_{N}) \in \mathbb{R}^N$ denote the eigenvalues of a real symmetric / complex Hermitian matrix $M_{N}$ of size $N\times N$. The **counting measure**, $\mathcal{N}_{N}$ of its eigenvalues is
> 
$$\mathcal{N}_{N}(\Delta) := \Big|  \big (\ell \in \{1,\dots,N\}:\lambda_{\ell}\in \Delta \big) \Big|$$
where $\Delta$ is an interval of $\mathbb{R}$ and the **normalised counting measure** $\bar{\mathcal{N}}_{N}$ of its eigenvalues is
$$\bar{\mathcal{N}}_{N}(\Delta):= \frac{1}{N} \mathcal{N}_{N}(\Delta)$$
Simply put, the counting measure tells us how many eigenvalues lie in the region $\Delta$, and the normalised counting measure tells us the *fraction* of the eigenvalues that lie in that region (see [[Spectral Statistics#^E15-2a| Example 15.2 (a)]]).

If $M_{N}$ is a random matrix, then the counting measure then the counting measure $\mathcal{N}_{N}(\Delta)$ of its eigenvalues is a random variable (a measurable function) for a given interval $\Delta$ and we shall index our eigenvalues in a nondecreasing order

$$
-\infty<\lambda_{1}(M_{N})\leq \dots \leq \lambda_{N}(M_{N})<\infty
$$

i.e. the eigenvalues are indexed in increasing order.


> [!example] Example 15.2 (a)
> Take the matrix 
> $$\begin{pmatrix}7 & 6 \\ -4 & -3 \end{pmatrix}$$
> such that $\lambda_{1}=1$, $\lambda_{2}=3$. In this case, we have
> $$\mathcal{N}_{2}([0,2])=1; \quad \bar{\mathcal{N}}_{N}([0,2])=\frac{1}{2}$$
>  since only one eigenvalue lies in this region $[0,2]$, which is $\frac{1}{2}$ of the number of eigenvalues in total. 
>  We might also say
>  $$\mathcal{N}_{2}([-\infty,0.5] \cup [\pi, 101] )=0; \quad \bar{\mathcal{N}}_{2}([-\infty, 0.5]\cup[\pi,101])=0$$
>  where we recall that $A\cup B$ denotes that an element belongs to $A$ and $B$. 
>  We could also say
>  $$\mathcal{N}_{2}(\mathbb{R})=2; \quad \bar{N}_{2}(\mathbb{R})=1$$  
> 
^E15-2a


> [!Example] Example 15.2 (b) 
> Take the matrix
>  $$\begin{pmatrix} B_{1} & B_{2} \\
 B_{2}  & B_{1}
\end{pmatrix}$$
where $B_{1}, B_{2}$ are independent standard Bernoulli random variables (taking the values 0 and 1 with probability $\frac{1}{2}$ each).
We have four possible matrices each occurring with probability $\frac{1}{4}$, $$\begin{align}
\begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix};&\quad \lambda_{1,2}=1\\ \\
\begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix};&\quad\lambda_{1,2}=1,-1\\  \\
\begin{pmatrix}1 & 1 \\ 1 & 1\end{pmatrix}; & \quad \lambda_{1,2}= 0,2\\ \\
\begin{pmatrix}0 & 0  \\ 0 & 0\end{pmatrix}; &\quad \lambda_{1,2}=0 \\
\end{align}$$
Hence our possible spectra are $\{ 0 \}$, $\{ 1 \}$, $\{ 1,-1 \}$ or $\{ 0,2 \}$. 
Since this matrix is random, *the associated counting measure is also random.* Indeed, by considering cases we have that if $\Delta_{1},\Delta_{-1} \subset \mathbb{R}$ such that $1\not\in \Delta_{1}$ and $-1 \not\in \Delta_{-1}$ (i.e. $\Delta_{1}$ is defined such that it contains all values *except* 1), then 
$$P(\mathcal{N}_{2}(\Delta_{1})=1)=\frac{1}{2};\quad P(\mathcal{N}_{2}(\Delta_{-1})=1)=\frac{3}{4}$$
i.e. there is a 50% chance that there is 1 eigenvalue in $\Delta_{1}$, coming from $\{ 0 \}$ and $\{ 1,-1 \}$ - i.e. the two spectra of the four that contain exactly 1 eigenvalue that is not equal to 1. 
See [[Coded Example 15.2 (b)]].


^E15-2b

We can generalise this counting measure $\mathcal{N}_{N}(\Delta)$. Let's consider it as a function of the **indicator function** $\chi_{\Delta}$ where

$$
\text{given } \Delta \subset \mathbb{R}, \chi_{\Delta} :\mathbb{R}\to \mathbb{C} \text{ is } \chi_{\Delta}(x)=1 \text{ if } x \in \Delta \text{ and } \chi_{\Delta}(x)=0 \text{ if } x \not\in \Delta
$$

Essentially, this states that $\chi_{\Delta}(x)=1$ if $x$ is in the interval $\Delta$, otherwise it is zero (so a top-hat function).

This allows us to take more general view of $\mathcal{N}_{N}$ as a function of a wider class of functions called **test functions**. This can be thought of (this is not a proper definition per. se.) as a function $\varphi:\mathbb{R}\to \mathbb{C}$ which is complex valued, smooth (infinitely differentiable) whose support $\text{supp}(\varphi)$ is compact. 


> [!help] Compact supports
> A “test function of compact support” is just a smooth function that is zero outside some finite stretch of the real axis.


These functions are *nice* in that we can make examples that closely approximate the indicator function, but have the extra property that they are infinitely differentiable. 

![[Screenshot 2025-02-28 at 15.39.46.png]]


> [!info] Definition 15.3
> Given a real or complex Hermitian matrix $M_{N}$ with eigenvalues $\lambda_{1},\dots,\lambda_{N}$ and a test function $\varphi:\mathbb{R}\to \mathbb{C}$, the corresponding **linear statistic** $\mathcal{N}_{N}[\varphi]$ is
> $$\mathcal{N}_{N}[\varphi]:= \sum^{N}_{j=1} \varphi(\lambda_{j})=\mathrm{Tr}(\varphi(M_{N}))$$

^9cac02

If $\mathcal{P}_{N}$ is a probability measure, determining a random matrix, and $\mathbb{E}_{N}$ denotes the corresponding **expectation**, then we consider further the expectation $\mathbb{E}_{N}[\bar{\mathcal{N}_{N}}(\Delta)]$ of the *normalised* counting measure, and the **occupation probabilities** $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)$ for $\ell\in \{ 0,1,2,\dots,N \}$ of the counting measure of a given interval $\Delta$. In the case $\ell=0$ i.e. the interval contains *no* eigenvalues, this is referred to as the **gap probability** 

$$
\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=0)
$$

The linear statistic is symmetric functions of the eigenvalues (meaning that you reorder the eigenvalues in any way and get the same result). This is also true of certain jpdfs e.g. the Haar measure. When we did that, we also defined the **correlation functions**:

$$
R_{\ell}(x_{1},\dots,x_{\ell})=\frac{N!}{(N-\ell)!}\int _{\mathbb{R}^{N-\ell}} P_{N}(x_{1},\dots,x_{N})dx_{\ell+1}\dots dx_{N}
$$

defined for any $\ell=1,\dots,N$. Without the pre-factor, we define the **marginal densities** of $P_{N}$**:

$$
P_{N,\ell}(x_{1},\dots,x_{N}):= \int_{\mathbb{R}^{N-\ell}} P_{N}(x_{1}, \dots,x_{N}) dx_{\ell+1}\dots dx_{N},\quad \ell=1,2,\dots,N
$$

These three quantities (the occupation probabilities, the marginal probabilities and the correlation functions) are all connected. It is clear that the correlation functions and marginal densities are trivially related by a pre-factor. To see how they relate to the occupation probabilities, first notice that we can write the gap probability as 

$$
\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=0)=\mathbb{E}_{N}\left[ \prod^{N}_{j=1} (1-\chi_{\Delta}(\lambda_{j})) \right]
$$

> [!help] Note
> Here, $1-\chi_{\Delta}(\lambda_{j})$ is now 0 if there is an eigenvalue in $\Delta$, and 1 if there isn't. Just referring to the product inside, it can only be 1 if all the eigenvalues fall outside $\Delta$. However, as $\lambda_{j}$ is a random variable, the whole product essentially becomes a random variable. When we take the expectation value, we essentially receive a probability that there are no eigenvalues in $\Delta$ - exactly what we are trying to find. 

We can define a more general quantity by replacing $\chi_{\Delta}$ with a test function $\varphi:\mathbb{R}\to \mathbb{C}$

$$
\mathbb{E}_{N}\left[ \prod^{N}_{j=1} (1-\varphi(\lambda_{j})) \right]
$$

We can expand the product inside.

$$
\prod_{j=1}^{N} (1-\varphi(\lambda_{j}))=\sum_{\Omega \subset \{ 1,\dots,N \}}(-1)^{|\Omega|}\prod_{j \in \Omega} \varphi(\lambda_{j})
$$


and so 
 
$$
\begin{aligned}\mathbb{E}_N{\left[\sum_{\Omega\subset\{1,...,N\}}(-1)^{|\Omega|}\prod_{j\in\Omega}\varphi(\lambda_j)\right]}&=\mathbb{E}_N\left[\sum_{\ell=0}^N(-1)^\ell\binom{N}{\ell}\prod_{j=1}^\ell\varphi(\lambda_j)\right]\\&=\sum_{\ell=0}^N(-1)^\ell\binom{N}{\ell}\mathbb{E}_N\left[\prod_{j=1}^\ell\varphi(\lambda_j)\right]\\&=\sum_{\ell=0}^N(-1)^\ell\binom{N}{\ell}\int_{\mathbb{R}^\ell}P_{N,\ell}(x_1,\ldots,x_\ell)\prod_{j=1}^\ell\varphi(x_j)dx_j\end{aligned}
$$

where the term corresponding to $\Omega=\emptyset$ (the empty set) in the first equality, respectively to $\ell=0$ in the second and all later equalities, is 1. 

Now it is possible to define a generalisation of a directional derivative known as a **Gateaux derivative** or a **variational derivative** $\frac{\partial}{\partial \varphi}\Phi$. It is defined implicity as

$$
\frac{d}{d \epsilon} \Phi [\varphi+\epsilon \psi] \Bigg |_{\epsilon=0} = \lim_{ \epsilon \to 0 } \frac{\Phi[\varphi+\epsilon \psi]-\Phi[\varphi]}{\epsilon}=\int \psi(x) \frac{\partial}{\partial \varphi(x)}\Phi[\varphi]dx
$$

for a *functional* (a function of functions) acting on a certain set of functions $\varphi$. Applying this operator to the above shows that

$$
-\frac{\partial}{\partial \varphi(x_{1})}\mathbb{E}_{N}\left[ \prod_{j=1}^{N}(1-\varphi(\lambda_{j})) \right]=NP_{N,1} (x_{1})
$$

The following proposition is for the general case.


> [!info] Proposition 15.4
> For any $\ell = 1,2,\dots,N$ we have for any collection of distinct $(x_{1},\dots,x_{\ell})$
> $$(-1)^{\ell} \frac{\partial^{\ell}}{{\partial \varphi(x_{1}) \dots \partial \varphi(x_{\ell})}}\mathbb{E}_{N} \left[ \prod_{j=1}^{N} (1-\varphi(\lambda_{j})) \right]=N(N-1)\dots(N-\ell+1)P_{N,\ell}\left( x_{1}, \dots x_{\ell} \right)$$
> Notice that the right hand side is actual the $\ell$th correlation function (the pre-factor IS the coefficient in front here).

This establishes the claimed connection to the gap probabilities. It is not a far leap to tie in the occupation probabilities $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)$. We choose $\varphi=a \chi_{\Delta}$ for some real $a$. Then we have the following lemma.

> [!info] Lemma 15.5
> For any $\ell \in \{ 0,1,2,\dots,N \}$ and any interval $\Delta \subset \mathbb{R}$ we have
> $$\frac{(-1)^{\ell}}{{\ell!}} \frac{d^{\ell}}{{da^{\ell}}} \mathbb{E}_{N} \left[ \prod_{j=1}^{N} (1-a\chi_{\Delta}(\lambda_{j} )) \right]=\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta) = \ell )$$
> *Proof in lecture notes (page 7)*.

^28d6f4

Because of the above proposition and lemma, the functional $\mathbb{E}_{N}\left[ \prod_{j=1}^{N}(1-\varphi(\lambda_{j})) \right]$ plays the role of the **generating function** for both the marginal densities of the random variables $\{ \lambda_{j} \}_{j=1}^N$ and for the probability distribution of the counting measure of the eigenvalues. It can be thought of as a kind of Taylor series with coefficients $a^{n}$, and when we evaluate at the $\ell$th derivative, we get the probability of there being $\ell$ eigenvalues in $\Delta$. 

We can also say that

$$
(-1)^{\ell} \frac{\partial^{\ell}}{\partial \varphi(x_{1})\dots \partial \varphi(x_{N})}\mathbb{E}_{N}\left[ \prod_{j=1}^{N} (1-\varphi(\lambda_{j})) \right]=R_{\ell}(x_{1},\dots,x_{N})
$$
and

$$
\mathbb{E}_{N}\left[ \prod_{j=1}^{N} (1-\varphi(x_{j})) \right]=1+\sum^{N}_{\ell=1} \frac{(-1)^{\ell}}{\ell!}\int_{\mathbb{R}^{\ell}} R_{\ell} (x_{1,\dots,x_{\ell}})\prod_{j=1}^{\ell} \varphi(x_{j})dx_{j} 
$$

^d91146

##### In practice: an application to i.i.d. random variables

We now consider *independent, identically distributed (i.i.d.) random variables*. Let $(\lambda_{j})^{N}_{j=1}$ be a collection of (possibly $N$ dependent) i.i.d. real-valued random variables with common law $F_{N}$ (this is another way of saying they have the same distribution according to $F$, so $F$ might be a normal distribution, or uniform etc.). We will define the *diagonal* $N\times N$ random matrix $M_{N}$ as follows:

$$
M_{N}=(\zeta_{j,k})^{n}_{j,k=1}\quad\quad\quad\zeta_{j,k} := \begin{cases}
\lambda_{j} & \text{if } j=k \\
0 & \text{if } j \neq k
\end{cases}
$$

And so the diagonal elements are just the eigenvalues (random variables).

Recall that we said 

$$
\bar{\mathcal{N}}_{N}(\Delta):= \frac{1}{N} \mathcal{N}_{N}(\Delta)
$$

and so here

$$
\bar{\mathcal{N}}_{N}(\Delta)=\frac{1}{N}\sum_{j=1} ^{N} \chi_{\Delta} (\lambda_{j})
$$

> [!help] Note
> To see this, remember $\chi_{\Delta}(\lambda_{j})=1$ if $\lambda_{j}$ is in the interval $\Delta$. And so the sum is just counting the number of eigenvalues in $\Delta$ - and normalisation happens via the $\frac{1}{N}$.
> 

We can say that

$$
\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)] = \mathbb{E}_{N}[\chi_{\Delta}(\lambda_{1})]=\mathcal{P}_{N}(\lambda_{1}\in \Delta) \equiv F_{N}(\Delta)
$$


> [!help] Note
> To see this, remember we are using independent, *identically distributed* random variables. And so we can drop the sum inside, since all the eigenvalues have the exact same probability distribution and so summing over more and more wont change the expected outcome.
> The reason the probability equals $F_{N}(\Delta)$ is because we assume that it is some *normalised* distribution, and so we say that $F_{N}(\Delta)$ is essentially the area under the distribution in the interval $\Delta$ - which gives us a probability of $\lambda_{j}$ falling in there (since they are distributed according to $F_{N}$). 

We can also see that

$$
\begin{align}
\text{Var}_{N}[\bar{\mathcal{N}}_{N}(\Delta)] & = \mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)^{2}]-\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]^2 \\ \\

 & = \mathbb{E}_{N}[(\bar{\mathcal{N}}_{N}(\Delta)-\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)])^2] \\
 \\
 & = \frac{1}{N}F_{N}(\Delta)(1-F_{N}(\Delta))
\end{align}

$$

where we have already said that $\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=F_{N}(\Delta)$ above.

Similarly, the occupation probabilities, including the gap probability are

$$
\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)=\binom{N}{\ell}(F_{N}(\Delta))^{\ell}(1-F_{N}(\Delta))^{N-\ell}
$$

arising from [[Spectral Statistics#^28d6f4|Lemma 15.5]]. 

Let's further assume that $F_{N}$ has a probability density $\rho_{N}$ i.e. $F_{N}(\Delta)=\int_{\Delta} \rho_{N}(x)dx$, then also 

$$
\mathbb{E}_{N}\left[ \prod_{j=1}^{N} (1-\varphi(\lambda_{j}) \right]=\left( 1-\int_{\mathbb{R}}\rho_{N}(x)\varphi(x)dx \right)^N
$$

> [!help] Note
> Since all the $\varphi(\lambda_{j})$ are the same, we can say 
> $$\mathbb{E}_{N}\left[ \prod_{j=1}^{N} (1-\varphi(\lambda_{j}) \right]= \mathbb{E}_{N}[(1-\varphi(x))^{N}] = (\mathbb{E}_{N}[1-\varphi(x)])^N=\left( 1-\int_{\mathbb{R}}\rho_{N}(x)\varphi(x)dx \right)^N$$
> where the final integral is just the expectation value of the function $\varphi(x)$ with respect to the probability density $\rho_{N}$. We can take $\mathbb{E}_{N}$ inside because it is *linear*. 

Recall that a motivation for this part of the course is understanding how various statistical quantities behave in a *limiting sense*. In order to study the large $N$ behaviour of the above, we now put in place the following assumption underlying probability measures.

> [!info] Assumption
> The law $F_{N}$ weakly converges to some limiting law $F$ with density $\rho$, that is to say for every continuous and bounded function $\varphi:\mathbb{R}\to \mathbb{R}$ we have that 
> $$ \lim_{ N \to \infty } \int_{\mathbb{R}}\varphi(x)\rho_{N}dx=\int_{R}\varphi(x)\rho(x)dx$$
> or equivalently, with $F_{N}(x):=F_{N}((-\infty,x])$ and $F(x):= F((-\infty,x])$, denoting the distribution function of $F_{N}$ and $F$ respectively, we have a convergence of the distribution functions $\lim_{ N \to \infty }F_{N}(x)=F(x)$ at every continuity point $x$ of $F$.

Consequently, with this assumption in place on the law of $\lambda_{j}$, we have as $N\to \infty$ 
$$
\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=F_{N}(\Delta)=\int_{\Delta}\rho_{N}(x)dx \to \int_{\Delta}\rho(x)dx=F(\Delta)
$$

> [!help] Note
> Essentially all this is saying is that as $N \to \infty$, $F_{N} \to F$. 

Moreover, by **Chebyshev's inequality** and the above, for any $\epsilon > 0$, $\Delta \subset \mathbb{R}$ and $N \geq N_{0}$ sufficiently large, 

$$
\mathcal{P}_{N}(|\bar{\mathcal{N}}_{N}(\Delta)-\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]>\epsilon) \leq \frac{4}{\epsilon^{2}} \text{Var}_{N}(\bar{N_{c}(\Delta)})=\frac{4}{\epsilon^{2}N} F_{N}(\Delta)(1-F_{N}(\Delta))
$$

so the right hand side vanishes for large $N$. This shows that $\bar{\mathcal{N}}_{N}(\Delta)$ converges to $\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=F(\Delta)$ in probability i.e. the same counting measure satisfies a *weak law of large numbers* (*A.12 in lecture notes*). 

In the same way, we can apply the **classical Lindeberg central limit theorem** (*see A.14 in lecture notes*). Writing $\sigma^{2}:= F(\Delta)(1-F(\Delta))$ we find 

$$
\lim_{ N \to \infty } \mathcal{P}_{N}(\sqrt{ N }(\bar{\mathcal{N}}_{N}(\Delta)- F_{N}(\Delta))\leq x)=\frac{1}{\sigma \sqrt{ 2\pi }} \int_{-\infty}^{x}e^{-\frac{1}{2} (y/\sigma)^2}dy
$$

valid for any fixed $x \in \mathbb{R}, \Delta \subset \mathbb{R}$. This tells us that the normalised counting measure, once properly centered and normalised, *converges to a Gaussian random variable* of zero mean and with variance equal to $F(\Delta)(1-F(\Delta))$. 

Consider now the gap probability in our diagonal matrix $M_{N}$. 

$$
\mathcal{P}_{N}  (\mathcal{N}_{N}(\Delta)=0) = (1-F_{N}(\Delta))^N
$$

> [!help] Note
> Recall that 
> $$\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta)=\ell)=\binom{N}{\ell}(F_{N}(\Delta))^{\ell}(1-F_{N}(\Delta))^{N-\ell}$$
> Plug in $\ell=0$ and see what happens - it converges to the above.

We have then

$$
\lim_{ N \to \infty } \mathcal{P}_{N}(\mathcal{N}(\Delta )=0)=\begin{cases}
0 & F(\Delta )>0 \\
1 & F(\Delta)=0
\end{cases}
$$

> [!help] Note
> If $F(\Delta)=0$ then $(1-F_{N}(\Delta))^N=1$, and if it is greater than zero, then the exponent will always cause it to converge to zero.

In the limiting case, there is a probability zero that *no eigenvalues of $M_{N}$ fall in $\Delta$* if $F(\Delta)>0$. 


> [!example] Example 15.6
> Suppose we have diagonal matrix as before
> $$M_{N}=\begin{pmatrix}\lambda_{1} & 0 & \dots & \dots & 0 \\
0 & \lambda_{2} & 0 & \dots & 0 \\
\vdots  & \ddots &  & \ddots & \vdots \\
0  & \dots & \dots & 0 & \lambda_{N}\end{pmatrix}$$
where the diagonal entries $\lambda_{j}$ are distributed Binomially i.e. they are Binomial random variables with unit means such that $\lambda_{j} \sim \text{Bin}\left( N, \frac{1}{N} \right)$.
> >[!help] Reminder
> > Binomial random variables have two inputs: the number of events $N$ and the probability of "success" - here $\frac{1}{N}$. The probability that $\lambda_{j}$ takes a particular value $\kappa$ where $\kappa=0,1,2,\dots N$ is 
> > $$\mathcal{P}(\lambda_{j}=\kappa)=\binom{N}{\kappa}p^{\kappa}(1-p)^{N-\kappa}$$
> > where $p=\frac{1}{N}$ in this case.
> 
> So the eigenvalues can have integer values of $0 \to N$ with a probability governed by a Binomial distribution. 
> We can then say that 
> $$\bar{\mathcal{N}}_{N}([0,N])=\frac{1}{N} \sum_{j=1}^{N}\chi_{[0,N]}(\lambda_{j})=1$$
> which is essentially just saying that all the eigenvalues *have* to fall in the range $[0,N]$ - which makes sense if they are *only* allowed to be in that range. We could also say things like
> $$\bar{\mathcal{N}}_{N}([-2,-1])=0$$
> since it is impossible for eigenvalues to fall outside the range $\{ 0,\dots,N \}$.
> Let's consider some general $\Delta =[a,b]$, where $0 \leq a<b \leq \infty$. What would the expected value of the normalised counting measure be? 
> $$\begin{align}
> \mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)] & = \mathcal{P}_{N}\left( \text{Bin}\left( N, \frac{1}{N} \right) \in [a,b]\right) \\
 & = \sum_{[a] \leq j \leq [b]} \binom{N}{j} \frac{1}{N^{j}}\left( 1-\frac{1}{N} \right)^{N-j}
> \end{align}$$
> where we have essentially said that this expected value is equal to the probability that a binomial distributed variable falls in the desired region - which works when we use i.i.d. random variables like we are here. The second line is essentially counting only the random variables that fall in the desired region. Remember, the term inside the sum is a probability - not the value itself - so we get back a probability over a region - $\Delta$!
> So, we have created a formula for the expected value, which we can then use to work out other things (remember we called it a "generating function"). For example
> $$\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta )=0)=(1-\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)])^N$$





