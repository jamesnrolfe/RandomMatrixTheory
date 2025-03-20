#Notes 

The concept of a **real Wigner matrix** is a generalisation of the construction for the GOE, in the we no longer impose a concrete distribution on the values (i.e. it can be anything now).

>[!info] Definition 17.1
>Start with two independent families of i.i.d. random variables (real-valued) which we name 
>$$(Z_{j,k})_{1\leq j<k\leq N};\quad(Y_{j})_{j=1}^{N}$$
>such that
>$$\begin{align} \mathbb{E}[Z_{1,2}] & =\mathbb{E}[Y_{1}]=  0 \\
 \mathbb{E}[Z_{1,2}^2] & =t>0\end{align}$$
 >> [!help] Note
 >> Here we are basically saying the distributions are centered around zero, and have positive second moment,.
 >
 >We also say that for all $k \in \mathbb{N}$:
 >$$r_{k}:= \text{max}(\mathbb{E}[|Z_{1,2}|^{k}], \mathbb{E}[|Y_{1}|^{k}])<\infty$$
 >The, the **real Wigner ensemble** is the set of all real symmetric matrices $\mathcal{M}_{N}=(\xi_{j,k})_{j,k=1}^{N}$ of size $N\times N$ with entries
 >$$\xi_{j,k}=\frac{1}{\sqrt{ N }}  \begin{cases} Z_{j,k} & j<k \\
Z_{k,j} & j>k \\
Y_{j} & j=k\end{cases}$$

As before, we let $(\lambda_{j}(\mathcal{M}_{N}))^N_{j=1}\subset \mathbb{R}$ denote the eigenvalues of a real Wigner matrix $\mathcal{M}_{N}$, indexed in non-decreasing order i.e.

$$
-\infty<\lambda_{1}\leq\dots\leq \lambda_{N}<\infty
$$

The original result for real Wigner matrices asserts convergence of the normalised counting measure $\bar{\mathcal{N}}_{N}$ to the semicircle distribution or law - that is to the probability distribution with density

$$
\sigma_{t}(x):= \frac{1}{2\pi t}\sqrt{ (4t-x^2)_{+} }
$$

Recall that $\frac{t}{N}$ is the off-diagonal entry variance. In the GUE case, $t=\frac{1}{2}$ (see how the above converges to [[Bulk of the spectrum#^b35f3e|Wigner's semicircle law for the GUE]]). More precisely, we have the following Theorem.

>[!info] Theorem 17.2 
>Let $\Delta \subset \mathbb{R}$ be an interval and $\mathcal{M}_{N}$ a real Wigner matrix of size $N\times N$, with eigenvalues $-\infty<\lambda_{1}\leq\dots\leq \lambda_{N}<\infty$. Then, the normalised counting measure satisfies for all $\epsilon>0$:
>$$\lim_{ N \to \infty } \mathcal{P}\left( \Big| \bar{\mathcal{N}}_{N}(\Delta)-\int_{\Delta}\sigma_{t}(x)dx \Big| > \epsilon\right)=0$$
>or if instead we used any continuous bounded function $\varphi:\mathbb{R}\to \mathbb{C}$, then the linear statistic obeys
>$$\lim_{ N \to \infty } \left( \Big| \frac{1}{N}\mathcal{N}_{N}[\varphi]-\int_{\mathbb{R}}\varphi(x)\sigma_{t}(x)dx \Big|>\epsilon \right)=0$$
>>[!help] Note
>>Essentially what this is saying is that in the large $N$ limit, the normalised counting measure / linear statistic becomes (almost) equal to the integral on the right.

An important special case is when $\varphi(x)=x^{k}$. We might see that this is unbounded, but apparently that just doesn't matter. We have the following result.

>[!info] Theorem 17.3
>Let $\mathcal{M}_{N}$ be a real Wigner matrix of dimension $N$. Then, for any fixed $k \in \mathbb{N}$ and $\epsilon>0$ we have
>$$\lim_{ N \to \infty } \mathcal{P}\left( \Big| \frac{1}{N}\mathrm{Tr} (\mathcal{M}_{N}^{k})-\int_{\mathbb{R}}x^{k}\sigma_{t}(x)dx\Big| >\epsilon\right)=0$$
>We can see that the integral describes the $k$th moment of $\sigma_{t}(x)$.
>(*see [[Proof of Theorem 17.3]]*)

^06ccc5

So, we wan't to start calculating the moments of the semicircle law. For any $k \in \mathbb{N}$, define the *moments* of the semicircle law as
$$m_{k}:= \int_{\mathbb{R}}x^{k}\sigma_{1}(x)dx$$ 
We make use of the following lemmas.

>[!info] Lemma 17.4 (a)
> For any $t>0$, we have
> $$\int_{\mathbb{R}}x^{k}\sigma_{t}(x)dx=t^{\frac{k}{2}}m_{k}$$
> > [!tldr] Proof
> > This first assertion comes from a change of variables. 
> > $$\begin{align}\int_{\mathbb{R}}x^{k}\sigma_{t}(x)dx  & = \frac{1}{2\pi t}\int_{\mathbb{R}}x^{k} \sqrt{ (4t-x^{2}) } dx \\
 \end{align}$$
 >> Let $x=t^{\frac{1}{2}}y$ such that 
 >> $$\begin{align}\frac{1}{2\pi t}\int_{\mathbb{R}}x^{k} \sqrt{ (4t-x^{2}) }  & = \frac{1}{2\pi t}\int_{\mathbb{R}}t^{\frac{k}{2}}y^{k} \sqrt{ (4t-ty^{2}) } t^{\frac{1}{2}}dy  \\
 \\
 & = \int_{\mathbb{R}}y^{k} \frac{1}{t} t^{\frac{k}{2}}t \sigma_{1}(y) dy \\
 \\
 & =t^{\frac{k}{2}} \int_{\mathbb{R}}y^{k} \sigma_{1}(y) dy = t^{\frac{k}{2}}m_{k}\end{align}$$
> >

^a90151

>[!info] Lemma 17.4 (b)
>We have $m_{0}=1$, $m_{2k-1}=0$ and then
>$$m_{2k}=\frac{2(2k-1)}{k+1}m_{2k-2}$$
>with the latter holding for $k \in \mathbb{N}$. Therefore:
>$$m_{2k}=\frac{1}{k+1}\binom{2k}{k} =: C_{k}$$
>where the numbers $C_{k}$ are the **Catalan numbers**.
>>[!tldr] Proof
>>The odd numbers are zero because we are integrating an odd function times an even function over $\mathbb{R}$ (giving us negative integral on one side which is equal and opposite to positive integral on the other, cancelling out to give zero overall). 
>>For the even numbers, consider the integral
>>$$m_{2k}=\int_{-2}^{+2} x^{2k} \sigma_{1}(x)dx$$
>>We can do a trigonometric substitution $x=2\sin \theta$ and the integral becomes
>>$$m_{2k}=\frac{2^{2k+1}}{\pi}\int^{\frac{\pi}{2}}_{-\frac{\pi}{2}} \sin^{2k}(\theta)\cos^{2}\theta d\theta$$ 
>>Then, using the fact that $\cos^{2}\theta=1-\sin^{2}\theta$, we can split the integral such that
>>$$m_{2k}= \frac{2^{2k+1}}{\pi}\left( \int^{\frac{\pi}{2}}_{-\frac{\pi}{2}}\sin^{2k}(\theta)d\theta-\int^{\frac{\pi}{2}}_{-\frac{\pi}{2}} \sin^{2k+1}(\theta)\sin (\theta)d\theta \right)$$
>>and then integrate the second integral by parts to find
>>$$m_{2k}=\frac{2^{2k+1}}{\pi}\int^{\frac{\pi}{2}}_{-\frac{\pi}{2}}\sin^{2k}(\theta)d\theta-(2k+1)m_{2k}$$
>>such that we find for any $k\in \mathbb{N}$ we can relate the $2k$th moment to the previous integer moment
>>$$m_{2k}=\frac{2^{2k}}{\pi(k+1)}\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}\sin^{2k}(\theta)d\theta=\frac{2^{2k}}{\pi(k+1)}\int^{\frac{\pi}{2}}_{-\frac{\pi}{2}}\sin^{2k-1}(\theta)\sin(\theta)d\theta=\frac{2(2k-1)}{k+1}m_{2k-2}$$
>>This completely determines the even moments (when combined with $m_{0}=1$). 

^7ec087

The Catalan numbers in [[Real Wigner matrices - traces, moments and combinatorics#^7ec087|Lemma 17.4 (b)]] possess several combinatorial interpretations and appear in many other scenarios. One that will feature prominently is related to **simple walks** on $\mathbb{Z}$. 

>[!info] Definition 17.5
>An integer-valued sequence $(S_{n})_{n=0}^{\ell}$ is called a **Bernoulli walk** of length $\ell \in \mathbb{N}$ if $S_{0}=0$ and $|S_{n+1}-S_{n}|=1$ for $n\leq \ell-1$.
>>[!help] Note
>>So this basically says that if each sequence is separated by one, and we start at zero, then it is a Bernoulli walk. So, we might go $0, 1, 0, 1, 2, 1, 0, -1, \dots$.
>
>A **Dyck path** of length $2k$ is a non-negative Bernoulli walk of length $\ell=2k$ that terminates at $S_{2k}=0$.![[Screenshot 2025-03-16 at 16.15.02.png]]

^418ec4

We can count the number of possible Dyck paths of length $2k$. 

>[!info] Lemma 17.6
>Let $D_{k}$ denote the number of Dyck paths of length $2k$ with $k \in \mathbb{N}$. Then
>$$D_{k}=C_{k}< 4^{k}$$
>Further, the generating function
>$$\hat{D}(z) := 1+\sum_{k=1}^{\infty}D_{k}z^{k}$$
>satisfies, for $|z| < \frac{1}{4}$,
>$$\hat{D}(z)=\frac{1}{2z} (1-(1-4z)^{\frac{1}{2}})$$
>>[!tldr] Proof
>>We let $B_{k}$ denote the number of Bernoulli walks $(S_{n})_{n=0}^{2k}$ (so of length $2k$) that satisfy $S_{2k}=0$. We also let $\beta_{k}$ be the number of Bernoulli walks $(S_{n})_{n=0}^{2k}$ (also of length $2k$) that satisfy $S_{2k}=0$ *and* $S_{m}<0$ for some $m<2k$ (so these are not [[Real Wigner matrices - traces, moments and combinatorics#^418ec4|Dyck paths]] since the can be negative). Evidently,
>>$$D_{k}=B_{k}-\beta_{k}$$
>>>[!help] Note
>>>This is true since the total number of Dyck paths is all the paths that end at 0, minus all the paths that are negative (that also end at 0).
>>
>>We can also say that $B_{k}=\binom{2k}{k}$, since we need as many up and down steps to return to zero when starting from $S_{0}=0$.
>>On the other hand, perform the following procedure. Take a path $(S_{n})_{n=0}^{2k}$ that crosses the $x$-axis at some point. Let the first crossing be at the step $m$, so $S_{m}<0$. Define a reflected copy of the path $(\bar{S}_{n})_{n=0}^{2k}$ that takes the *reflected step* to $(S_{n})_{n=0}^{2k}$ for all steps after step $m$. ![[Screenshot 2025-03-16 at 16.25.34.png]]
>>Hence, $\bar{S}_{2k}=-2$ and $\beta_{k}$ equals the number of Bernoulli walks $(S_{n})_{n=0}^{2k}$ of length $2k$ that terminate at $-2$.
>>In turn, $\beta_{k}=\binom{2k}{k+1}=\binom{2k}{k-1}$ as one needs two more down steps to end up at $S_{2k}=-2$ when starting from $S_{0}=0$. All together, we can say
>>$$D_{k}=\binom{2k}{k}-\binom{2k}{k-1}=\frac{1}{k+1}\binom{2k}{k}=C_{k}$$
>>for any $k \in \mathbb{N}$ and $C_{k}$ are the [[Real Wigner matrices - traces, moments and combinatorics#^7ec087|Catalan numbers]], equal to $m_{2k}$ from [[Real Wigner matrices - traces, moments and combinatorics#^7ec087|Lemma 17.4 (b)]]. At each step of a Bernoulli walk, we can either go up or down, and so the number of possible Bernoulli walks is less than the total number of paths $2^{2k}=4^{k}$ i.e.
>>$$D_{k} < 4^{k}$$
>>We can use this to show that the power series of $\hat{D}(z)$ is absolutely convergent for $|z| < \frac{1}{4}$, and so $\hat{D}(z)$ is analytic in the open disk $|z| < \frac{1}{4}$.
>>>[!help] Note
>>>This is true because a power series $\sum_{k=1}^{\infty}r^{k}$ will converge for $|r|<1$. Here we have that $D_{k}<4^{k}$, and so 
>>>$$\sum^{\infty}_{k=1}D_{k}z^{k} \leq \sum_{k=1}^{\infty}(4z)^{k}$$
>>>which will converge for $|z| < \frac{1}{4}$ (making the overall base $|4z|<1$).
>>
>>Now, if a Bernoulli walk starts and ends at 0, then we could equally consider 'breaking' the walk at step $2p$ for some $1\leq p\leq k$ and count all the ways we could return to 0 in $2p$ steps, multiplied by all the ways we could return to the 'breakpoint' in $2k-2p$ steps.
>>This then gives the relations 
>>$$\begin{align} D_{0} & =1   \\
D_{k} & =\sum_{p=1}^{k}D_{p-1}D_{k-p}\end{align}$$
>> Putting these relations into the definition of $\hat{D}(z)$
>> $$\hat{D}(z) = 1+\sum_{k=1}^{\infty}D_{k}z^{k}$$
>> with $|z| < \frac{1}{4}$, we find
>> $$\begin{align}\hat{D}(z)-1  & = \sum_{k=1}^{\infty}\left( \sum_{p=1}^{k}D_{p-1}D_{k-p} \right)z^{k} \\
 \\
 & = z \sum_{k=0}^{\infty}\left( \sum_{p=0}^{k}D_{p}D_{k-p} \right)z^{k} \\
 \\
 & = z \left( \sum_{k=0}^{\infty}D_{k}z^{k} \right)\left( \sum_{p=0}^{\infty}D_{p}z^{k} \right)=z (\hat{D}(z))^{2}\end{align}$$
 >> and hence we are left with a quadratic 
>> $$z(\hat{D}(z))^{2}-\hat{D}(z)+1=0$$
>> Solving this equation, we find
>> $$\hat{D}(z)=\frac{1 \pm \sqrt{ 1-4z }}{2z}$$
>> We want to keep $\hat{D}(0)=1$, and so in this case, we keep the minus sign. Then we end up with
>> $$\hat{D}(z)=\frac{1}{2z} (1-(1-4z)^{\frac{1}{2}})$$
>> as required.

We will also quickly define the **Stieltjes transform** $S(z)$ of the semicircle law ($t=1$) for $z \in \mathbb{C}$ such that $z \not\in [-2,2] \subset \mathbb{R}$ as 

$$S(z):= \int_{\mathbb{R}} \frac{\sigma_{1}(\lambda)}{\lambda-z} d\lambda=-\frac{1}{2}(z-(z^{2}-4)^{\frac{1}{4}})$$

which we will see later on. 