---
dg-publish: true
---
#Notes 

Now, we will continue from [[Hermitian Matrices]] and look at the $2\times2$ case. This generalizes well into higher dimensions. 

Let’s start by considering the question - *why are normal random variables the best choice for the distribution to describe the matrix elements*?

So we are considering $2\times 2$ symmetric matrices as

$$
H=\begin{pmatrix}h_{11}&h_{12}\\h_{21}&h_{22}\end{pmatrix}
$$

where since $H$ is symmetric, $h_{21}=h_{12}$. Every matrix in this set can be *diagonalized* by an **orthogonal matrix**

$$
O^tHO=\begin{pmatrix}\lambda_1&0\\0&\lambda_2\end{pmatrix}
$$

which is like changing the basis such that the off-diagonal elements are zero. Our orthogonal matrix will satisfy $O^tO=I$, since in 2D it acts as a rotation, and rotating by $\theta$ and then by $-\theta$ does nothing overall. 

The most general orthogonal matrix in $O(2)$ (the set of all $2\times 2$ orthogonal matrices) is

$$
\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos \theta \end{pmatrix}
$$

(recall this just describes a rotation by an angle $\theta$). 

The joint probability density function for the matrix elements is a real, non-negative function $P_1(H)=P_1(h_{11},h_{22},h_{12})$ such that

$$
\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}P_{1}(h_{11},h_{22},h_{12})dh_{11}dh_{22}dh_{12}=1
$$

i.e. it is normalized. Note that we don’t include $h_{21}$ since it is *not independent* from $h_{12}$ (see [[Hermitian Matrices]]).

We want to find the *most general $P_1(H)$* such that we satisfy two conditions:


> [!check] Condition 1
> If $H'=O^tHO$ for any $O\in O(2)$, we find
>$$P_1(h_{11}^{\prime},h_{22}^{\prime},h_{12}^{\prime})dh_{11}^{\prime}dh_{22}^{\prime}dh_{12}^{\prime}=P_1(h_{11},h_{22},h_{12})dh_{11}dh_{22}dh_{12}$$
>i.e. if we change the basis, the outcome probabilities don’t change. This is pretty fundamental - if we change the way we look at a system, we expect it to behave the same way as it did before (the outcome probability remains constant regardless of how you view it). 


> [!check] Condition 2
> The independent elements of $H$ are uncorrelated i.e.
> $$P_1(h_{11},h_{22},h_{12})=p_{11}(h_{11})p_{22}(h_{22})p_{12}(h_{12})$$
> which we recall is the product of one-dimensional probability density functions, as we would expect for independent variables. 
    

Let’s go back to our orthogonal matrix, and call it $\delta E$.

$$
\delta E=\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos \theta \end{pmatrix}
$$

Now let’s assume $\theta$ is small, to make the maths easier for now. 

$$
\delta E \approx \begin{pmatrix} 1 & -\theta \\ \theta & 1 \end{pmatrix}
$$

We only consider terms here that go slower than $\theta\to0$ i.e. first order $\theta$ only. 

Let’s now make a change of variables to $H$, such that $H'=\delta E^tH\delta E$. Then,

$$
H'=\begin{pmatrix} 1 & \theta \\ -\theta & 1 \end{pmatrix}   \begin{pmatrix}h_{11}&h_{12}\\h_{12}&h_{22}\end{pmatrix}\begin{pmatrix} 1 & -\theta \\ \theta & 1 \end{pmatrix}=\begin{pmatrix} 1 & \theta \\ -\theta & 1 \end{pmatrix} \begin{pmatrix} h_{11}+\theta h_{12} & -\theta h_{11}+h_{12} \\ h_{12}+\theta h_{22} & -\theta h_{12} + h_{22}\end{pmatrix} = \begin{pmatrix} h_{11}+2\theta h_{12} & h_{12}+\theta(h_{22}-h_{11}) \\ h_{12}+\theta(h_{22}-h_{11}) & h_{22}-2\theta h_{12}\end{pmatrix}\quad
$$


> [!help] Note
> We remove all the high-order $\theta^{2}$ terms in the final part of this equation.


We can note immediately that $h'_{12}=h'_{21}$ as we would expect. We then get three independent equations from this.

$$
\begin{aligned} h'_{11}&= h_{11}+2\theta h_{12} \\ h'_{22} &= h_{22}-2\theta h_{12} \\ h'_{12}&=h_{12}+\theta(h_{22}-h_{11})\end{aligned}
$$

The volume element transforms according to the *Jacobian* as 

$$
dh_{11}^{\prime}dh_{22}^{\prime}dh_{12}^{\prime}=\left|\frac{\partial(h_{11}^{\prime},h_{22}^{\prime},h_{12}^{\prime})}{\partial(h_{11},h_{22},h_{12})}\right|dh_{11}dh_{22}dh_{12}
$$

where 

$$
\left|\frac{\partial(h_{11}^{\prime},h_{22}^{\prime},h_{12}^{\prime})}{\partial(h_{11},h_{22},h_{12})}\right|=\begin{vmatrix}1&0&2\theta\\0&1&-2\theta\\-\theta&\theta&1\end{vmatrix}=1+\mathrm{o}(\theta)
$$

We have here a Jacobian equal to one on first order. Therefore, up to but not including $\theta^2$ terms

$$
dh_{11}^{\prime}dh_{22}^{\prime}dh_{12}^{\prime}=dh_{11}dh_{22}dh_{12}
$$

Even if we *had not made the small angle approximation*, this is still true (the maths is just harder). 

We then need to find functions that satisfy $P_1(H)=P_1(H')$, such that

$$
P_1(H)=P_1(H^{\prime})=p_{11}(h_{11})p_{22}(h_{22})p_{12}(h_{12})=p_{11}(h_{11}^{\prime})p_{22}(h_{22}^{\prime})p_{12}(h_{12}^{\prime})
$$

to satisfy condition 1. 

Let’s initially take 

$$
P_1(H')=p_{11}(h_{11}^{\prime})p_{22}(h_{22}^{\prime})p_{12}(h_{12}^{\prime})
$$

We have the conditions

$$
h'_{11}= h_{11}+2\theta h_{12}, \quad h'_{22} = h_{22}-2\theta h_{12} ,\quad h'_{12}=h_{12}+\theta(h_{22}-h_{11})
$$


> [!info] Context
> Suppose we have a function $f(x)$. If $x'=x+\Delta$, where $\Delta$  is some *small* increment, then to first order in $\Delta$
> $$f(x+\Delta)\approx f(x)+\Delta f'(x)$$  
> In this case, we can then write
> $$p(h'_{ij})\approx p_{ij}(h_{ij})+(h'_{ij}-h_{ij})\frac{d}{d h_{ij}}p_{ij}(h_{ij})$$
> where we have defined $\Delta =h'_{ij}-h_{ij}$. 
> However, we might instead chose to write this in *log-derivative form*. 
> $$\frac{d}{dh_{ij}}p_{ij}(h_{ij})\approx p_{ij}(h_{ij})\frac{d}{dh_{ij}}\bigg[\log p_{ij}(h_{ij})\bigg]$$
> Recall if $f(x)=\log g(x)$, then $f'(x)=\frac{1}{g(x)}g'(x)$. Then, the above clearly reduces to
> $$\frac{d}{dh_{ij}}p_{ij}(h_{ij})=\frac{d}{dh_{ij}}p_{ij}(h_{ij})$$
> Hence we find 
> $$p(h'_{ij}) \approx p_{ij}(h_{ij})+(h'_{ij}-h_{ij})p_{ij}(h_{ij})\frac{d}{dh_{ij}}\bigg[\log p_{ij}(h_{ij})\bigg]=p_{ij}(h_{ij}) \bigg ( 1+(h'_{ij}-h_{ij})\frac{d}{dh_{ij}}\bigg[\log p_{ij}(h_{ij})\bigg]\bigg )$$
> Let’s also let $h'_{ij}-h_{ij}=\Delta_{ij}$
> $$p(h'_{ij})=p_{ij} (h_{ij})\bigg ( 1+\Delta_{ij}\frac{d}{dh_{ij}}\bigg[\log p_{ij}(h_{ij})\bigg]\bigg )$$

To find the values of $\Delta_{ij}$, we can use the equations from before, and simply rearrange them to find

$$
\Delta _{11}=2h_{12}\theta,\quad \Delta _{22}= -2h_{12}\theta,\quad \Delta _{12}=\theta(h_{22}-h_{11})
$$

We can then write 

$$
\begin{aligned}
P_1(H')&= p_{11}(h_{11}^{\prime})p_{22}(h_{22}^{\prime})p_{12}(h_{12}^{\prime})

\\ 

\\&= \Bigg(p_{11} (h_{11})\bigg ( 1+2h_{12}\theta\frac{d}{dh_{11}}\bigg[\log p_{11}(h_{11})\bigg]\bigg ) \Bigg )
\Bigg(p_{22} (h_{22})\bigg ( 1-2h_{12}\theta\frac{d}{dh_{22}}\bigg[\log p_{22}(h_{22})\bigg]\bigg ) \Bigg )
\Bigg(p_{12} (h_{12})\bigg ( 1+(h_{22}-h_{11})\theta\frac{d}{dh_{12}}\bigg[\log p_{12}(h_{12})\bigg]\bigg ) \Bigg )

\\ 

&= p_{11}(h_{11})p_{22}(h_{22})p_{12}(h_{12}) 
\Bigg ( 1+\theta \bigg ( 2h_{12}\frac{d}{dh_{11}}\bigg[\log p_{11}(h_{11})\bigg] -2h_{12}\frac{d}{dh_{22}}\bigg[\log p_{22}(h_{22})\bigg] 
(h_{22}-h_{11})\frac{d}{dh_{12}}\bigg[\log p_{12}(h_{12})\bigg] \Bigg )

\\ 
&=P_1(H)\Bigg ( 1+\theta \underline{\bigg ( 2h_{12}\frac{d}{dh_{11}}\bigg[\log p_{11}(h_{11})\bigg]
-2h_{12}\frac{d}{dh_{22}}\bigg[\log p_{22}(h_{22})\bigg] 
 + (h_{22}-h_{11})\frac{d}{dh_{12}}\bigg[\log p_{12}(h_{12})\bigg] }\Bigg )
\end{aligned}
$$

Remember, we required $P_1(H')=P_1(H)$. Since $\theta$ can be anything, we require the underlined term to be zero. Let’s divide through this term by $h_{12}(h_{11}-h_{22})$ to obtain 

$$
\frac{1}{h_{12}}\frac{d \log p_{12}}{dh_{12}}-\frac{2}{h_{11}-h_{22}} \bigg (\frac{d\log p_{11}}{dh_{11}}-\frac{d\log p_{22}}{dh_{22}}\bigg ) =0
$$

where $p_{ij}$ is shorthand for $p_{ij}(h_{ij})$. Therefore, we have

$$
\frac{1}{h_{12}}\frac{d \log p_{12}}{dh_{12}}=\frac{2}{h_{11}-h_{22}} \bigg (\frac{d\log p_{11}}{dh_{11}}-\frac{d\log p_{22}}{dh_{22}}\bigg )
$$

such that

$$
\frac{1}{h_{12}}\frac{d \log p_{12}}{dh_{12}} =-4A, \qquad \frac{1}{h_{11}-h_{22}} \bigg (\frac{d\log p_{11}}{dh_{11}}-\frac{d\log p_{22}}{dh_{22}}\bigg )=-2A\quad
\\\scriptsize
$$


> [!help] Convention
> *The choice of coefficients here are such that $A$ comes out positive in the end. It is purely convention.


Integrating the first equation, we find

$$
\begin{aligned}
\int\frac{1}{h_{12}}d\log p_{12}&=-4A\int dh_{12}

\\

\Rightarrow \quad \int d\log p_{12} &= -4A\int h_{12} dh_{12}

\\

\Rightarrow \quad \quad \;\;\; \log p_{12}&=-2A h_{12}^2 +c

\\ 

\Rightarrow \quad \quad \,p_{12}(h_{12}) &= C\exp\Big (-2A h_{12}^2\Big)

\end{aligned}
$$

Since $\int^\infty_{-\infty}p_{12}(h_{12})dh_{12}=c$, $A$ must be positive. 

Similarly, the second equation becomes 

$$
\frac{d\log p_{11}}{dh_{11}}+2Ah_{11}-\frac{d\log p_{22}}{dh_{22}}-2Ah_{22}=0
$$

which gives

$$
\frac{d\log p_{11}}{dh_{11}}+2Ah_{11}=B\\\frac{d\log p_{22}}{dh_{22}}+2Ah_{22}=B
$$

By integrating, we can obtain 

$$
p_{11}(h_{11})=C_{1}\exp\left(-Ah_{11}^{2}+Bh_{11}\right)\quad \mathrm{and}\quad p_{22}(h_{22})=C_{2}\exp\left(-Ah_{22}^{2}+Bh_{22}\right)
$$

And hence, multiplying all these together we obtain 

$$
\begin{aligned}P_{1}(H)&=p_{11}(h_{11})p_{22}(h_{22})p_{12}(h_{12})\\&=D\exp\left(-A(h_{11}^{2}+h_{22}^{2}+2h_{12}^{2})+B(h_{11}+h_{22})\right)\end{aligned}
$$

There is a convention that $A=1/2$ and $B=0$. The joint probability distribution for the GOE is therefore

$$
P_1(H)=\frac{1}{2\pi^{3/2}}\exp\left(-\frac{1}{2}\operatorname{Tr}H^2\right)
$$

where $\text{Tr} \, H^2=h_{11}^{2}+h_{22}^{2}+2h_{12}^{2}$. 

$D=1/2\pi^{3/2}$ is found via normalisation $\int_{\mathbb{R}^3}P_1(H)d\mu(H) =1$, where $d\mu(H)=dh_{11}dh_{22}dh_{12}$. 

So, we have found the j.p.d.f. only by requiring invariance under conjugation by orthogonal matrices and independent elements being uncorrelated (our two conditions from before). 

It is clear then, that our j.p.d.f. is a *product of Gaussians*! This helps us to understand why we use normal distributions for the matrix elements, since they appear to fundamentally build the most general j.p.d.f..

$$
p_{11}(h_{11})=\frac{1}{\sqrt{2\pi}}e^{-h_{11}^{2}/2},\quad p_{22}(h_{22})=\frac{1}{\sqrt{2\pi}}e^{-h_{22}^{2}/2},\quad p_{12}(h_{12})=\frac{1}{\sqrt{\pi}}e^{-h_{12}^{2}}
$$

Remember that the p.d.f. of a Gaussian random variable with mean $\mu$ and variance $\sigma ^2$ is 

$$
p(x)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp(-(x-\mu)^2/(2\sigma^2))
$$
