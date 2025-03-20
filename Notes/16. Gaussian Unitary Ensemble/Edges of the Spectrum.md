---
dg-publish: true
---
#Notes 

In [[Bulk of the spectrum]] we presented the basic properties of the GUE *bulk eigenvalues* i.e. all eigenvalues in $|x|<\sqrt{ 2 }$, where the limiting density of states

$$
\lim_{ N \to \infty } \rho_{N}(x)=\frac{1}{\pi} \sqrt{ (2-x^2)_{+} }
$$

was strictly positive. [[Bulk of the spectrum#^b35f3e|Theorem 16.4]] regards the global regime, and [[Bulk of the spectrum#^0e8e95|Theorem 16.6]]the local one. Now, we consider analogous results concerning the *edges of the support* i.e. at the positions $\pm \sqrt{ 2 }$. 

We state initially that as the matrix size grows, since the density of the states will converge to the [[Bulk of the spectrum#^b35f3e|Wigner semicircle law]], it is fairly obvious that the maximum eigenvalue *will* be at $\sqrt{ 2 }$, and similarly the minimum at $-\sqrt{ 2 }$. How can we prove this formally? 


> [!info] Theorem 16.7
> Consider a matrix $M_{N}$ (of size $N\times N$) drawn from the rescaled GUE. Denote $\lambda_{N}=\lambda_{N}(M_{N})$ and $\lambda_{1}=\lambda_{1}(M_{N})$ its maximum and minimum eigenvalues respectively. Then, with probability 1, 
> $$\lim_{ N \to \infty } \lambda_{N}=\sqrt{ 2 };\quad\quad\lim_{ N \to \infty } \lambda_{1}=-\sqrt{ 2 }$$
> >[!tldr] Proof
> > We will focus on the first equality (maximum eigenvalue) since the proof of the second one is done in exactly the same way.
> > We then want to prove that 
> > $$\mathcal{P}_{N}(\lim_{ N \to \infty } \lambda_{N}=\sqrt{ 2 })=1$$
> > > [!help] Note
> > > $\limsup_{ n \to \infty }$ essentially means the maximum value that the function reaches infinitely often. To see this in practice, consider the sequence $a_{n}=(-1)^n$. This sequence does not have a well defined limit - since it keeps bouncing between $-1$ and $1$ for each ascending $n \in \mathbb{N}$. However, it does have a superior limit, which is $1$, since this is the highest value that the function reaches (infinitely often). 
> > > The opposite of this is $\liminf_{ n \to \infty }$, which is exactly the same but the *minimum value* (so here would be $-1$).
> > 
> > We can say that to prove the above statement, it is sufficient to show that
> > $$\mathcal{P}_{N}(\limsup_{ N \to \infty } \lambda_{N} \leq \sqrt{ 2 })=1\quad \text{and}\quad\mathcal{P}_{N}(\liminf_{ N \to \infty } \lambda_{N} \geq \sqrt{ 2 })=1$$
> > i.e. the superior limit is at most $\sqrt{ 2 }$ (the sequence doesn't go above $\sqrt{ 2 }$) and the inferior limit is at least $\sqrt{ 2 }$ (the sequence doesn't go below $\sqrt{ 2 }$). Then, this by definition means that the limiting value of $\lambda_{N}$ is $\sqrt{ 2 }$. The inferior limit is really hard to prove, and beyond the scope of this course, so here we take it as fact. We can however, prove the superior limit. 
> > We can use the **Borel-Cantelli lemma** (*see lecture notes Theorem A.11*). Essentially, this states that if 
> > $$\sum_{N\geq {1}}\mathcal{P}_{N}(\limsup_{ N \to \infty } \lambda_{N}>\sqrt{ 2 }) < \infty$$
> > then 
> > $$\mathcal{P}_{N}(\limsup_{ N \to \infty } \lambda_{N} \leq \sqrt{ 2 })=1$$
> > This basically says that if it is *very unlikely* (bit of a simplification, its to do with infinities) for an eigenvalue to fall beyond $\sqrt{ 2 }$, then we can say with certainty that the eigenvalue must be less than or equal to $\sqrt{ 2 }$.  So, all we need to do is prove that the sum above converges. We will rewrite it as
> > $$\sum_{N \geq 1}\mathcal{P}_{N}(\lambda_{N} \geq \sqrt{ 2 }(1+\epsilon))$$
> > for some $\epsilon>0$. We will use **Markov's inequality** (second line) (*see lecture notes A.5*) to say that
> > $$\begin{align} \mathcal{P}_{N}(\lambda_{N} \geq \sqrt{ 2 }(1+\epsilon)) & = \mathcal{P}_{N}(\mathcal{N}_{N}([\sqrt{ 2 }(1+\epsilon),\infty])\geq 1) \\ \\
 & \leq N \mathbb{E}_{N}[\bar{\mathcal{N}}_{N}([\sqrt{ 2 }(1+\epsilon),\infty])] \\ \\
 & =N \int_{\sqrt{ 2 }(1+\epsilon)}^{\infty}\rho_{N}(x)dx\end{align}$$
 >> with the final equality using the density for the mean normalised counting measure given in [[Spectral statistics for Beta=2 ensembles#^4cee7d|Theorem 15.15 (a)]]. One can show by applying the [[Rescaling the GUE#^0c5426|Plancherel-Rotach asymptotics]] (as well as [[Bulk of the spectrum#^15ae9d|Proposition 16.3]], the **Cauchy-Schwarz inequality** and **Laplace's method of integral approximation**) that the bound 
 >> $$\rho_{N}\left( \sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}} \right) \leq c_{1}N^{- \frac{1}{3}}  \frac{1}{s}  e^{-c_{2}s^{\frac{3}{2}}}$$
 >> is valid for some $c_{1},c_{2}>0$ and sufficiently large $s,N$. Let's do a coordinate transform to put the integral in this form. Consider $x \to \sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}}$. Then
 >> $$dx = \frac{1}{\sqrt{ 2 }N^{\frac{2}{3}}}ds$$ 
 >> and the limits become $\epsilon N^{\frac{2}{3}}$ and $\infty$. Then
 >> $$\begin{align} \mathcal{P}_{N}(\lambda_{N} \geq \sqrt{ 2 }(1+\epsilon)) & =N \int_{\sqrt{ 2 }(1+\epsilon)}^{\infty}\rho_{N}(x)dx \\
 \\
 & = \frac{N^{\frac{1}{3}}}{\sqrt{ 2 }}\int^{\infty}_{\epsilon N^{\frac{2}{3}}} \rho_{N}\left( \sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}} \right)ds  \\
 \\
 & \leq c_{1}\int^{\infty}_{\epsilon N^{\frac{2}{3}}} \frac{1}{s}e^{-c_{2}s^{\frac{3}{2}}}ds \\
 \\
 & = \frac{2}{3} \frac{c_{1}}{c_{2}} \epsilon^{- \frac{3}{2}} \frac{1}{N} e^{-N c_{2} \epsilon^{\frac{3}{2}}}\end{align}$$
 >>> [!help] Note
 >>> In the third line, we used the inequality from above. The integral can be computed via integration by parts (done [[Edge integral.pdf|here]]).
 >>
 >>The last line guarantees convergence (it is *rapidly summable*) in the sum above (and since our actual thing is less than this, it will also converge). Hence, we have proved that  
 >>$$\mathcal{P}_{N}(\limsup_{ N \to \infty } \lambda_{N} \leq \sqrt{ 2 })=1$$

^faf64e

We can say that the limits given in [[Edges of the Spectrum#^faf64e|Theorem 16.7]]:

$$\lim_{ N \to \infty } \lambda_{N}=\sqrt{ 2 };\quad\quad\lim_{ N \to \infty } \lambda_{1}=-\sqrt{ 2 }$$

imply the relation

$$
\lim_{ N \to \infty } \mathcal{P}_{N} (\lambda_{N} \leq x)=\lim_{ N \to \infty } \mathcal{P}_{N}(\mathcal{N}((x,\infty))=0)=\begin{cases}
0, & x \leq \sqrt{ 2 } \\
1,  & x>\sqrt{ 2 }
\end{cases}
$$

This is basically saying that as $N$ grows to infinity, the probability that the biggest eigenvalue is smaller than $\sqrt{ 2 }$ is zero, and the probability that it is smaller than some number that is *bigger than $\sqrt{ 2 }$* is 1. So in the limit, $\lambda_{N}=\sqrt{ 2 }$. 

This is a global regime concerning the support of the limiting normalised counting measure of eigenvalues. We now discuss the corresponding *local regime results*, zooming in around the edge. For the next theorem, take $M_{N}$ from the rescaled GUE. The following limits then hold.

>[!info] Theorem 16.8 (a)
>For the density $\rho_{N}$ of the mean normalised counting measure in [[Spectral statistics for Beta=2 ensembles#^4cee7d|Theorem 15.15 (a)]] i.e. 
>$$\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=\int_{\Delta} \rho_{N}(x)dx=\frac{1}{N}\int_{\Delta}K_{N}(x,x)dx$$
>we can say 
>$$ \lim_{ N \to \infty }  \frac{1}{\sqrt{ 2 }}N^{\frac{1}{3}}\rho_{N}\left( \sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}} \right)  
 =\int _{s} ^{\infty} \text{Ai}^{2}(y)dy  
 = -s\text{Ai}^{2}(s)+(\text{Ai}'(s))^{2} $$
 where $\text{Ai}(x)$ is the standard **Airy function**
 $$\text{Ai}(x)=\frac{1}{\pi}\int_{0}^{\infty}\cos\left( \frac{1}{3}t^{3}+xt \right)dt$$
 >> [!tldr] Proof
 >> Take as a starting point the integral we had before in [[Bulk of the spectrum#^15ae9d|Proposition 16.3]] i.e.
 >> $$\rho_{N}(x)=\sqrt{ 2 }\int_{x}^{\infty}\psi_{N}^{(N)}(y)\psi_{N-1}^{(N)}(y)dy$$
 >> We have $x=\sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}}$, and we can write this by splitting the integral to some arbitrary point $A$.
 >> $$\rho_{N}(x)=\sqrt{ 2 }\int_{\sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{2/3}}}^{A}\psi_{N}^{(N)}(y)\psi_{N-1}^{(N)}(y)dy+\sqrt{ 2 }\int_{A}^{\infty}\psi_{N}^{(N)}(y)\psi_{N-1}^{(N)}(y)dy$$
 >> If we include the pre-factor in the final result $\frac{1}{\sqrt{ 2 }}N^{\frac{1}{3}}$, we get
 >> $$\rho_{N}(x)=N^{\frac{1}{3}}\int_{\sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{2/3}}}^{A}\psi_{N}^{(N)}(y)\psi_{N-1}^{(N)}(y)dy+N^{\frac{1}{3}}\int_{A}^{\infty}\psi_{N}^{(N)}(y)\psi_{N-1}^{(N)}(y)dy$$
 >> We can use [[Rescaling the GUE#^4722f5|Corollary 16.2 (c)]] to rewrite the $\psi$'s as
 >> $$\psi_{N}=2^{\frac{1}{4}}N^{\frac{1}{6}}(\text{Ai}(s)+o(1))$$
 >> and 
 >> $$\psi_{N-1}=2^{\frac{1}{4}}(N-1)^{\frac{1}{6}}(\text{Ai}(s)+o(1))$$
 >> where we can note that as $N\to \infty$, $(N-1)^{\frac{1}{6}}\to N^{\frac{1}{6}}$. Hence, the first integral becomes (as we go to large $N$)
>> $$\int_{s}^{A} \text{Ai}^{2}(s)ds+o(1)$$
>> For the second integral, we can write it as
>> $$\rho_{N}(A)=\sqrt{ 2 }\int_{A}^{\infty}\psi_{N}(y)\psi _{N-1}(y)dy$$
>> We can show that this vanishes for $A \to \infty$. Indeed, we can show the following bound, for any $\delta>0$ and $|x|>\sqrt{ 2 }(1+\delta)$:
>> $$\rho_{N}(x)\leq c_{1}e^{-c_{2}Nx^{2}}$$
>> where $c_{1},c_{1}>0$ are two constants that may depend on $\delta$. Therefore, if we take $A \to \infty$, the entire integral for $\rho_{N}(x)$ becomes:
>> $$\lim_{ N \to \infty }  \frac{1}{\sqrt{ 2 }}N^{\frac{1}{3}}\rho_{N}\left( \sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}} \right)  
 =\int _{s} ^{\infty} \text{Ai}^{2}(y)dy$$
 >> To obtain the second inequality, can use the fact that the Airy function satisfies the different equation $y''-xy=0$ for $y=\text{Ai}(x)$. From this, we can have the relation
>> $$\int_{0}^{\infty}\text{Ai}(x+u)\text{Ai}(u+x)du=(\text{Ai}'(x))^{2}-\text{Ai}''(x)\text{Ai}(x)=(\text{Ai}'(x))^{2}-x\text{Ai}^{2}(x)$$
>> which proves the second equality.

^742561

>[!info] Theorem 16.8 (b)
>If $P_{N,\ell}=P^{(2)}_{N,\ell}$ is the $\ell$th marginal (see [[Spectral statistics for Beta=2 ensembles#^193f65|Corollary 15.10]]) with $\beta=2$ and $V(x)=x^{2}$, then for any $\ell \in \mathbb{N}$ we have
>$$\lim_{ N \to \infty } \left( \frac{1}{\sqrt{ 2 }N^{\frac{1}{3}}} \right)^{\ell}P_{N,\ell}\left( \sqrt{ 2 }+\frac{x_{1}}{\sqrt{ 2 }N^{\frac{2}{3}}},\dots,\sqrt{ 2 }+\frac{x_{\ell}}{\sqrt{ 2 }N^{\frac{2}{3}}} \right)=\det(K_{\text{Ai}}(x_{j},x_{k}))^{\ell}_{j,k=1}$$
>where 
>$$K_{\text{Ai}}(x,y):= \int_{0}^{\infty}\text{Ai}(x+u)\text{Ai}(u+y)du=\frac{\text{Ai}(x)\text{Ai}'(y)-\text{Ai}(y)\text{Ai}'(x)}{x-y}$$
>is the **Airy kernel**.
>> [!tldr] Proof
>> To prove this, in view of the determinantal formula for the $\ell$th marginal (see [[Spectral statistics for Beta=2 ensembles#^6f152f|Example 15.14]]), the second proof above in [[Edges of the Spectrum#^742561|Theorem 16.8 (a)]] can be reduced to 
>> $$\lim_{ N \to \infty } \frac{1}{\sqrt{ 2 }N^{\frac{2}{3}}}K_{N}\left( \sqrt{ 2}+\frac{x_{j}}{\sqrt{ 2 }N^{\frac{2}{3}}} , \sqrt{ 2 }+\frac{x_{k}}{\sqrt{ 2 }N^{\frac{2}{3}}} \right) =K_{\text{Ai}}(x_{j},x_{k})$$
>> This is shown using the [[Spectral statistics for Beta=2 ensembles#^23a96c|Christoffel-Darboux identity]] and [[Rescaling the GUE#^b993f2|Plancherel-Rotach asymptotics]]. 

^802ec2


>[!info] Theorem 16.8 (c)
>For the *gap probability* $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta _{N})=0)$ corresponding to $\Delta_{N}=\sqrt{ 2 }+\frac{J}{\sqrt{ 2 }N^{\frac{2}{3}}}$ where $J \subset (a,b)$ with $-\infty<a<b<\infty$, we have
>$$\lim_{ N \to \infty } \mathcal{P}_{N}(\mathcal{N}_{N}(\Delta_{N})=0)=\det(I-K_{J})$$
>This is a [[Spectral statistics for Beta=2 ensembles#^a85492|Fredholm determinant]], with $K_{J}$ the integral operator defined by the Airy kernel $K_{\text{Ai}}$ acting on square integrable functions $f:J\to \mathbb{C}$. 
>>[!tldr] Proof
>>To see this, we first change variables to $y_{k}=\sqrt{ 2 }N^{\frac{2}{3}}(x_{k}-\sqrt{ 2 })$ in the $\ell$th term in the Fredholm determinant sum to obtain
>>$$\begin{align} & \mathcal{P}_{N}(\mathcal{N}_{N}(\Delta_{N})=0)\\ & =1+\sum_{\ell=1}^{N}\frac{(-1)^{\ell}}{\ell!}\int_{J^{\ell}}\det\left( \frac{1}{\sqrt{ 2 }N^{\frac{2}{3}}} K_{N}\left( \sqrt{ 2 }+\frac{y_{j}}{\sqrt{ 2 }N^{\frac{2}{3}}} , \sqrt{ 2 }+\frac{y_{k}}{\sqrt{ 2 }N^{\frac{2}{3}}}\right)\right)_{j,k=1}^{\ell} \prod_{m=1}^{\ell}dy_{m}\end{align} $$
>>Considering the equation in the proof in [[Edges of the Spectrum#^802ec2|Theorem 16.8 (b)]], we can see that the integrand will converge as $N\to \infty$, but we need to justify in this case that the infinite sum still converges so that the Fredholm determinant is well defined. It is indeed possible to prove that it does (*with help from lecture notes section A.2*).

^aa3f97

Let $\lambda_{N}^*$ be the *maximum* eigenvalue of a $N\times N$ GUE matrix $\mathcal{M}_{N}=\frac{1}{\sqrt{ N }}M_{N}$ (and so $\lambda_{N}^*$ is a random variable). Setting the rescaling 

$$
\lambda^{*}_{N} = \sqrt{ 2 }+\frac{\Lambda^{*}_{N}}{\sqrt{ 2 }N^{\frac{2}{3}}}
$$

we find from [[Edges of the Spectrum#^aa3f97|Theorem 16.8 (c)]] that the limiting cumulative distribution function for this rescaled maximum eigenvalue is 

$$
F(s):= \lim_{ N \to \infty } \mathcal{P}_{N}(\Lambda_{N}^{*}\leq s)=\lim_{ N \to \infty } \mathcal{P}_{N}\left( \mathcal{N}_{N}\left( \left( \sqrt{ 2 }+\frac{s}{\sqrt{ 2 }N^{\frac{2}{3}}} , \infty\right) \right) \right)=\det(I-K_{(s,\infty)})
$$

This distribution is known as the ($\beta=2$) **Tracy-Widom distribution**. Its analogues for the GOE and other ensembles occur in a number of interesting problems.

Let's again compare to i.i.d. random variables. Let $(\lambda_{j})_{j=1}^ N$ be a collection of i.i.d. real random variables where $\lambda_{j} \sim \mathcal{G}\left( 0, \frac{1}{2N} \right)$. Define the diagonal $N\times N$ random matrix $M_{N}=(\xi_{j,k})_{j,k=1}^N$ where $\xi_{j,j}=\lambda_{j}$ and $\xi_{j,k}=0$ (so diagonal values are RVs and off diagonals are zero). Therefore, $M_{N}$ is real and symmetric with diagonal distributed identically to the normalised GUE (but the off-diagonal entries have a different distribution). What is the distribution of the maximum eigenvalue $\lambda^{*}_{N}$? It transpires that, after rescaling, this will follow a **Gumbel distribution** with density function $\exp(-(x+\exp(-x)))$.![[Screenshot 2025-03-15 at 17.09.31.png]]