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

>[!info] Theorem 16.8 (b)
>If $P_{N,\ell}=P^{(2)}_{N,\ell}$ is the $\ell$th marginal (see [[Spectral statistics for Beta=2 ensembles#^193f65|Corollary 15.10]]) with $\beta=2$ and $V(x)=x^{2}$, then for any $\ell \in \mathbb{N}$ we have
>$$\lim_{ N \to \infty } \left( \frac{1}{\sqrt{ 2 }N^{\frac{1}{3}}} \right)^{\ell}P_{N,\ell}\left( \sqrt{ 2 }+\frac{x_{1}}{\sqrt{ 2 }N^{\frac{2}{3}}},\dots,\sqrt{ 2 }+\frac{x_{\ell}}{\sqrt{ 2 }N^{\frac{2}{3}}} \right)=\det(K_{\text{Ai}}(x_{j},x_{k}))^{\ell}_{j,k=1}$$
>where 
>$$K_{\text{Ai}}(x,y):= \int_{0}^{\infty}\text{Ai}(x+u)\text{Ai}(u+y)du=\frac{\text{Ai}(x)\text{Ai}'(y)-\text{Ai}(y)\text{Ai}'(x)}{x-y}$$
>is the **Airy kernel**.

