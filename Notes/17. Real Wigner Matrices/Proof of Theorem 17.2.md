#Notes 

>[!summary]

In [[Proof of Theorem 17.3|the last section]] we proved [[Real Wigner matrices - traces, moments and combinatorics#^06ccc5|Theorem 17.3]], and now we wish to prove the stronger case - [[Real Wigner matrices - traces, moments and combinatorics#^8bba3c|Theorem 17.2]], written here for convenience.

>[!info] Theorem 17.2
>Let $\Delta \subset \mathbb{R}$ be an interval and $\mathcal{M}_{N}$ a real Wigner matrix of size $N\times N$, with eigenvalues $-\infty<\lambda_{1}\leq\dots\leq \lambda_{N}<\infty$. Then, the normalised counting measure satisfies for all $\epsilon>0$:
>$$\lim_{ N \to \infty } \mathcal{P}\left( \Big| \bar{\mathcal{N}}_{N}(\Delta)-\int_{\Delta}\sigma_{t}(x)dx \Big| > \epsilon\right)=0$$
>or if instead we used any continuous bounded function $\varphi:\mathbb{R}\to \mathbb{C}$, then the linear statistic obeys
>$$\lim_{ N \to \infty } \left( \Big| \frac{1}{N}\mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{t}(x)dx \Big|>\epsilon \right)=0$$

Let first attempt to prove the second result, and then move on to the first.

We will again use the setup from [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]] to define our Wigner matrix. Then, we may easily fix the variance of $Z_{1,2}$ to be $t=1$. With this convention in hand, we can begin with the following lemma. 

>[!info] Lemma 17.17
>Let $k \in \mathbb{N}$, $\varepsilon >0$ and $b \geq 0$ be fixed. Take $\Delta=\Delta_{b}\subset \mathbb{R}$ be defined as
>$$\Delta := (-\infty, -b) \cup (b,\infty)$$
>>[!help] Note
>>This essentially means that $\Delta$ is everywhere except the region $[-b,b ]$.
> 
> Then we define a function (dependent on $\Delta$) $\varphi:\mathbb{R}\to \mathbb{R}_{\geq 0}$ by
> $$\varphi(x):= |x|^{k} \chi_{\Delta}(x)= \begin{cases} |x|^{k} & x \in \Delta \\ 0 & x \not\in \Delta\end{cases}$$
> such that $\chi_{\Delta}$ acts as an indicator function of being in $\Delta$.
> Then, for any $b > 4$,
> $$\limsup_{ N \to \infty } \mathcal{P}\left( \frac{1}{N}\mathcal{N}_{N}[\varphi]>\varepsilon \right) =0$$
> i.e. the probability that there are any eigenvalues outside the region $[-b,b]$ goes to zero with large $N$.
> >[!tldr]- Proof
> >First, by [[Markov's inequality]], noting that $\mathcal{N}_{N}[\varphi]=\sum_{j=1}^{N}\varphi(\lambda_{j})\geq 0$, we have
> >$$\mathcal{P}\left( \frac{1}{N}\mathcal{N}_{N}[\varphi]>\varepsilon \right)\leq \frac{1}{\varepsilon N}\mathbb{E}[\mathcal{N}_{N}[\varphi]]$$
> >where 
> >$$\begin{align} \mathcal{N}_{N}[\varphi] & = \sum_{j=1}^{N}|\lambda_{j}(\mathcal{M}_{N})|^{k} \chi_{\Delta}(\lambda_{j}(\mathcal{M}_{N})) \\
  \\
> >  & \leq \frac{1}{b^{k}}\sum_{j=1}^{N} |\lambda_{j}(\mathcal{M}_{N})|^{2k}\chi_{\Delta}(\lambda_{j}(\mathcal{M}_{N})) \\
 \\
> >  & \leq \frac{1}{b^{k}} \mathrm{Tr}(\mathcal{M}_{N}^{2k})\end{align} $$
> >  Hence
> >  $$\mathcal{P}\left( \frac{1}{N}\mathcal{N}_{N}[\varphi]>\varepsilon \right)\leq \frac{1}{\varepsilon N b^{k}}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{2k})]$$
> >  where the right hand side converges to $\frac{C_{k}}{\varepsilon b^{k}}$ under large $N$. Hence, by [[Real Wigner matrices - traces, moments and combinatorics#^1360ca|Lemma 17.6]] it follows that 
> >  $$\limsup_{ N \to \infty }\mathcal{P}\left( \frac{1}{N}\mathcal{N}_{N}[\varphi]>\varepsilon \right) \leq \frac{C_{k}}{\varepsilon b^{k}}\leq \frac{1}{\varepsilon}\left( \frac{4}{b} \right)^{k}$$
> >  On the other hand, when $|x|>b>4>1$, the function $k \mapsto |x|^{k}$ is strictly increasing, which means the sequence of limsups in the left-hand side of the above is increasing in $k$. But the sequence decays exponentially as $\frac{4}{b}<1$ in $\Delta$. The only way that these conditions can be met is if the sequence of limsups is $0$ i.e. 
> >  $$\limsup_{ N \to \infty } \mathcal{P}\left( \frac{1}{N}\mathcal{N}_{N}[\varphi]>\varepsilon \right) =0$$
> >  as claimed.

^843bba

Now we can prove [[Real Wigner matrices - traces, moments and combinatorics#^8bba3c|Theorem 17.2]]. 

Let's fix a continuous bounded function $\varphi:\mathbb{R} \to \mathbb{C}$, and fix $\varepsilon>0$ and $b>4$. By the **[[Weierstrass approximation]]** there exists a polynomial $P_{\varepsilon}\in \mathbb{C}[x]$ such that 
$$
\sup_{|x|\leq b} |\varphi(x)-P_{\varepsilon}(x)|< \frac{\varepsilon}{6}
$$
>[!help] Note
>The $6$ is just there to make the next bit of the derivation cleaner - it is just part of the constant.

Then by triangle inequality estimates

$$
\begin{align}
\bigg | \frac{1}{N}\mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx \bigg|  & \leq \bigg | \frac{1}{N}\mathcal{N}_{N}[\varphi]-\frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}]\bigg | + \bigg | \frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}]-\int_{\mathbb{R}}P_{\varepsilon}(x)\sigma_{1}(x)dx\bigg| \\
 \\
&\quad+ \bigg | \int_{\mathbb{R}}P_{\varepsilon}(x)\sigma_{1}(x)dx - \int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx \bigg| \\
 \\
 & =: A_{1}+A_{2} +A_{3}
\end{align}
$$
>[!help] Note
>Here we have added and subtracted two things, which we are allowed to do.

Hence, the event $\left\{  | \frac{1}{N} \mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx|  > \varepsilon\right\}$ is contained in the union of three events (the three terms $A_{1},A_{2},A_{3}$). This means that each of the terms is bigger than $\frac{\varepsilon}{3}$ by the triangle inequality. This means that
$$
\mathcal{P}\left(\bigg| \frac{1}{N}\mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx \bigg| > \varepsilon\right) \leq \mathcal{P}\left( A_{1}> \frac{\varepsilon}{3} \right)+\mathcal{P}\left( A_{2}> \frac{\varepsilon}{3} \right)+\mathcal{P}\left( A_{3}> \frac{\varepsilon}{3} \right)
$$

^65b468

Using our [[Weierstrass approximation]] we can say that $|f(x)-P_{\varepsilon}(x)|< \frac{\varepsilon}{6}$ on $[-b,b]$, which includes the support $[-2,2]$ of $x\mapsto \sigma_{1}(x)$. 
>[!help] Note
>It is important to mention the support here, since we are saying that the interval we care about overlaps with the support of our function, so we can use the Weierstrass approximation just fine. 

With this knowledge, consider $A_{3}$:
$$
A_{3}=\bigg | \int_{\mathbb{R}}P_{\varepsilon}(x)\sigma_{1}(x)dx-\int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx \bigg | = \int_{\mathbb{R}}|P_{\varepsilon}(x)-\varphi(x)|\sigma_{1}(x)dx  \leq \frac{\varepsilon}{6} \int_{\mathbb{R}}\sigma_{1}(x)dx 
$$
The integral in the last term is just the integral of a probability density function, which should be equal to $1$. Hence, we can say $A_{3}\leq \frac{\varepsilon}{6}$. Then, it is clear that
$$
\mathcal{P}\left( A_{3}> \frac{\varepsilon}{3} \right)=0
$$
since $A_{3}$ can never reach $\frac{\varepsilon}{3}$, as it has maximum $\frac{\varepsilon}{6}$. So, we have removed a term from the [[Proof of Theorem 17.2#^65b468|above inequality]], it becomes
$$
\mathcal{P}\left(\bigg| \frac{1}{N}\mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx \bigg| > \varepsilon\right) \leq \mathcal{P}\left( A_{1}> \frac{\varepsilon}{3} \right)+\mathcal{P}\left( A_{2}> \frac{\varepsilon}{3} \right)
$$
Then, for the term $\mathcal{P}\left( A_{1}> \frac{\varepsilon}{3} \right)$, we can write
$$
\begin{align}
\bigg| \frac{1}{N} \mathcal{N}_{N}[\varphi]- \frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}] \bigg|  & = \bigg | \frac{1}{N}\sum^{N}_{j=1}\varphi(\lambda_{j}) - \frac{1}{N}\sum_{j=1}^{N}P_{\varepsilon}(\lambda_{j}) \bigg| \\
 \\
 &= \frac{1}{N}\sum_{j=1}^{N}\bigg | \varphi(\lambda_{j})- P_{\varepsilon}(\lambda_{j}) \bigg| 
\end{align}
$$
Then, we can multiply the left hand side by our indicator function, representing being in our interval $\Delta=\Delta_{b}=[-b,b]$. More specifically we will multiply the LHS by
$$
\chi_{\Delta}(\lambda_{j}) +1 - \chi_{\Delta}(\lambda_{j})=1
$$
which is clearly equal to one, and so doesn't change the LHS. Notice as well that the term $1-\chi_{\Delta}(\lambda_{j})$ is the probability of *not* being in $\Delta$, and so we could easily rewrite the above as
$$
\chi_{\Delta}(\lambda_{j})+\chi_{\mathbb{R} \setminus \Delta}(\lambda_{j})
$$
We would then find
$$
\bigg| \frac{1}{N} \mathcal{N}_{N}[\varphi]- \frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}] \bigg|  = \frac{1}{N}\sum_{j=1}^{N}\bigg | \varphi(\lambda_{j})- P_{\varepsilon}(\lambda_{j}) \bigg| (\chi_{\Delta}(\lambda_{j})-\chi_{R \setminus \Delta}(\lambda_{j}))
$$
We will do the triangle inequality again, and the RHS becomes
$$
\bigg| \frac{1}{N} \mathcal{N}_{N}[\varphi]- \frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}] \bigg|  \leq \frac{1}{N}\sum_{j=1}^{N}|\varphi(\lambda_{j})-P_{\varepsilon}(\lambda_{j})|\chi_{\Delta}(\lambda_{j})+\frac{1}{N}\sum_{j=1}^{N}|\varphi(\lambda_{j})-P_{\varepsilon}(\lambda_{j})|\chi_{\mathbb{R}\setminus\Delta}(\lambda_{j}) =: B_{1}+B_{2}
$$
By the same reasoning as above, we then estimate
$$
\mathcal{P}\left( A_{1}> \frac{\varepsilon}{3} \right) = \mathcal{P}\left( \bigg| \frac{1}{N}\mathcal{N}_{N}[\varphi]- \frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}] \bigg| > \frac{\varepsilon}{3} \right) \leq \mathcal{P}\left( B_{1}> \frac{\varepsilon}{6} \right)+\mathcal{P}\left( B_{2} > \frac{\varepsilon}{6} \right)
$$
Recall that we said $|f(x)-P_{\varepsilon}(x)|< \frac{\varepsilon}{6}$ on $\Delta=[-b,b]$, and so the first term involving $B_{1}$ is zero.
>[!help] Note
>Why is this? The indicator function in the first term essentially means we only count values in the range $[-b,b]$, so we can think of it as the sum of functions $|\varphi-P_{\varepsilon}|$ in this range, which above we said was less than $\frac{\varepsilon}{6}$. Hence, this probability that this is larger than $\frac{\varepsilon}{6}$ is zero.
>Note as well that the support $[-2,2]$ is only included in the second term (i.e. the region $\mathbb{R} \setminus \Delta$), and so we can only use a Weierstrass approximation there. 

Then, we can rewrite [[Proof of Theorem 17.2#^65b468|above inequality]] again as 
$$
\mathcal{P}\left(\bigg| \frac{1}{N}\mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{1}(x)dx \bigg| > \varepsilon\right) \leq \mathcal{P}\left( B_{2}> \frac{\varepsilon}{6} \right)+\mathcal{P}\left( A_{2}> \frac{\varepsilon}{3} \right)
$$
Now consider briefly the $A_{2}$ term above. Remember that 
$$
A_{2}=\bigg | \frac{1}{N}\mathcal{N}_{N}[P_{\varepsilon}]-\int_{\mathbb{R}}P_{\varepsilon}(x)\sigma_{1}(x)dx\bigg| 
$$
Consider [[Real Wigner matrices - traces, moments and combinatorics#^06ccc5|Theorem 17.3]]. If $P_{\varepsilon}(x)=\sum_{k=0}^{d} f_{k}x^{k}$ is a polynomial, then with some $c_{k}>0$ as $N \to \infty$
$$
\mathcal{P}\left( A_{2}> \frac{\varepsilon}{3} \right)\leq \sum_{k=0}^{d}|f_{k}| \mathcal{P}\left( \bigg| \frac{1}{N} \mathrm{Tr}(\mathcal{M}_{N}^{k})-\int_{\mathbb{R}}x^{k}\sigma_{1}(x)dx \bigg| > \varepsilon c_{k} \right) \to 0
$$
So we are left only to estimate the first term in the right hand side: $\mathcal{P}\left( B_{2}> \frac{\varepsilon}{6} \right)$. First, denote $d= \deg(P_{\varepsilon})$. Since $\varphi$ is globally bounded, we have $|\varphi(x)-P_{\varepsilon}(x)|\leq || \varphi ||_{\infty}+|P_{\varepsilon}(x)|$ with $||\varphi||_{\infty}:= \sup_{x \in \mathbb{R}}|\varphi(x)|<\infty$, which yields on the set $\mathbb{R} \setminus \Delta$ the bound
$$
|f(x)-P_{\varepsilon}(x)|\leq c|x|^{d},\quad x \in \mathbb{R} \setminus \Delta
$$
for some positive constant $c$. This implies that
$$
\mathcal{P}\left( B_{2}> \frac{\varepsilon}{6 } \right)\leq \mathcal{P}\left(  \bigg| \frac{1}{N}\sum_{j=1}^{N}|\lambda_{j}|^{d} \chi_{\mathbb{R}\setminus \Delta}(\lambda_{j})\bigg| > \frac{\varepsilon}{6c}\right)
$$
and so by [[Proof of Theorem 17.2#^843bba|Lemma 17.17]] the term also tends to zero. 
This completes our proof. 