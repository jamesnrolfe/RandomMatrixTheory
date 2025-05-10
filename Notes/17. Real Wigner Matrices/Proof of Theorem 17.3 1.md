#Notes 

The theorem is restated here for convenience. 

>Let $\mathcal{M}_{N}$ be a real Wigner matrix of dimension $N$. Then, for any fixed $k \in \mathbb{N}$ and $\epsilon>0$ we have
>$$\lim_{ N \to \infty } \mathcal{P}\left( \Big| \frac{1}{N}\mathrm{Tr} (\mathcal{M}_{N}^{k})-\int_{\mathbb{R}}x^{k}\sigma_{t}(x)dx\Big| >\epsilon\right)=0$$
>We can see that the integral describes the $k$th moment of $\sigma_{t}(x)$.

To do this, we will follow this plan.

*Step 1*
Show that as $N\to \infty$, ^993ad6
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

If we can show these two things, then [[Real Wigner matrices - traces, moments and combinatorics#^06ccc5|Theorem 17.3]] follows via [[Markov's and Chebyshev's Inequality]] and [[Real Wigner matrices - traces, moments and combinatorics#^a90151|Lemma 17.4 (a)]]. To see how this would work, abbreviate 

$$
X_{N,k}:= \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k})
$$

with $N,k \in \mathbb{N}$. Then, we have
$$
\mathcal{P}_{N}\left(|X_{N,k}-t^{\frac{k}{2}}m_{k}|> \epsilon\right)\leq \mathcal{P}\left( |X_{N,k}-\mathbb{E}_{N}[X_{N,k}]|< \frac{\epsilon}{2} \right)+\mathcal{P}\left( |\mathbb{E}_{N}[X_{N,k}]-t^{\frac{k}{2}}m_{k}|> \frac{\epsilon}{2} \right)
$$
(triangle identity) where we can note that the first probability is the same as the one in the theorem we are trying to prove.
By the equation in step 1, and [[Real Wigner matrices - traces, moments and combinatorics#^a90151|Lemma 17.4 (a)]], as $N\to \infty$, 
$$
\mathbb{E}_{N}[X_{N,k}] \to t^{\frac{k}{2}}m_{k}
$$
for $k\in \mathbb{N}$. Hence, the second summand $\mathcal{P}\left( |\mathbb{E}_{N}[X_{N,k}]-t^{\frac{k}{2}}m_{k}|> \frac{\epsilon}{2} \right)$ will be zero for sufficiently large $N$. 

To conclude we examine the first summand $\mathcal{P}\left( |X_{N,k}-\mathbb{E}_{N}[X_{N,k}]|< \frac{\epsilon}{2} \right)$. By [[Markov's and Chebyshev's Inequality]], as $N \to \infty$,
$$
\mathcal{P}\left( |X_{N,k}-\mathbb{E}_{N}[X_{N,k}]|< \frac{\epsilon}{2} \right)\leq \frac{4}{\epsilon^{2}}\text{Var}(X_{N,k})
$$
for all $k\in \mathbb{N}$ - but step 2 would prove that this tends to zero. 

Thus, this is enough to find [[Real Wigner matrices - traces, moments and combinatorics#^06ccc5|Theorem 17.3]].

##### Proof of step 1

First for any $\mathcal{M}_{N}=(\xi_{j,k})_{j,k=1}^{N}$ by linearity of expectation we can say

$$
\frac{1}{N} \mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\frac{1}{N}\mathbb{E}\left[ \sum_{j_{1},\dots,j_{k}=1}^{N} \xi_{j_{1},j_{2}}\xi_{j_{2},j_{3}}\dots \xi_{j_{k-1},j_{k}}\xi_{j_{k},j_{1}}\right] =: \frac{1}{N}\sum_{\boldsymbol{j} \in \{ 1,\dots,N \}^{k}}\mathbb{E}[\xi_{\boldsymbol{j}}]
$$

where given the vector $\boldsymbol{j}:= (j_{1},\dots,j_{k})$ we define $\xi_{\boldsymbol{j}}=\xi_{j_{1},j_{2}}\xi_{j_{2},j_{3}}\dots \xi_{j_{k-1},j_{k}}\xi_{j_{k},j_{1}}$.

>[!help] Note
>This can be seen by finding the trace of a matrix manually for small $k$s. Consider $k=N=2$. Then
>$$\mathcal{M}_{2}^{2}=\begin{pmatrix}\xi_{1,1} & \xi_{1,2} \\ \xi_{2,1} & \xi_{2,2}\end{pmatrix}\begin{pmatrix}\xi_{1,1} & \xi_{1,2} \\ \xi_{2,1} & \xi_{2,2}\end{pmatrix}=\begin{pmatrix}\xi_{1,1}^{2}+\xi_{1,2}\xi_{2,1} & \xi_{1,1}\xi_{1,2}+\xi_{1,2}\xi_{2,2} \\
\xi_{2,1}\xi_{1,1}+\xi_{2,2}\xi_{2,1} & \xi_{2,1}\xi _{1,2}+\xi_{2,2}^{2}\end{pmatrix}$$
> Then, $\mathrm{Tr}(\mathcal{M}_{2}^{2})=\xi_{1,1}^{2}+2\xi_{1,2}\xi_{2,1}+\xi_{2,2}^{2}$. Let's see if this is the same as the sum above.
> $$\sum^{2}_{j_{1},j_{2}=1}\xi_{j_{1},j_{2}}\xi_{j_{2},j_{1}}=\xi_{1,1}\xi_{1,1}+\xi_{1,2}\xi_{2,1}+\xi_{2,2}\xi_{2,2}=\mathrm{Tr}(\mathcal{M}_{2}^{2})$$

To solve problems using this, we will start to use **graphs**.

>[!info] Definition 17.7
> Let $\boldsymbol{j}=(j_{1},\dots,j_{k})\in \{ 1,\dots,N \}^{k}$. The **graph** $G_{\boldsymbol{j}}=(V_{\boldsymbol{j}},E_{\boldsymbol{j}})$ associated with $\boldsymbol{j}$ is defined as follows:
> - The set of vertices $V_{\boldsymbol{j}}$ consists of the *distinct* elements elements of $\{ j_{1},j_{2}, \dots,j_{k} \}$. So if we had $\boldsymbol{j}=(1,2,4,2)$ then $V_{\boldsymbol{j}}=\{ 1,2,4 \}$.
> - The set of edges $E_{\boldsymbol{j}}$ consists of the *distinct* pairs amongst $\{ j_{1},j_{2} \},\{ j_{2},j_{3} \},\dots,\{ j_{k-1},j_{k} \},\{ j_{k},j_{1} \}$. So, for our above example, it is $E_{\boldsymbol{j}}=\{ \{ 1,2 \},\{ 2,4 \} \}$ (these are the only *distinct* edges. Here, direction doesn't make a path distinct, so $\{ 1,2 \}=\{ 2,1 \}$).
> - The *walk* $w_{\boldsymbol{j}}$ associated with $\boldsymbol{j}$ is given by the edge sequence
> $$w_{\boldsymbol{j}}:= (\{ j_{1},j_{2} \},\{ j_{2},j_{3} \},\dots,\{ j_{k-1},j_{k} \},\{ j_{k},j_{1} \})$$
> So in our example $w_{\boldsymbol{j}}=(\{ 1,2 \},\{ 2,4 \}, \{ 4,2 \}, \{ 2,1 \})$.
> Note that the walk visits each edge of $G_{\boldsymbol{j}}$ including any *self-edges* (so this might be $\{ 2,2 \}$) present, and it begins and ends at the vertex $j_{1}$. This means in particular that the graph $G_{\boldsymbol{j}}$ is connected. 
> Also, the walk $w_{\boldsymbol{j}}$ encodes a labelling of the edges $E_{\boldsymbol{j}}$ in that it implicitly counts the number of times each edge is traversed. Then, for each edge $e \in \{ E_{\boldsymbol{j}} \}$ we write
> $$w_{\boldsymbol{j}}(e)=|\{ e'=\{ e_{1},e_{2} \} \in E_{\boldsymbol{j}} : e'=e \}|$$
> for the number of times the walk traverses the edge $e$. So simply put, $w_{\boldsymbol{j}}(e)$ is a way to denote the number of times the edge $e=\{ e_{1},e_{2} \}$ is traversed.

>[!example] Example 17.8
>Let's say we have some vector
>$$\boldsymbol{j}=(1,2,2,3,5,2,4,1,4,2)\in \{ 1,\dots,5 \}^{10}$$
>Then, the *vertex set* $V_{\boldsymbol{j}}$ is
>$$V_{\boldsymbol{j}}=\{ 1,2,3,4,5 \}$$
>(all the distinct vertices) and the *edge set* $E_{\boldsymbol{j}}$ is
>$$E_{\boldsymbol{j}}=\{ \{ 1,2 \},\{ 2,2 \},\{ 2,3 \},\{ 3,5 \},\{ 5,2 \},\{ 2,4 \},\{ 4,1 \} \}$$
>(all the distinct edges).
> The corresponding *walk* is then 
> $$w_{\boldsymbol{j}}=(\{ 1,2 \},\{ 2,2 \},\{ 2,3 \},\{ 3,5 \},\{ 5,2 \},\{ 2,4 \},\{ 4,1 \},\{ 1,4 \},\{ 4,2 \},\{ 2,1 \})$$
> which defines a walk on the graph $G_{\boldsymbol{j}}=(V_{\boldsymbol{j}},E_{\boldsymbol{j}})$.![[Screenshot 2025-03-21 at 14.19.14.png]]
> The first graph here shows the edges, and the second shows the edges and the walk. Notice that the walk is directional and the order matters.
> Also, by symmetry and construction of $M_{N}=(\xi_{j,k})_{j,k=1}^{N}$, we can say
> $$\xi_{\boldsymbol{j}}=\xi_{1,2}\xi_{2,2}\xi_{2,3}\xi_{3,5}\xi_{5,2}\xi_{2,4}\xi_{4,1}\xi_{1,4}\xi_{4,2}\xi_{2,1}\quad \text{s.t.}\quad\mathbb{E}[\xi_{\boldsymbol{j}}]=\frac{1}{(\sqrt{ N })^{10}} Z_{1,2}^{2}Z_{1,4}^{2}Z_{2,4}^{2}Y_{2}Z_{2,3}Z_{2,5}Z_{3,5}$$
> where we defined the matrix elements [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]]. 
> For the number of times edges are traversed, we have for example 
> $$w_{\boldsymbol{j}}(\{ 1,2 \})=2$$
> where we have simply counted the number of times $\{ 1,2 \}$ or $\{ 2,1 \}$ occur in $w_{\boldsymbol{j}}$.

^4ba195

The observations in [[Proof of Theorem 17.3#^4ba195|Example 17.8]] are true in general, so if we exploit the independence and i.i.d. assumptions of [[Real Wigner matrices - traces, moments and combinatorics#^418ec4|Definition 17.1]], the following compact expression for $\mathbb{E}[\xi_{\boldsymbol{j}}]$ in the equation

$$
\frac{1}{N} \mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\frac{1}{N}\mathbb{E}\left[ \sum_{j_{1},\dots,j_{k}=1}^{N} \xi_{j_{1},j_{2}}\xi_{j_{2},j_{3}}\dots \xi_{j_{k-1},j_{k}}\xi_{j_{k},j_{1}}\right] =: \frac{1}{N}\sum_{\boldsymbol{j} \in \{ 1,\dots,N \}^{k}}\mathbb{E}[\xi_{\boldsymbol{j}}]
$$

^07a70b

arises as

$$
\mathbb{E}[\xi_{\boldsymbol{j}}]=\frac{1}{(\sqrt{ N })^{k}}\prod_{e \in E^{s}_{\boldsymbol{j}}} \mathbb{E}[Y_{1}^{w_{\boldsymbol{j}}(e)}]\prod_{e \in E_{\boldsymbol{j}}^{c}}\mathbb{E}[Z_{1,2}^{w_{\boldsymbol{j}}(e)}]
$$

where $E^{s}_{\boldsymbol{j}} := \{ \{ e_{1},e_{1} \} \in E_{\boldsymbol{j}}\}$ is the set of all *self-edges*, and $E^{c}_{\boldsymbol{j}}:= \{ \{ e_{1},e_{2} \} \in E_{\boldsymbol{j}}: e_{1} \neq e_{2} \}$ is the set of all *connecting edges*. 

>[!help] Note
>Why does this work? Well, in [[Proof of Theorem 17.3#^4ba195|Example 17.8]], we said that 
>$$\mathbb{E}[\xi_{\boldsymbol{j}}]=\frac{1}{(\sqrt{ N })^{10}} Z_{1,2}^{2}Z_{1,4}^{2}Z_{2,4}^{2}Y_{2}Z_{2,3}Z_{2,5}Z_{3,5}$$
>where the $Z$ terms correspond to off-diagonal terms, which by definition come from *connecting edges* (since the bottom indicies are *not* the same) and the $Y$ terms correspond to diagonal terms, which similarly come from *self-edges* (since the bottom indicies are the same). Hence, it is relatively clear how we get the above expression for $\mathbb{E}_{\xi_{\boldsymbol{j}}}$.

What this tells us in particular, is that the value of $\mathbb{E}[\xi_{\boldsymbol{j}}]$ is solely determined by the pair $(G_{\boldsymbol{j}}, w_{\boldsymbol{j}})$. This means that each graph might give a different result if the walk is different (i.e. the order of $\boldsymbol{j}$). We then abbreviate 

$$
\Pi (G_{\boldsymbol{j}}, w_{\boldsymbol{j}}):= \prod_{e \in E^{s}_{\boldsymbol{j}}} \mathbb{E}[Y_{1}^{w_{\boldsymbol{j}}(e)}]\prod_{e \in E_{\boldsymbol{j}}^{c}}\mathbb{E}[Z_{1,2}^{w_{\boldsymbol{j}}(e)}]
$$

Next, for any vector $\boldsymbol{j}\in \{ 1,\dots,N \}^{k}$, the connected graph $G_{\boldsymbol{j}}$ has at most $k$ vertices, and for all $e \in E_{\boldsymbol{j}}$ we have 

$$
|w_{\boldsymbol{j}}| := \sum_{e \in E_{\boldsymbol{j}}}w_{\boldsymbol{j}}(e) = k
$$

i.e. the modulus of the walk is just the sum of all the values in the walk, which is equal to $k$ (the maximum value of the number of vertices). 

>[!info] Definition 17.9
>Let $\mathcal{G}_{k},k \in \mathbb{N}$ denote the set of all pairs $(G,w)$ where $G=(V,E)$ is a connected graph with at most $k$ vertices given by the set $V$ and edges given by the set $E$, and $w$ is a closed walk covering $G$ and satisfying $|w|=k$.
>>[!help] Note
>>So this is basically saying that $\mathcal{G}_{k}$ is the set of all graph-walk pairs that have a walk of length $k$. So $\mathcal{G}_{1}=(G,w: |w|=1)$, *plus* the over conditions outlined above (these are usually the case for our purposes).

^4cb70f

We can then 'reindex' the sum 

$$
\frac{1}{N} \mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\frac{1}{N}\mathbb{E}\left[ \sum_{j_{1},\dots,j_{k}=1}^{N} \xi_{j_{1},j_{2}}\xi_{j_{2},j_{3}}\dots \xi_{j_{k-1},j_{k}}\xi_{j_{k},j_{1}}\right] =: \frac{1}{N}\sum_{\boldsymbol{j} \in \{ 1,\dots,N \}^{k}}\mathbb{E}[\xi_{\boldsymbol{j}}]
$$

as

$$
\begin{align}
 \frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})] & =\frac{1}{N}\sum_{i \in \{ 1,\dots,N \}^{k}}\mathbb{E}[\xi_{\boldsymbol{i}}] \\ \\
 & = \sum_{(G,w) \in \mathcal{G}_{k} }\sum_{j\in \{ 1,\dots,N \}^{k}; (G_{\boldsymbol{j}},w_{\boldsymbol{j}})=(G,w)} \frac{1}{N}\mathbb{E}[\xi_{\boldsymbol{j}}] \\
 \\
 & =\frac{1}{N} \sum_{(G,w)\in \mathcal{G}_{k}} \Pi(G,w) \frac{|\{ j \in \{ 1,\dots ,N \}^{k}:(G_{j},w_{j})=(G,w) \}|}{(\sqrt{ N })^{k}}
\end{align}
$$

>[!help] Note
>So this looks scary. In the second line, we essentially sum over all the graph-walk pairs that satisfy our conditions, and then all the $\boldsymbol{j}$ vector combinations for each of those pairs. 
>Then, we expand out the expectation value in terms of our $\Pi$ function, multiplied by the number of sets that satisfy the conditions (this is what the modulus of the set does).

So, we are now left to count the sets of vectors $\boldsymbol{j}$. For a fixed, but arbitrary, $(G,w)\in \mathcal{G}_{k}$, an index $\boldsymbol{j} \in \{ 1,\dots,N \}^{k}$ with that corresponding graph $G$ and walk $w$ is *completely determined* by assigning which distinct values from $\{ 1,\dots,N \}$ appear as the vertices of $G$. 

For the first vertex, we have $N$ ways of choosing the value. For the second, we have $N-1$ ways, then $N-2$ ways etc. all the way down to the number of vertices such that the last choice has $N-|G|+1$ choices. So, there are 

$$
N(N-1)(N-2)\dots(N-|G|+1)
$$

ways to chose which distinct values from $\{ 1,\dots,N \}$ fall into $G$.

>[!info] Lemma 17.10
>Given $(G,w ) \in \mathcal{G}_{k}$ with $k \in \mathbb{N}$, denote by $|G|$ the number of vertices in $G$. Then
>$$|\{ \boldsymbol{j} \in \{ 1,\dots, N \}^{k}: (G_{\boldsymbol{j}}, w_{\boldsymbol{j}})=(G,w) \}|=N(N-1)\dots(N-|G|+1)$$

^695984

Then, the equation before simplifies to 

$$
\frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\sum_{(G,w)\in\mathcal{G}_{k}}\Pi(G,w) \frac{N(N-1)\dots(N-|G|+1)}{N^{\frac{k}{2}+1}}
$$

We are now going to try and figure out the value of $\Pi(G,w)$. In it, it contains the terms

$$
\mathbb{E}[Y_{1}^{w(e)}]\quad\text{and}\quad\mathbb{E}[Z_{1,2}^{w(e)}]
$$

Remember from [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]] that these distributions $Y$ and $Z$ are centered. This means that $\mathbb{E}[Y_{1}]=\mathbb{E}[Z_{1,2}]=0$ such that then $w(e)=1$, both terms are zero. So, we actually only need to consider terms $w\geq 2$. We can write this as 

$$
\frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\sum_{(G,w)\in\mathcal{G}_{k}; \; w\geq 2}\Pi(G,w) \frac{N(N-1)\dots(N-|G|+1)}{N^{\frac{k}{2}+1}}
$$

Remember that $|w| = k$ is the *maximum* number of vertices a graph can have. Then, if each edge in $G$ is traversed at least twice, then the number of edges cannot exceed $\frac{k}{2}$. 

>[!info] Proposition 17.11
>Let $G=(V,E)$ be a finite connected graph. Then $|V|\leq|E|+1$ and $|V|=|E|+1$ *if and only if* $G$ is a **tree** (i.e. a connected graph not containing any cycles). 

^5c81fa

Using [[Proof of Theorem 17.3#^5c81fa|Proposition 17.11]] we can see that for any graph $G=(V,E)$ appearing in the sum in the right hand side of the equation above, we must have 

$$
|G| \leq \frac{k}{2}+1
$$

as the number of *edges* cannot exceed $\frac{k}{2}$. Consider then the fraction in the sum

$$
\frac{N(N-1)\dots(N-|G|+1)}{N^{\frac{k}{2}+1}}
$$

The order of the bottom fraction is $\frac{k}{2}+1$. The order of the top fraction is $|V|$. Hence, the fraction can be written in the limit as

$$
\frac{N^{|G|}}{N^{\frac{k}{2}+1}}
$$

Since $|G|\leq \frac{k}{2}+1$, in the case $|G|< \frac{k}{2}+1$, the above tends to 0 for large $N$. At equality, it tends to 1. 

Consider for a second that $k$ is odd. Since $|G|$ is integer valued, it follows that $|G| \leq \frac{k-1}{2}+1 < \frac{k}{2}+1$ (since if $k$ odd, then $\frac{k}{2}+1$ is not an integer, so we essentially have to go 'one-down' to still satisfy the inequality). 

Then, since we can then say $|G|< \frac{k}{2}+1$ (strictly less than), then it follows that the fraction

$$
\lim_{ N \to \infty } \frac{N(N-1)\dots(N-|G|+1)}{N^{\frac{k}{2}+1}} =0
$$

and so we can say that 

$$
\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{2k-1})] = 0
$$

which was part of our original condition in [[Proof of Theorem 17.3#^993ad6|step 1]]. 

To prove the rest of this then, we are going to assume that $k$ is even (so we will use $2k$ for the rest of the proof).

>[!info] Proposition 17.12
>Let $(G,w) \in \mathcal{G}_{k}$ with $k \in \mathbb{N}$ even and $w \geq 2$. Then, we have the following:
>1. If there exists any self-edge $e$ in $G$, then $|G|\leq \frac{k}{2}$.
>2. If there exists an edge $e$ in $G$ with $w(e)\geq 3$, then $|G|\leq \frac{k}{2}$.
>
>>[!tldr]+ Proof
>>If $G=(V,E)$ contains a self-edge, then it contains a cycle and hence it is *not* a tree. Then, by [[Proof of Theorem 17.3#^5c81fa|Proposition 17.11]], $|V| < |E|+1$. But, $w\geq 2$ implies that $|E|\leq \frac{k}{2}$ and so $|V|< \frac{k}{2}+1$ i.e. $|G|\leq \frac{k}{2}$ (since $|G|$ is integer valued). 
>>Next, if for some $e'$ we have $w(e')\geq 3$ then $\sum_{e \in E \not \{ e' \}}w(e)\leq k-3$ and thus 
>>$$|E| < 1+ \frac{1}{2}(k-3) = \frac{1}{2}(k-1)$$
>> since $w \geq 2$. By [[Proof of Theorem 17.3#^5c81fa|Proposition 17.11]] then
>> $$|V|\leq \frac{1}{2}(k-1)+1=\frac{1}{2}(k+1)$$
>> but $k$ is even, so $|G|=|V| \leq \frac{k}{2}$. This completes our proof.

^2ec7d4

We can combine [[Proof of Theorem 17.3#^2ec7d4|Proposition 17.12]] with 

$$
\frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\sum_{(G,w)\in\mathcal{G}_{k}; \; w\geq 2}\Pi(G,w) \frac{N(N-1)\dots(N-|G|+1)}{N^{\frac{k}{2}+1}}
$$

and drastically refine the set $\mathcal{G}_{k}$ for even $k$.

>[!info] Definition 17.13
>Take an even positive integer $2\ell$. Let $\dot{\mathcal{G}}_{2\ell}$ be defined as the set of pairs $(G,w) \in \mathcal{G}_{2\ell}$ where $G$ has $\ell+1$ vertices and contains no self-edges, and the walk $w$ traverses every edge exactly twice. 

^0ade5a

Using [[Proof of Theorem 17.3#^0ade5a|Definition 17.13]] we can change the above equation into

$$
\frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\sum_{(G,w)\in \dot{\mathcal{G}_{k} }}\Pi(G,w) \frac{N(N-1)\dots(N-|G|+1)}{N^{\frac{k}{2}+1}}+O_{k}\left( \frac{1}{N} \right)
$$

Since $|G|=\frac{k}{2}+1$ for the $G$ appearing in the sum in the above, and so the numerator of the fraction can be approximated as $N^{\frac{k}{2}+1}$ for large $N$, we have that the fraction tends to 1, and so

$$
\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{k})]=\sum_{(G,w)\in \dot{\mathcal{G}_{2k}}} \Pi(G,w)
$$

for all $k \in \mathbb{N}$.

Thus, it remains to show that the outstanding sum in the above is equal to $t^{k}C_{k}$ to complete our proof. Well, if $(G,w) \in \dot{\mathcal{G}}_{k}$, then the number of edges $G$ is $\frac{k}{2}$ since $w$ traverses each edge exactly twice, and so $G$ must be a tree by [[Proof of Theorem 17.3#^5c81fa|Proposition 17.11]]. In particular, $G$ cannot contain any self-edges, and so the value $\Pi(G,w)$ can be reduced as:

$$
\Pi(G,w)= \prod_{e \in E^{c}}\mathbb{E}[Z_{1,2}^{w(e)}]=\prod_{e\in E^{c}}\mathbb{E}[Z_{1,2}^{2}]=t^{|E|}=t^{\frac{k}{2}}
$$

>[!help] Note
>A few things to note here. 
>- We remember that each edge is traversed exactly twice and so it is clear that $w(e)=2$ for all $e \in E^{c}$. 
>- We removed the product over $E^{s}$ since there are no self-edges.
>- We used [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]] to provide $\mathbb{E}[Z_{1,2}^{2}]=t$.

Consequently, from the penultimate equation, we can say for any $k\in \mathbb{N}$ that

$$
\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{2k})] = \sum_{(G,w)\in \dot{\mathcal G}_{2k}}\Pi(G,w)=\sum_{(G,w) \in \dot{\mathcal G}_{2k}}t^{\frac{k}{2}}=t^{k}|\dot{\mathcal G}_{2k}|
$$
Finally, to complete our derivation, we must enumerate the set $\dot{\mathcal G}_{2k}$. To do so, we consider the [[Real Wigner matrices - traces, moments and combinatorics#^418ec4|Dyck paths]]: given $(G,w)\in \dot{\mathcal G}_{2k}$, $k \in \mathbb{N}$ where $w=(w_{j_{1}}, w_{j_{2}},\dots,w_{j_{2k}})$ with $w_{j_{i}}\in E$, we define a sequence $d=d(G,w)\in \{ -1,1 \}^{2k}$ recursively as follows:

1. Set $d_{1}+=+1$.
2. For $i \in \{ 2,3,\dots,2k \}$, if $w_{j_{i}} \not\in \{ w_{j_{1}},w_{j_{2}},\dots,w_{j_{i-1}} \}$, set $d_{i}:= 1$, otherwise set $d_{i}:= -1$.
3. Put $d=d(G,w)=(d_{i})^{2k}_{i=1}$.

>[!help] Note
>So this is basically saying that we set a value equal to 1 in $d$ if we have not explored the edge in the walk yet, and equal to $-1$ if we have already. So, if we traverse each edge exactly twice, we should expect the same number of 1's and -1's (returning us to the original location at the end - a Dyck path).

>[!example] Example 17.14
>Consider $(G,w)\in \dot{\mathcal{G}}_{10}$ where $G$ is a tree with six vertices $\{ 1,2,3,4,5,6 \}$ with inner vertices $\{ 2,4 \}$ and $w$ denotes the walk
>$$w = (\{ 1,2 \},\{ 2,3 \},\{ 3,2 \}, \{ 2,4 \},\{ 4,5 \},\{ 5,4 \},\{ 4,6 \},\{ 6,4 \},\{ 4,2 \},\{ 2,1 \})$$
>also denoted in the following figure.![[Screenshot 2025-03-23 at 12.28.10.png]]
> Then, by the above recursion, we are going to go from $d_{1}=+1$ all the way to $d_{10}$. So, for $d_{2}$, consider $w_{j_{2}}=\{ 2,3 \}$. We have not explored this edge yet, so it should be $+1$. Mathematically, we have the condition
> $$w_{j_{2}} \not\in \{ w_{j_{1}} \}$$
> which is met, and so we have $+1$. 
> We can do this for all of the rest of the paths, and we find
> $$d=d(G,w)=(+1,+1,-1,+1,+1,-1,+1,-1,-1,-1)$$
> which we can check sums to 0 as expected (i.e. the change in the value from the start to the finish is zero - we end in the same place we start). We can view this as a *lattice path*, setting $P_{0}=(0,0)$ and $P_{i}=(i,d_{1}+\dots+d_{i})$ such that we can see a Dyck path appear.![[Screenshot 2025-03-23 at 12.44.38.png]]
> 

^3e59d9

Using the construction as in [[Proof of Theorem 17.3#^3e59d9|Example 17.14]] we can see that the map taking the pair $(G,w)$ to the Dyck path $d(G,W)$ is actually a bijection between $\dot{\mathcal G}_{2k}$ and the set of Dyck paths of length $2k$. Thus, by [[Real Wigner matrices - traces, moments and combinatorics#^1360ca|Lemma 17.6]]:

$$
|\dot{\mathcal G}_{2k}|=\beta _{k}=C_{k}
$$

Then, we can combine this with the result from earlier to finally show

$$
\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}[\mathrm{Tr}(\mathcal{M}_{N}^{2k})]=t^{k}C_{k}
$$

as we wanted. So, we finally have both cases and thus

$$
\frac{1}{N}\mathbb{E}_{N}[\mathrm{Tr}(\mathcal{M}_{N}^{\ell})] \to \begin{cases}
0 & \ell=2k-1 \\
t^{k}C_{k} & \ell=2k
\end{cases}
$$

which is the proof required in step 1. 

##### Proof of step 2

This furthers the ideas in the above proof. Remember that we want to prove that

$$
\lim_{ N \to \infty } \text{Var}\left( \frac{1}{N} \mathrm{Tr}(\mathcal{M}_{N}^{k}) \right) =0
$$

We can expand the variance out as follows:

$$
\begin{align}
\text{Var}\left( \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k}) \right) & =\mathbb{E}\left[ \left( \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k}) \right)^{2} \right]-\left( \mathbb{E}\left[ \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k}) \right] \right)^{2} \\
 \\
 & = \frac{1}{N^{2}}\sum_{\boldsymbol{i},\boldsymbol{j}\in \{ 1,\dots,N \}^{k}}(\mathbb{E}[\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}]-\mathbb{E}[\xi_{\boldsymbol{i}}]\mathbb{E}[\xi_{\boldsymbol{j}}])
\end{align}

$$

where as before, the values $\mathbb{E}[\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}]$ and $\mathbb{E}[\xi_{\boldsymbol{i}}]\mathbb{E}[\xi_{\boldsymbol{j}}]$ only depend on the vectors $\boldsymbol{i}$ and $\boldsymbol{j}$ through a certain graph structure underlying the $2k$-tuple $(\boldsymbol{i},\boldsymbol{j})$. 

Indeed, $G_{\boldsymbol{i}}=(V_{\boldsymbol{i}},E_{\boldsymbol{i}})$ and $G_{\boldsymbol{j}}=(V_{\boldsymbol{j}},E_{\boldsymbol{j}})$ are the graphs associated with $\boldsymbol{i}$ and $\boldsymbol{j}$ respectively, then consider the graph

$$
G_{\boldsymbol{i}} \cup G_{\boldsymbol{j}} := (V_{\boldsymbol{i}} \cup V_{\boldsymbol{j}}, E_{\boldsymbol{i}}\cup E_{\boldsymbol{j}})
$$

We will see this in the next example. 

>[!example] Example 17.15
>If $\boldsymbol{i}=(1,2,1,3,2,3)\in \{ 1,\dots,5 \}^{6}$ and $\boldsymbol{j}=(2,4,5,1,4,3)\in \{ 1,\dots,5 \}^{6}$. Then:
>$$\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}=(\xi_{1,2}\xi_{2,1}\xi_{1,3}\xi_{3,2}\xi_{2,3},\xi_{3,1})(\xi_{2,4}\xi_{4,5}\xi_{5,1}\xi_{1,4}\xi_{4,3}\xi_{3,2})$$
>and so
>$$\begin{align}V_{\boldsymbol{i}}\cup V_{\boldsymbol{j}} & =\{ 1,2,3,4,5 \} \\\\E_{\boldsymbol{i}}\cup E_{\boldsymbol{j}} & =\{ \{ 1,2 \}, \{ 1,3 \}, \{ 3,2 \}, \{ 2,4 \},\{ 4,5 \},\{ 5,1 \},\{ 1,4 \},\{ 4,3 \} \}\end{align}$$
> such that 
> $$G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}}=(\{ 1,2,3,4,5 \}, \{ \{ 1,2 \}, \{ 1,3 \}, \{ 3,2 \}, \{ 2,4 \},\{ 4,5 \},\{ 5,1 \},\{ 1,4 \},\{ 4,3 \} \})$$
![[Screenshot 2025-03-23 at 13.05.46.png]]
> Essentially, we "glue" the two graphs together, such that all vertices and edges of each remain.

^53c8d4
The product $\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}$ also gives rise to the two walks $w_{\boldsymbol{i}}$ and $w_{\boldsymbol{j}}$. However, as can be seen in [[Proof of Theorem 17.3#^53c8d4|Example 17.15]], these do not constitute a single walk of length $2k$, as there is no requirement for the endpoint of the first walk to coincide with the starting point of the second walk. 

Still, since we can recover $(G_{\boldsymbol{i}},w_{\boldsymbol{i}})$ and $(G_{\boldsymbol{j}},w_{\boldsymbol{j}})$ from $(G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}}, w_{\boldsymbol{i}},w_{\boldsymbol{j}})$, via the same reasoning as before, we say that the value of $\mathbb{E}[\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}]-\mathbb{E}[\xi_{\boldsymbol{i}}]\mathbb{E}[\xi_{\boldsymbol{j}}]$ is determined by the data $(G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}}, w_{\boldsymbol{i}},w_{\boldsymbol{j}})$. We can denote this value

$$
\mathbb{E}[\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}]-\mathbb{E}[\xi_{\boldsymbol{i}}]\mathbb{E}[\xi_{\boldsymbol{j}}]=: \frac{1}{N^{k}}\Pi(G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}},w_{\boldsymbol{i}},w_{\boldsymbol{j}})
$$

and then we can generalise [[Proof of Theorem 17.3#^4cb70f|Definition 17.9]] to the current setting.

>[!info] Definition 17.16
>Let $\mathcal{G}_{k,k}, k \in \mathbb{N}$ denote the set of all triples $(G,w,w')$ where $G=(V,E)$ is a connected graph (with vertices $V$ and edges $E$) with at most $2k$ vertices, and $w$, $w'$ are closed walks whose union covers $G$ and which satisfy $|w|=|w'|=k$. 

This means we can expand as before 

$$
\begin{align}
 & \text{Var}\left( \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k}) \right) \\
 \\
 & =\sum_{(G,w,w') \in \mathcal{G}_{k,k}} \Pi(G,w,w') \frac{|\{ (\boldsymbol{i},\boldsymbol{j}) \in \{ 1,\dots,N \}^{2k}:()G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}},w_{\boldsymbol{i}},w_{\boldsymbol{j}})=(G,w,w')\}|}{N^{k+2}}
\end{align}

$$

Next, we let $E^{s}_{\boldsymbol{i},\boldsymbol{j}}$ and $E^{c}_{\boldsymbol{i},\boldsymbol{j}}$ be the self and connecting edges, and $w_{\boldsymbol{i},\boldsymbol{j}}(e)$ be the number of times the edge $e \in E_{\boldsymbol{i}}\cup E_{\boldsymbol{j}}$ is traversed by *either* of the two walks $w_{\boldsymbol{i}}, w_{\boldsymbol{j}}$. Then, by [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]] we have

$$
\begin{align}
\Pi(G_{\boldsymbol{i}} & \cup G_{\boldsymbol{j}},w_{\boldsymbol{i}},w_{\boldsymbol{j}}) \\
 \\
 & = \prod_{e \in E^{s}_{\boldsymbol{i},\boldsymbol{j}}} \mathbb{E}[Y_{1}^{w_{\boldsymbol{i},\boldsymbol{j}}(e)}] \prod_{e \in E^{c}_{\boldsymbol{i},\boldsymbol{j}}} \mathbb{E}[Z_{1,2}^{w_{\boldsymbol{i},\boldsymbol{j}}(e)}]  \\
  &\quad -\prod_{e \in E^{s}_{\boldsymbol{i}}} \mathbb{E}[Y_{1}^{w_{\boldsymbol{i}}(e)}] \prod_{e \in E^{c}_{\boldsymbol{i}}} \mathbb{E}[Z_{1,2}^{w_{\boldsymbol{i}}(e)}] \prod_{e \in E^{s}_{\boldsymbol{j}}} \mathbb{E}[Y_{1}^{w_{\boldsymbol{j}}(e)}] \prod_{e \in E^{c}_{\boldsymbol{j}}} \mathbb{E}[Z_{1,2}^{w_{\boldsymbol{j}}(e)}] 
\end{align}

$$

The key thing to note is that

$$
\sum_{e\in E_{\boldsymbol{i}}\cup E_{\boldsymbol{j}}}w_{\boldsymbol{i},\boldsymbol{j}}(e)=2k=\sum_{e \in E_{\boldsymbol{i}}}w_{\boldsymbol{i}}(e)+\sum_{e \in E_{\boldsymbol{j}}}w_{\boldsymbol{j}}(e)
$$

that is, the sum of all exponents in either term $\mathbb{E}[\xi_{\boldsymbol{i}}\xi_{\boldsymbol{j}}]$ or $\mathbb{E}[\xi_{\boldsymbol{i}}]\mathbb{E}[\xi_{\boldsymbol{j}}]$ is the total length of the walk (i.e. $2k$). Thus, using the bound in [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]]:

$$
r_{k} =\text{max}(\mathbb{E}[|Z_{1,2}|^{k}], \mathbb{E}[|Y_{1}|^{k}]) < \infty
$$

we can see that each of the terms in the long equation above for $\Pi$ are bounded by something of the form $r_{m_{1}},\dots,r_{m_{\ell}}$, for which $m_{1}+\dots +m_{\ell}=2k$. Precisely, we have the blunt upper bound 

$$
|\Pi(G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}},w_{\boldsymbol{i}},w_{\boldsymbol{j}})| \leq 2 \prod^{\ell}_{j=1; \sum _\boldsymbol{i} m_{\boldsymbol{i}}=2k  }r_{m_{\boldsymbol{j}}}\leq 2c_{2k}
$$

for some large but undetermined constant $c_{2k}$ as there are only finitely many non-negative integers $(m_{1},\dots,m_{\ell})$ such that $m_{1}+\dots+m_{\ell}=2k$. That being said, we can show that many of these terms in the long equation for $\Pi$ are zero, as before. 

Indeed, by construction, every edge in the union graph $G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}}$ is traversed at least once by union of these two walks. Suppose $e\in E_{\boldsymbol{i}}\cup E_{\boldsymbol{j}}$ is traversed only *once*. This means that $w_{\boldsymbol{i}, \boldsymbol{j}}(e)=1$ and so it follows that the two values $w_{\boldsymbol{i}}(e)$ and $w_{\boldsymbol{j}}(e)$ are in $\{ 0,1 \}$. Hence, the long equation for $\Pi$ and the fact that the matrix elements are centered (see [[Real Wigner matrices - traces, moments and combinatorics#^188072|Definition 17.1]]) show that $\Pi$ vanishes completely in this case. Consequently the variance sum reduces to 

$$
\begin{align}
 & \text{Var}\left( \frac{1}{N}\mathrm{Tr}(\mathcal{M}_{N}^{k}) \right) \\
 \\
 & =\sum_{(G,w,w') \in \mathcal{G}_{k,k}; w+w' \geq 2} \Pi(G,w,w') \frac{|\{ (\boldsymbol{i},\boldsymbol{j}) \in \{ 1,\dots,N \}^{2k}:()G_{\boldsymbol{i}}\cup G_{\boldsymbol{j}},w_{\boldsymbol{i}},w_{\boldsymbol{j}})=(G,w,w')\}|}{N^{k+2}}
\end{align}

$$

similarly to before. However, the enumeration of the number of $2k$-tuples yielding a certain graph with two walks is the same as in our previous workings (see [[Proof of Theorem 17.3#^695984|Lemma 17.10]]). The structure $(G,w,w')$ specifies the $2k$-tuple precisely once we select the $|G|$ distinct indicies for the vertices. So, as before, the remaining ratio in the variance sum becomes

$$
\frac{N(N-1)\dots(N-|G|+1)}{N^{k+2}}
$$

Since now we have the condition $w+w'\geq 2$, meaning every edge is traversed at least twice, and there are $k$ steps in each of the two walks, this means that there are at most $k$ edges. Consequently, by [[Proof of Theorem 17.3#^5c81fa|Proposition 17.11]] it follows that $|G|\leq k+1$ and hebnce

$$
\frac{N(N-1)\dots(N-|G|+1)}{N^{k+2}}=O_{k}(N^{|G|-k-2})=O_{k}\left( \frac{1}{N} \right)
$$

as $N \to \infty$. In summary we have proven that

$$
\text{Var}\left( \frac{1}{N}\mathrm{Tr}[\mathcal{M}_{N}^{k}] \right)=\sum_{(G,w,w')\in\mathcal{G}_{k,k}; w+w' \geq 2} \Pi(G,w,w') \frac{N(N-1)\dots(N-|G|+1)}{N^{k+2}}=O_{k}\left( \frac{1}{N} \right)
$$

which clearly tends to zero as $N \to \infty$. Hence, we have proved

$$
\lim_{ N \to \infty } \text{Var}\left( \frac{1}{N} \mathrm{Tr}(\mathcal{M}_{N}^{k}) \right) =0
$$

And so this completes our proof. Clearly, we have shown both the conditions such that 

$$
\lim_{ N \to \infty } \mathcal{P}\left( \Big| \frac{1}{N}\mathrm{Tr} (\mathcal{M}_{N}^{k})-\int_{\mathbb{R}}x^{k}\sigma_{t}(x)dx\Big| >\epsilon\right)=0
$$
