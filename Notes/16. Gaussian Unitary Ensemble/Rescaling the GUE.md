---
dg-publish: true
---
#Notes 

As we are interested in taking the matrix size $N\to \infty$, we should rescale our matrix from the GUE such that it is bounded. Recall from [[Spectral statistics for Beta=2 ensembles#^5eb37b|Theorem 15.8]] that

$$
a_{j}=\sqrt{ \frac{j}{2} }
$$

As $j\to \infty$, $a_{j}\to \infty$. This is not good - we want to scale this such that we don't go to infinity.

Take an $N\times N$ matrix $A=(a_{j,k})$ and assume that it has eigenvalues $\alpha_{1}<\dots<\alpha_{N}$. Then, for example

$$
\sum_{j=1}^{N}\alpha_{j}^{2} \leq N \text{max}_{j=1,\dots,N} (\alpha_{j}^{2})=N\text{max}\{a_{1}^2,a_{N}^2\}
$$

The left hand side, after dividing by $N$, *is the linear statistic* $\frac{1}{N}\sum_{j=1}^{N}\alpha_{j}^{2}$. By the **spectral mapping theory**

$$
\frac{1}{N}\sum_{j=1}^{N} \alpha_{j}^{2}=\frac{1}{N}\mathrm{Tr}(A^2)=\frac{1}{N}\sum_{j,k}^{N}a_{j,k}a_{k,j}=\frac{1}{N}\sum_{j,k=1}^{N}|a_{j,k}|^2 
$$

Since $A$ is hermitian, using [[Spectral statistics for Beta=2 ensembles#^9857c9|the jpdf for the matrix elements]],

$$
\mathbb{E}_{N}\left[ \frac{1}{N}\sum_{j,k=1}^{N}  |a_{j,k}|^{2}\right] =\frac{1}{N}\left( \sum_{j=1}^{N} \mathbb{E}[a_{11}^2]+2\sum_{j,k=1; j<k} \mathbb{E}[|a_{12}|^{2}]\right)=\mathbb{E}[a_{11}^2]+(N-1)E[|a_{12}|^{2}]
$$


and thus 

$$\mathbb{E}[a_{11}^{2}]+(N-1)\mathbb{E}[|a_{12}|^{2}]\leq \mathbb{E}[\text{max}\{ \alpha_{1}^{2},\alpha_{N}^2 \}]$$

Consequently, if we take $N\to \infty$, then the left hand side diverges - forcing the right hand side to diverge (since is it always equal or *bigger*). So, in order to get a non-trivial scaling limit in some sense, we should scale the entries $a_{j,k}$ by $\frac{1}{\sqrt{ N }}$, compensating for the linear growth of $N$. 

To this end, we will henceforth consider *rescaled* matrices $\mathcal{M}_{N} \to \frac{1}{\sqrt{ N }}M_{N}$. Some previous results are affected, the most important of which are collected below. 

The jpdf of the rescaled matrix entries $\mathcal{M}_{N}=(m_{j,k})$ is

$$
P_{N}(\mathcal{M}_{N}) \propto \exp(-N \mathrm{Tr}(\mathcal{M}_{N}^2))
$$

and the jpdf for the eigenvalues is 

$$
P_{N}(\lambda_{1},\dots,\lambda_{N})\propto \exp\left( -N\sum^{N}_{j=1}\lambda_{j}^2 \right)|\Delta(\lambda_{1},\dots,\lambda_{N})|^2
$$

where we notice the new factors of $N$ in both.

The associated weight $w_{N}(x)=\exp(-Nx^{2})$ is now known as the **varying weight** (since it depends on $N$), and consequently the $j$th orthonormal polynomial for the rescaled GUE also depends on $N$, and is 

$$
p_{j}^{(N)} (x) = N^{\frac{1}{4}} \gamma_{j}H_{j}(\sqrt{ N }x)
$$

where $H_{j}(x)$ is the $j$th [[Spectral statistics for Beta=2 ensembles#^c20d5a|Hermite polynomial]], with $\gamma_{j}$ the same as before. When we [[Spectral statistics for Beta=2 ensembles#^bd5d40|changed notation]] before, the equivalent change here is

$$
\psi_{j}^{(N)} (x)=\sqrt{ w_{N}(x) }p_{j}^{(N)}(x)
$$

The coefficient $a_{j}^{(N)}$ in the [[Spectral statistics for Beta=2 ensembles#^23a96c|three term recurrence relation]] (see [[Spectral statistics for Beta=2 ensembles#^5eb37b|Theorem 15.18]]) also changes to

$$
a_{j}^{(N)} = \sqrt{ \frac{j}{2N} }
$$

Hence, for example, $p_{0}^{(N)}(x)=\left( \frac{N}{\pi} \right)^{\frac{1}{4}}$ (verify remembering that $H_{0}(x)=1$).

In the forthcoming, there are a few mathematical tools we need to solve problems, outlined in the propositions below. For all, we denote by $H_{\ell}(x)$ the classical [[Spectral statistics for Beta=2 ensembles#^c20d5a|Hermite polynomial]] and let $\epsilon$ and $\omega$ be fixed positive numbers. The following holds true for $\ell\to \infty$.

>[!info] Proposition 16.1 (a)
>For $x=\sqrt{ 2\ell+1 }\cos \phi$ with $\epsilon\leq \phi \leq \pi-\epsilon$ we have
>$$e^{-\frac{1}{2}x^{2}}H_{\ell}(x)=2^{\frac{\ell}{2}+\frac{1}{4}} \sqrt{ \ell! }(\pi \ell)^{-\frac{1}{4}} \frac{1}{\sqrt{ \sin \phi }}\left( \sin\left[ \left( \frac{\ell}{2} +\frac{1}{4} \right) (\sin{2}\phi-2\phi)+\frac{3\pi}{4}\right] + \mathcal{O}(\ell^{-1})\right)$$

>[!info] Proposition 16.1 (b)
>For $x=\sqrt{ 2\ell+1 }\cosh \phi$ with $\epsilon \leq \phi \leq \omega$ we have
>$$e^{-\frac{1}{2}x^{2}}H_{\ell}(x)=2^{\frac{\frac{\ell}{2}-3}{4}}\sqrt{ \ell! }(\pi \ell)^{-\frac{1}{4}} \frac{1}{\sqrt{ \sinh \phi }}\exp\left( \left[ \frac{\ell}{2}+\frac{1}{4} \right](2\phi-\sinh{2}\pi) \right)(1+\mathcal{O}(\ell^{-1}))$$

>[!info] Proposition 16.1 (c)
>For $x=\sqrt{ 2\ell+1 } -2^{- \frac{1}{2}}3^{- \frac{1}{3}} \ell^{- \frac{1}{6}}t$ with $t \in \mathbb{C}$ bounded we have
>$$e^{- \frac{1}{2}x^{2}}H_{\ell}(x)=\pi^{\frac{1}{4}}2^{\frac{\frac{\ell}{2}+1}{4}}\sqrt{ \ell! }\ell^{- \frac{1}{12}}(A(t)+\mathcal{O}(\ell^{\frac{-7}{3}}))$$
>with $A(t)=\text{Ai}(-3^{- \frac{1}{3}}t)$ in terms of the standard Airy function 
>$$\text{Ai}(x):= \frac{1}{\pi}\int^{\infty}_{0} \cos\left( \frac{1}{3}t^{3}+xt \right)dt$$

One can use (a) and (b) to derive the leading terms of the large $N$-asymptotics of the functions 

$$
\psi_{N-k}^{(N)} (x)=\sqrt{ w_{N}(x) }p_{N-k}^{(N)}(x)=e^{- \frac{N}{2}x^2}N^{\frac{1}{4}}\gamma_{N-k}H_{N-k}(\sqrt{ N }x)
$$

for integer $k \geq 0$.

This can be seen in the following corollaries. For them, consider $\psi_{N-k}^{(N)}$ as in the above, for fixed $k \in \mathbb{Z}_{\geq{0}}$. We then have, as $N \to \infty$, the following.

>[!info] Corollary 16.2 (a)
>For any $x \in(-\sqrt{ 2 },\sqrt{ 2 })$, parametrised as $x=\sqrt{ 2 }\cos \theta$ with $\theta \in (0,\pi)$, we have
>$$\psi_{N-k}^{(N)}(x)= \sqrt{ \frac{2}{\pi\sqrt{ 2-x^{2} } }}\cos\left( N \beta(\theta)-\left[ k-\frac{1}{2}\right]\theta-\frac{\pi}{4} \right)+\mathcal{O}(N^{-1})$$
>with $\beta(\theta):= \theta-\frac{1}{2}\sin 2\theta$.

>[!info] Corollary 16.2 (b)
>For $|x| > \sqrt{ 2 }$ parametrised as $x=\sqrt{ 2 }\cosh \theta$ with $\theta>0$, we have
>$$\psi_{N-k}^{(N)}(x)=\sqrt{ \frac{1}{2\pi\sqrt{ x^{2}-2 } }} \exp\left( -N\alpha(\theta)-\left[ k-\frac{1}{2} \right]\theta \right)(1+\mathcal{O}(N^{-1}))$$
>where $\alpha(\theta):=\frac{1}{2}\sinh{2}\theta-\theta$.

>[!info] Corollary 16.2 (c)
>For $t \in \mathbb{C}$ fixed and setting $x=\sqrt{ 2 }+\frac{t}{\sqrt{ 2 }N^{2/3}}$ we have
>$$\psi_{N-k}^{(N)}(x)=2^{\frac{1}{4}}N^{\frac{1}{6}}(\text{Ai}(t)+\mathcal{O}(N^{\frac{-3}{4}}))$$

We can use (b) to see what happens as $x\to \infty$. Since $\theta=\cosh^{-1}\left( \frac{x}{\sqrt{ 2 }} \right)$ goes to infinity in this limit, we find from (b) that

$$
\lim_{ x \to \infty } \psi_{N-k}^{(N)}(x)=0
$$

