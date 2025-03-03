---
dg-publish: true
---
#Notes 

We will now introduce a theorem.

Let $p_{j}(\lambda)$ be a set of orthogonal monic polynomials with weight $w(\lambda)$. Then we have

$$
\prod^{N}_{l=1} w(\lambda_{l})\prod_{1\leq j<k\leq N} |\lambda_{k}-\lambda_{j}|^2=\left( \prod^{N-1}_{l=0} (p_{l}, p_{l}) \right)\det_{N\times N}(K_{N}(\lambda_{j},\lambda_{k}))
$$

where 

$$
K_{N}(\lambda,\mu)= (w(\lambda)w(\mu))^{\frac{1 }{ 2}} \sum^{N-1}_{j=0} \frac{p_{j}(\lambda) p_{j}(\mu)}{(p_{j},p_{j})}
$$

This looks like a nightmare, so let's prove it. 

Recall from [[Introducing orthogonal polynomials]] that

$$
\det_{n\times n}(p_{j-1}(\lambda_{k})) = \det_{n\times n} (\lambda_{k}^{j-1})=\prod _{1\leq j<k\leq n} (\lambda_{k}-\lambda_{j})
$$

First notice that 

$$
\det_{n\times n}(p_{j-1}(\lambda_{k}))\det_{n\times n}(p_{j-1}(\lambda_{k}))=\prod _{1\leq j<k\leq n} (\lambda_{k}-\lambda_{j})\prod _{1\leq j<k\leq n} (\lambda_{k}-\lambda_{j})=\prod _{1\leq j<k\leq n} |\lambda_{k}-\lambda_{j}|^2

$$

> [!help] Note
> We have essentially squared both sides of the above (in this case, the product squared is just the product of the inside squared).

Hence from our theorem, we find

$$
\prod^{N}_{l=1} w(\lambda_{l})\prod_{1\leq j<k\leq N} |\lambda_{k}-\lambda_{j}|^{2}=\prod^{N}_{l=1} w(\lambda_{l}) \bigg( \det_{N\times N} (p_{j-1}(\lambda_{k}))\det_{N\times N} (p_{j-1}(\lambda_{k}))\bigg)
$$

Recall that 

$$
(p_{j}, p_{j})=\int _{J} w(\lambda)p_{j}(\lambda)p_{j}(\lambda)d\lambda
$$

and now consider that the product on the RHS is of the form 

$$
\prod^{N}_{l=1} \sqrt{ w(\lambda_{l}) } \det_{N\times N} (p_{j-1}(\lambda_{k}))\times \sqrt{ w(\lambda_{l}) }\det_{N\times N} (p_{j-1}(\lambda_{k}))
$$

For each determinant, we can bring the factor of $\sqrt{ w(\lambda_{l}) }$ inside by multiplying each column by that determinant (then when evaluating that determinant, the factor as a result of this is simply the one we have). The reason we do this is because $w(\lambda_{l})$ depends on the index of $\lambda$, which changes by column.

So we can say that the above is equal to

$$
\prod^{N}_{l=1}  \det_{N\times N} (\sqrt{ w(\lambda_{k}) }p_{j-1}(\lambda_{k}))\times \det_{N\times N} (\sqrt{ w(\lambda_{k}) }p_{j-1}(\lambda_{k}))
$$

We the multiply by a factor of $(p_{l},p_{l}) / \sqrt{ (p_{l},p_{l})(p_{l},p_{l}) }$ (which is just 1), which we can write as 

$$
\prod^{N-1}_{l=0}  (p_{l},p_{l}) \frac{1}{\sqrt{ (p_{l},p_{l}) }}\det_{N\times N} (\sqrt{ w(\lambda_{k}) }p_{j-1}(\lambda_{k}))\times \frac{1}{\sqrt{ p_{l},p_{l} }}\det_{N\times N} (\sqrt{ w(\lambda_{k}) }p_{j-1}(\lambda_{k}))
$$

> [!help] Note
> We have changed the product boundaries here as well, to reflect that we are starting from the the 0th row.

We can take the factors of $\frac{1}{\sqrt{ (p_{l},p_{l}) }}$ inside in a similar way.

$$
\prod^{N-1}_{l=0}  (p_{l},p_{l}) \det_{N\times N} \left( \sqrt{ \frac{w(\lambda_{k})}{(p_{j-1},p_{j-1})}}p_{j-1}(\lambda_{k}) \right)\times \det_{N\times N} \left(\sqrt{ \frac{w(\lambda_{k})}{(p_{j-1},p_{j-1})}}p_{j-1}(\lambda_{k})\right)
$$

where now we apply to the rows inside the determinant, because that labels *which polynomial it is*. $p_{l}$ depends on the *row index* in this way, so it must be inserted like this.

So, our theorem becomes 

$$
\prod^{N}_{l=1} w(\lambda_{l})\prod_{1\leq j<k\leq N} |\lambda_{k}-\lambda_{j}|^{2}=\prod^{N-1}_{l=0}  (p_{l},p_{l}) \det_{N\times N} \left( \sqrt{ \frac{w(\lambda_{k})}{(p_{j-1},p_{j-1})}}p_{j-1}(\lambda_{k}) \right)\times \det_{N\times N} \left(\sqrt{ \frac{w(\lambda_{k})}{(p_{j-1},p_{j-1})}}p_{j-1}(\lambda_{k})\right)
$$

We can then apply [[The Transposing Lemma]] 

$$
\det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))=\det_{n\times n} \left( \sum^n_{l=1}\psi_{l}(x_{j})\phi_{l}(x_{k}) \right)
$$

to the RHS, to find

$$
\begin{align} \\

\prod^{N}_{l=1} w(\lambda_{l})\prod_{1\leq j<k\leq N} |\lambda_{k}-\lambda_{j}|^{2}&=\prod^{N-1}_{l=0}  (p_{l},p_{l}) \det_{N\times N} \left( \sqrt{ \frac{w(\lambda_{k})}{(p_{j-1},p_{j-1})}}p_{j-1}(\lambda_{k}) \right)\times \det_{N\times N} \left(\sqrt{ \frac{w(\lambda_{k})}{(p_{j-1},p_{j-1})}}p_{j-1}(\lambda_{k})\right) \\ \\

&= \prod^{N-1}_{l=0} (p_{l},p_{l}) \det_{N\times N} \left(  \sum_{l=0}^{N-1}  \sqrt{ \frac{w(\lambda_{j})}{(p_{l},p_{l})} }p_{l}(\lambda_{j})  \times \sqrt{ \frac{w(\lambda_{k})}{(p_{l},p_{l})} }p_{l}(\lambda_{k})\right) \\ \\

&=\prod^{N-1}_{l=0} (p_{l},p_{l}) \det_{N\times N} \left(\sqrt{ w(\lambda_{j})w(\lambda_{k} )} \sum ^{N-1}_{l=0} \frac{p_{l}(\lambda_{j})p_{l}(\lambda_{k})}{(p_{l},p_{l})}\right) \\ \\

&= \prod^{N-1}_{l=0} (p_{l},p_{l})\det_{N\times N} (K_{N}(\lambda_{j}, \lambda_{k}))

\end{align} \\
$$

> [!help] Note
> Note that the boundary changes on the sum and the product all come from the fact that we use $j-1$ i.e. in our matrices, we are starting from zero and not one (as we usually would - hence the Transposing Lemma needs to be adjusted etc.).


where 

$$
K_{N}(\lambda,\mu)= (w(\lambda)w(\mu))^{\frac{1 }{ 2}} \sum^{N-1}_{j=0} \frac{p_{j}(\lambda) p_{j}(\mu)}{(p_{j},p_{j})}

$$
