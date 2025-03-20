#Notes 

The theorem is restated here for convenience. 

>Let $\mathcal{M}_{N}$ be a real Wigner matrix of dimension $N$. Then, for any fixed $k \in \mathbb{N}$ and $\epsilon>0$ we have
>$$\lim_{ N \to \infty } \mathcal{P}\left( \Big| \frac{1}{N}\mathrm{Tr} (\mathcal{M}_{N}^{k})-\int_{\mathbb{R}}x^{k}\sigma_{t}(x)dx\Big| >\epsilon\right)=0$$
>We can see that the integral describes the $k$th moment of $\sigma_{t}(x)$.

To do this, we will follow this plan.

*Step 1*
Show that as $N\to \infty$,
$$
\frac{1}{N}\mathbb{E}_{N}[\mathrm{Tr}(\mathcal{M}_{N}^{\ell})] \to \begin{cases}
0 & \ell=2k-1 \\
t^{k}C_{k} & \ell=2k
\end{cases}
$$
for any $k \in \mathbb{N}$ with the $C_{k}$ being the [[Real Wigner matrices - traces, moments and combinatorics#^7ec087|Catalan numbers]].

*Step 2*
Show that as $N \to \infty$,
$$
\text{Var}\left( \frac{1}{N} \mathrm{Tr}(\mathcal{M}_{N}^{k}) \right) \to 0
$$
for all $k \in \mathbb{N}$. 

If we can show these two things, then [[Real Wigner matrices - traces, moments and combinatorics#^06ccc5|Theorem 17.3]] follows via [[Chebyshev's Inequality]] and [[Real Wigner matrices - traces, moments and combinatorics#^a90151|Lemma 17.4 (a)]]. To see how this would work, abbreviate 

$$
X_{N,k}:= \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k})
$$

with $N,k \in \mathbb{N}$. Then, we have
$$
\mathcal{P}_{N}\left(|X_{N,k}-t^{\frac{k}{2}}m_{k}|> \epsilon\right)\leq \mathcal{P}\left( |X_{N,k}-\mathbb{E}_{N}[X_{N,k}]|< \frac{\epsilon}{2} \right)+\mathcal{P}\left( |\mathbb{E}_{N}[X_{N,k}]-t^{\frac{k}{2}}m_{k}|> \frac{\epsilon}{2} \right)
$$
where we can note that the first probability is the same as the one in the theorem we are trying to prove.
By the equation in step 1, and [[Real Wigner matrices - traces, moments and combinatorics#^a90151|Lemma 17.4 (a)]], as $N\to \infty$, 
$$
\mathbb{E}_{N}[X_{N,k}] \to t^{\frac{k}{2}}m_{k}
$$
for $k\in \mathbb{N}$. Hence, the second summand $\mathcal{P}\left( |\mathbb{E}_{N}[X_{N,k}]-t^{\frac{k}{2}}m_{k}|> \frac{\epsilon}{2} \right)$ will be zero for sufficiently large $N$. 

To conclude we examine the first summand $\mathcal{P}\left( |X_{N,k}-\mathbb{E}_{N}[X_{N,k}]|< \frac{\epsilon}{2} \right)$. By [[Chebyshev's Inequality]], as $N \to \infty$,
$$
\mathcal{P}\left( |X_{N,k}-\mathbb{E}_{N}[X_{N,k}]|< \frac{\epsilon}{2} \right)\leq \frac{4}{\epsilon^{2}}\text{Var}(X_{N,k})
$$
for all $k\in \mathbb{N}$ - but step 2 would prove that this tends to zero. 

Thus, this is enough to find [[Real Wigner matrices - traces, moments and combinatorics#^06ccc5|Theorem 17.3]].

