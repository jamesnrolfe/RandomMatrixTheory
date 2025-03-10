---
dg-publish: true
---
#Notes 

We can now use [[Spectral statistics for Beta=2 ensembles#^4cee7d|Theorem 15.15 (a)]] i.e. 

$$\mathbb{E}_{N}[\mathcal{N}_{N}(\Delta)]=N \int_{\mathbb{R}} \varphi(x) \rho_{N}(x)dx$$

to compute the "limiting density of states". We will obtain **Wigner's semicircle law**, which states that as the system grows to infinite size, the density of eigenvalues converge to a semicircle. 
![[Screenshot 2025-03-07 at 13.00.35.png]]

This section will formalise the following idea.

For a *rescaled* matrix drawn from the GUE, consider $\bar{\mathcal{N}}_{N}(\Delta)$ the normalised count of its eigenvalues in $\Delta$. In the figures above, particularly (a), it is clear that it is *highly likely* that all eigenvalues fall between $-\sqrt{ 2 }$ and $\sqrt{ 2 }$, so formally $\bar{\mathcal{N}}_{N}([-\sqrt{ 2 },\sqrt{ 2 }])=1$. As well as this, if we looked at any range $[a,b]$ where both $a$ and $b$ fall within $[-\sqrt{ 2 },\sqrt{ 2 }]$, we would find that the proportion of eigenvalues in this range is roughly equal to the area under the curve. 

This curve is derived from the semi-circle of radius $\sqrt{ 2 }$ (but squashed to account for normalisation): $\sigma(x)=\frac{1}{\pi}\sqrt{ 2-x^{2}}$ for $-\sqrt{ 2 }\leq x\leq \sqrt{ 2 }$. 

Another thing to note is that this actually applies to a much wider range of matrix ensembles called Wigner matrices - of which the GUE is a specialisation! For this section and the next, we prove related results concerning the *mean* normalised counting measure $\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]$ which *is not a random quantity*. Consider figure (b) above - here we are drawing 100 GOE matrices (although still true for GUE) of size $100\times100$ and plotting the density of $10,000$ eigenvalues. This is capturing the idea of $\mathbb{E}_{N}[\bar{\mathcal{N}}_{100}(\Delta)]$ as we're getting the *average* picture over 100 experiments. This also looks close to the semi-circle plot (albeit with more "discrepancies" compared to figure (a)). We can remember that as we go to larger and larger systems, the actual value of $\bar{\mathcal{\mathcal{N}}}$ and $\mathbb{E}_{N}[\bar{\mathcal{N}}]$ get closer and closer to each other, which is kind of what we are seeing here (see [[Spectral statistics for Beta=2 ensembles#^eb204c|Chebyshev's inequality]], equally *lecture notes section A.4*).

Compare this to [[Spectral statistics#^e76b01|Example 15.6]], where we had a $N\times N$ matrix $M_{N}=(m_{j,k})$ with the only possible non-zero elements on the diagonal i.e. $m_{j,k}\propto \delta_{jk}$, and we took $\sqrt{ N }m_{j,k}=\mathcal{G}(0,1 / 2)$. Therefore, $M_{N}$ is real and symmetric, with a diagonal distributed exactly as a diagonal for the rescaled GUE. Then, the density plots for this are given below. 
![[Screenshot 2025-03-07 at 13.16.12.png]]

In this case

$$
\bar{\mathcal{N}}_{N}(\Delta)=\frac{1}{N}\sum_{j=1}^{N} \chi_{\Delta}(m_{j,j})
$$

and

$$
\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=\frac{1}{N}\sum_{j=1}^{N} \mathcal{P}(m_{j,j} \in \Delta)=\mathcal{P}\left( \mathcal{G} \left( 0, \frac{1}{2N} \right) \in \Delta\right)=\frac{1}{\sqrt{ 4\pi N }}\int_{\Delta}e^{\frac{-x^{2}}{4N}} dx
$$

so clearly, the expected value does not converge to the semi-circle seen in previous figures. Instead, since $\bar{\mathcal{N}}_{N}(\Delta)$ is the sum of *i.i.d.* random variables, it instead satisfies a central limit theorem (i.e. the blue curve in the above figures). Therefore, something *different* is happening in the case of the GUE due to these off diagonal entries - which if we remember, are not independent from each other!

Recall from [[Spectral statistics for Beta=2 ensembles#^4cee7d|Theorem 15.15 (a)]] that we can express the expected value of the normalised counting measure in terms of orthogonal polynomials.

$$
\mathbb{E}_{N}[\bar{\mathcal{N}}_{N}(\Delta)]=\int_{\Delta} \rho_{N}(x)dx=\frac{1}{N}\int_{\Delta}K_{N}(x,x)dx 
$$

We can therefore interpret $\rho_{N}(x)$ as a *density function* for the mean normalised counting measure, giving the appropriate weight for the expected proportion of GUE eigenvalues lying in an infinitesimally small interval around $x$. We would expect the, that this would converge to a semicircle. 

Before we state this formally, we prove two useful representations for $\rho_{N}$ using orthogonal polynomials. 

>[!info] Proposition 16.3
>Let $\rho_{N}$ be the density of the mean normalised counting measure for the GUE. Then, for any $x \in \mathbb{R}$, and any integer $N \geq 2$, we have 
>$$\rho_{N}(x)=(\psi_{N-1}^{(N)}(x))^{2}-\sqrt{ \frac{{N-1}}{N} }\psi_{N}^{(N)}(x)\psi_{N-2} ^{(N)}(x)$$
>and also
>$$\rho_{N}(x)=\sqrt{ 2 }\int_{x}^{\infty}\psi_{N}^{(N)}(y)\psi_{N-1}^{(N)}(y)dy$$
>where $\psi_{j}^{(N)}(x)=\exp\left(  \frac{N}{2} x^{2} \right)N^{\frac{1}{4}} \gamma_{j} H_{j}(\sqrt{ N }x)$ which we defined before in [[Spectral statistics for Beta=2 ensembles#^c20d5a|Hermite polynomials]].
>>[!tldr] Proof
>>To prove the first formula, we use the relation $\frac{d}{dx}H_{\ell}(x)=2\ell H_{\ell-1}(x)$, which presumably comes from a differing number of simple poles when differentiating and then using residue theorem. We then find that
>>$$\frac{d}{dx}\psi_{\ell}^{(N)}=N^{\frac{1}{4}}\gamma_{\ell} \frac{d}{dx} \left[ \exp\left( - \frac{N}{2} x^2 \right) H_{\ell}(\sqrt{ N }x)\right]$$
>>which after a few steps of differentiation (chain rule) and expanding out $\gamma_{\ell}$, arrives at 
>>$$\frac{d}{dx}\psi_{\ell}^{(N)}=-Nx\psi_{\ell}^{(N)}(x)+\sqrt{ 2N\ell }\psi_{\ell-1}^{(N)}(x)$$
>>Then, recalling from [[Spectral statistics for Beta=2 ensembles#^4cee7d|Theorem 15.15 (a)]] that 
>>$$\rho_{N}(x)=\frac{a_{N}}{N}\left( \psi_{N-1}(x) \frac{d}{dx}\psi_{N}(x)-\psi_{N}(x) \frac{d}{dx}\psi_{N-1}(x) \right)$$
>>we arrive at the first formula.
>>To obtain the second formula, we use the differential equation 
>>$$\frac{d^{2}}{dx^{2}}H_{\ell}(x)-2x \frac{d}{dx}H_{\ell}(x)+2\ell H_{\ell}(x)=0$$
>>for the Hermite polynomials, and hence 
>>$$\frac{d^{2}}{dx^{2}} \psi_{\ell}^{(N)}(x)=N(Nx^{2}-(2\ell+1))\psi_{\ell}^{(N)}(x)$$
>>Then, from the above equation from [[Spectral statistics for Beta=2 ensembles#^4cee7d|Theorem 15.15 (a)]] again, we find 
>>$$\frac{d}{dx}\rho_{N}(x)=-\sqrt{ 2 }\psi_{N}^{(N)}(x)\psi_{N-1}^{(N)}(x)$$
>>which can simply be integrated to find the second formula. The limits are found from [[Rescaling the GUE#^cb9f94|Corollary 16.2(b)]] and the [[Rescaling the GUE#^ab2ee8|comment after]], suggesting that $\lim_{ x \to \infty }\psi_{\ell}^{(N)}(x)=0$, and hence integrating the equation from $\infty$ to $x$ finds the correct identity.

^15ae9d

We can then state **Wigner's semicircle law for the GUE**.

>[!info] Theorem 16.4
>Let $\rho_{N}$ be the density of the mean normalised counting measure for the GUE. Then, its point-wise limit indeed converges to the semi-circle:
>$$\lim_{ N \to \infty } \rho_{N}(x)=\frac{1}{\pi}\sqrt{ (2-x^{2})_{+} }$$
>where we define $y_{+}:= \text{max}\{ y,0 \}$ such that the semicircle is zero outside its radius, and real.
>(*proof non-examinable, see lecture notes page 33*)

^b35f3e

The next result describes the *bulk* case of the local regime for the GUE. This scenario concerns the statistical properties of its eigenvalues in an $\mathcal{O}(N^{-1})$-neighbourhood of $x_{0}\in(-\sqrt{ 2 },\sqrt{ 2 })$: a point of the support of the limiting normalised counting measure of eigenvalues where its density does not vanish. Generally, we have the following definition. 

>[!info] Definition 16.5
>Suppose the normalised counting measure $\bar{\mathcal{N}}_{N}$ of eigenvalues of a given random matrix $M_{N}$ converges (in probability) to some limit law $N$ that has density $\rho$. Then, the **bulk of the spectrum** of $N$ is defined as 
>$$\text{bulk}(N) := \{ x \in \text{supp}(N): \text{there exists some }\delta>0 \text{ such that } \text{ inf }_{y \in [x-\delta,x+\delta]} \rho(y)>0\}$$
>This is a lot of jargon. Essentially what this is saying that for the non-zero values of $N$ there exists many points where there is "mass" (i.e. a presence of eigenvalues) on both sides. However, for two particular points $-\sqrt{ 2 }$ and $\sqrt{ 2 }$ in this case, there will only be mass on one side (right and left resp.), and hence these define the edge of the bulk. So in our case, the bulk is defined by the range $(-\sqrt{ 2 },\sqrt{ 2 })$.
>Points of the spectrum that do not belong to its bulk (so here $-\sqrt{ 2 }$ and $\sqrt{ 2 }$) are called **special points**.

For the next theorem, consider the GUE whose joint eigenvalue density is given in [[Spectral statistics for Beta=2 ensembles#^193f65|Corollary 15.10]] i.e. 

$$P_{N} ^{(\beta)}(\lambda_{1},\dots,\lambda_{N})=Z_{N}^{(\beta)} \exp \left( -\frac{\beta}{2} \sum_{j=1}^{N} V(\lambda_{j}) \right)|\Delta (\lambda_{1},\dots,\lambda_{N})|^{\beta},\quad\beta=1,2$$

with $\beta=2$ and $V(x)=x^2$. Assume that there is some point $x_{0}$ that belongs to the bulk of the spectrum (i.e. $(-\sqrt{ 2 }, \sqrt{ 2 })$) of the semicircle law with density given as 

$$
\lim_{ N \to \infty } \rho_{N}(x)=\frac{1}{\pi}\sqrt{ (2-x^{2})_{+} }$$

from [[Bulk of the spectrum#^b35f3e|Theorem 16.4]]. We then have the following three theorems.

>[!info] Theorem 16.6 (a)
>If $P_{N,\ell}=P^{(2)}_{N,\ell}$ is the $\ell$th marginal of the joint eigenvalue density and $\rho_{N}(x)$ remains the density of the mean normalised counting measure, then for any $\ell \in \mathbb{N}$ we hav
>$$\lim_{ N \to \infty } \frac{1}{(\rho_{N}(x_{0}))^{\ell}}P_{N,\ell}\left( x_{0}+ \frac{x_{1}}{N\rho_{N}(x_{0})},\dots,x_{0}+ \frac{x_{\ell}}{N\rho_{N}(x_{0})} \right)=\det\left( \frac{\sin [\pi(x_{j}-x_{k})]}{\pi(x_{j}-x_{k})} \right)^{\ell}_{j,k=1}$$
>The kernel here
>$$K_{N}(x,y)=\frac{\sin[\pi(x-y)]}{\pi(x-y)}$$
>is known as the **Sine kernel**.

^0e8e95

>[!info] Theorem 16.6 (b)
>If we consider $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta_{N})=0)$ the probability that a matrix from the GUE has no eigenvalues in 
>$$\Delta_{N}:= \left( x_{0},x_{0}+\frac{s}{N\rho_{N}(x_{0})} \right) \subset \mathbb{R}$$
>then in the large matrix limit, this has determinantal form 
>$$\mathcal{E}_{0}(s):= \lim_{ N \to \infty } \mathcal{P}_{N}(\mathcal{N}_{N}(\Delta_{N})=0)=\det(I-Q_{s})$$
>where $Q_{s}$ is the integral operator 
>$$(Q_{s}f)(x):= \int_{0}^{s} K_{N}(x,y)f(y)dy$$
>where $K_{N}(x,y)$ is the sine kernel in [[Bulk of the spectrum#^0e8e95|Theorem 16.6 (a)]].

>[!info] Theorem 16.6 (c)
>If we consider $\mathcal{P}_{N}(\mathcal{N}_{N}(\Delta_{N})=\ell)$ to be the probability that a GUE matrix has $\ell \in \mathbb{Z}_{\geq 0}$ eigenvalues in $\Delta_{N}$, then as $s \to 0$ from the right
>$$\mathcal{E}_{\ell}(s):= \lim_{ N \to \infty } \mathcal{P}_{N}(\mathcal{N}_{N}(\Delta_{N})=\ell)=C_{\ell}s^{\ell^{2}} (1+o(1))$$
>where $C_{0}=1$ and
>$$C_{\ell}=\frac{1}{(2\pi)^{\ell}\ell!} \frac{1}{\left( \prod_{j=1}^{\ell-1} j! \right)^{2}}\int_{[-\pi,\pi]^{\ell}}\Delta^{2}(x_{1},\dots,x_{\ell})\prod_{j=1}^{\ell} dx_{j}$$

^f26b66

(*proofs in lecture notes for now, writeup coming...*)

The value $s$ can be thought of as eigenvalue spacing, with a normalisation factor written in to ensure it becomes 1. If we did the above in [[Bulk of the spectrum#^f26b66|Theorem 16.6 (c)]], but with i.i.d. random variables, we would find that the probability is related to $s^{\ell}$, and so since $s$ is very small, this is much larger than $s^{\ell^2}$ as we saw in the above. Hence, we have shown for the GUE that there is some eigenvalues spacing (which is what we expected). 

Throughout the theorem, we are concerned with spacings normalised by $N\rho_{N}(x)$. Recall that

$$
\frac{1}{N}\mathbb{E}_{N}[\mathcal{N}_{N}([-\sqrt{ 2 },\lambda])]=\int_{-\sqrt{ 2 }}^{\lambda}\rho_{N}(x)
$$

which, in the large $N$ limit according to [[Bulk of the spectrum#^b35f3e|Theorem 16.4]] tends to

$$
{N \to \infty} \; :\;\to \int_{-\sqrt{ 2 }}^{\lambda} \frac{1}{\pi}\sqrt{ (2-x^{2})_{+} }dx=\frac{\lambda}{2\pi} \sqrt{ 2-\lambda^2 }+\frac{1}{\pi}\arcsin\left( \frac{\lambda}{\sqrt{ 2 }} \right)+\frac{1}{2}
$$

We can check that is works with out theory. If $\lambda=-\sqrt{ 2 }$ i.e. the first eigenvalue, then the expected value becomes 0 - this makes sense because there are no eigenvalues before this. If it is $\sqrt{ 2 }$ i.e. the last eigenvalue, then the expected value is just $1$ which also makes sense, because all of the eigenvalues are before this one.

We can then write the expected number of eigenvalues between $-\sqrt{ 2 }$ and $\lambda$ as 

$$
\mathbb{E}_{N}[\mathcal{N}_{N}([-\sqrt{ 2 },\lambda])]=\begin{cases}
0 & \lambda\leq-\sqrt{ 2 } \\
\frac{N\lambda}{2\pi}\sqrt{ 2-\lambda^2 }-\frac{N}{\pi}\arcsin\left( \frac{\lambda}{\sqrt{ 2 } } \right)+\frac{N}{2} & \lambda \in (-\sqrt{ 2 },\sqrt{ 2 }) \\
N & \lambda\geq \sqrt{ 2 }
\end{cases}
$$

Therefore, the expected position of the $j$th eigenvalue $\lambda_{j}$ (ordered) is the right and side of the above at $\lambda=\lambda_{j}$. If we rescale, and call $\bar{\lambda}_{j}=\mathbb{E}_{N}[\mathcal{N}_{N}([-\sqrt{ 2 },\lambda_{j}])]$ then the expected spacing between $\bar{\lambda}_{j}$ abd $\bar{\lambda}_{j+1}$ is just 1. 