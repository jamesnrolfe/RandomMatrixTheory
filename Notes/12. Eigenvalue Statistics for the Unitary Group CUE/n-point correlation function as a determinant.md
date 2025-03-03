---
noteID: 7decc63b-3493-40d6-b0b1-2f632d348db4
---
#Notes 

[[Gaudin's Lemma]] states that if we have a function of two variables $f(x,y)$ which is integrable on an interval $J$ and such that 

$$
\int_{J}f(x,y)f(y,z)dy=Kf(x,z)
$$

for all $x$ and $z$ and where $K=K(f,J)$ is a constant, and that 

$$
\int_{J}f(y,y)dy=D
$$

where $D=D(f,J)$ is also a constant, then

$$
\int_{J}\det_{n\times n}(f(x_{j},x_{k}))dx_{n}=(D-(n-1)K)\det_{(n-1)\times(n-1)}(f(x_{j},x_{k}))
$$

Why is this useful? Well, integrals are hard to solve. Determinants, not so. And so we can convert an integral of a determinant into something that is just a determinant - this is great! Not only this, but the determinant actually gets smaller each time we do this, and so this makes it even easier to solve. 

Gaudin's lemma is the main ingredient to prove 

$$
R_{n}^{U(N)}(\theta_{1},\dots,\theta_{n}) = \det_{n\times n}(S_{N}(\theta_{k}-\theta_{j}))
$$

(step 2 in [[Where we are headed]]).

We ultimately want to show that we can use Gaudin's lemma, and so our function $S_{N}(\theta_{k}-\theta_{j})$ must satisfy

$$

\int^{2\pi}_{0}S_{N}(\theta_{k}-\theta)S_{N}(\theta-\theta_{j}) d\theta =KS_{N}(\theta_{k}-\theta_{j})

$$

and 

$$
\int_{0}^{2\pi}S_{N}(\theta-\theta)d\theta=D
$$

The second condition is easy. We know $S_{N}(\theta-\theta)=S_{N}(0)$ and from [[Correlation functions for the CUE ensemble]] we know that $S_{N}(0)=\frac{N}{2\pi}$. Hence

$$
\int_{0}^{2\pi}S_{N}(\theta-\theta)d\theta= \int^{2\pi}_{0}  \frac{N}{2\pi}d\theta=N \quad \Rightarrow     \quad D=N
$$

The first condition is a bit more complicated. We must use 

$$
\begin{align}
S_{N}(\theta)=\frac{1}{2\pi} \frac{{\sin \frac{N\theta}{2}}}{\sin \frac{\theta}{2}}&=\frac{1}{2\pi} \frac{e^{-iN\theta /2}-e^{iN\theta /2}}{e^{-i\theta /2}-e^{i\theta /2}} \\
&=\frac{1}{2\pi} \frac{e^{iN \theta / 2}(1-e^{iN\theta})}{e^{i\theta /2}(1-e^{i\theta})} \\
&=\frac{e^{i(N-1)\theta /2}}{2\pi} \sum_{l=0}^{N-1}e^{il\theta} \\
\therefore \quad S_{N}(\theta_{k}-\theta_{j})&=\frac{e^{i(N-1)(\theta_{k}-\theta_{j}) /2}}{2\pi} \sum_{l=0}^{N-1}e^{il(\theta_{k}-\theta_{j})}
\end{align}
$$

> [!help] Note
> This is similar to what we saw in [[Haar measure as a determinant]], where we work with geometric sums. If this seems arbitrary, then it is more informative to see what we did there, since it goes the other way.


Then we can prove that 

$$
\begin{align}
\int_{0}^{2\pi} S_{N}(\theta_{k}-\theta)S_{N}(\theta-\theta_{j})d\theta
&=\int^{2\pi}_{0}\frac{{e^{i(N-1)(\theta-\theta_{k})/2}}}{2\pi}\sum^{N-1}_{l=0}e^{il(\theta_{k}-\theta)}\times\frac{{e^{i(N-1)(\theta_{j}-\theta)/2}}}{2\pi}\sum^{N-1}_{m=0}e^{im(\theta-\theta_{j})}d\theta 
 \\
&= e^{i(N-1)(\theta_{j}-\theta_{k}) /{2}} \times \sum^{N-1}_{l,m=0}e^{i(l\theta_{k}-m\theta_{j})} \times\int^{2\pi}_{0}e^{i(m-l)\theta}d\theta=S_{N}(\theta_{k}-\theta_{j})\\  
 
&\therefore \quad K=1
\end{align}
$$

> [!help] Note
> This is complicated. Take time to look through it to see how all the indicies move about. It does work, I promise.


So, $S_{N}(\theta_{k}-\theta_{j})$ satisfies the conditions for Gaudin's lemma. Hence we can use it. It is written again here for convenience. 

$$
\int_{J}\det_{n\times n}(f(x_{j},x_{k}))dx_{n}=(D-(n-1)K)\det_{(n-1)\times(n-1)}(f(x_{j},x_{k}))
$$

We want to apply Gaudin's lemma to the normalised Haar measure from [[Haar measure as a determinant]]

$$
P_{N2}(\theta_{1},\ldots,\theta_{N})=C(2\pi)^{N}\det_{N\times N}\left(S_{N}(\theta_{k}-\theta_{j})\right)
$$

where $C$ is some normalisation constant. Remember from [[Spectral Correlation Functions]] that 

$$
R_n(\theta_1,\dots,\theta_n)=\frac{N!}{(N-n)!}\int^{2\pi}_{0}\int^{2\pi}_{0}\dots \int^{2\pi}_{0}P_{N2}(\theta_1,\dots,\theta_N)d\theta_{n+1}\dots d\theta_N
$$

which is what we are trying to find, just this time in terms of determinants. 

Consider first the integral over just $\theta_{N}$. Let's set $Q=N! / (N-n)!$ for now for simplicity.

$$
R_{N-1}(\theta_{1},\dots,\theta_{N})=Q\int^{2\pi}_{0}P_{N 2}(\theta_{1},\dots,\theta_{N})d\theta _{N}
$$

We can take this further by applying Gaudin's lemma and our definition of $P_{N 2}$ above, where we set $f(\theta_j,\theta_{k})=S_{N}(\theta_{k}-\theta_{j})$, with out values of $K=1$ and $D=N$. Hence

$$
\begin{align}
R_{N-1}(\theta_{1},\dots ,\theta_{N}) &=Q\int^{2\pi}_{0}P_{N 2}(\theta_{1},\dots,\theta_{N})d\theta _{N} 
 \\
&=Q C(2\pi)^{N}\int_{0}^{2\pi} \det_{N\times N}(S_{N}(\theta_{k}-\theta_{j}))d\theta_{N} \\
&=Q C(2\pi)^N(N-(N-1))\det_{(N-1)\times(N-1)}(S_{N}(\theta_{k}-\theta_{j})) \\
&=QC(2\pi)^N\det_{(N-1)\times(N-1)}(S_{N}(\theta_{k}-\theta_{j}))
\end{align}

$$

This is good. However, we ideally want the $n$-point correlation function, not just the $N-1$-point correlation function. And so, we can apply this again!

$$
\begin{align}
R_{N-2}(\theta_{1},\dots,\theta_{N})&=Q\int^{2\pi}_{0} \int^{2\pi}_{0} P_{N 2}(\theta_{1},\dots,\theta_{N})d\theta_{N-1}d\theta \\
&=QC(2\pi)^N \int^{2\pi}_{0}\det_{(N-1)\times(N-1)}(S_{N}(\theta_k-\theta_{j}))d\theta_{N-1} \\
&=QC(2\pi)^N(N-(N-2))\det_{(N-2)\times(N-2)}(S_{N}(\theta_{k}-\theta_{j})) \\
&=QC(2\pi)^{N} \times 1 \times 2 \times \det_{(N-2)\times(N-2)}(S_{N}(\theta_{k}-\theta_{j}))
\end{align}
$$

By iteration, it is fairly clear that we have

$$
\int^{2\pi}_{0}\dots \int^{2\pi}_{0} P_{{N 2}}(\theta_{1},\dots,\theta_{N})d\theta_{n+1}\dots d\theta_{N}=C(2\pi)^{N}(N-n)! \det_{n\times n}(S_{N}(\theta_{k}-\theta_{j}))
$$

Remember that the probability distribution has to have an integral of $1$ to be normalised when integrating over all $n$, and so

$$
\int^{2\pi}_{0} \dots \int^{2\pi}_{0} P_{N 2}(\theta_{1},\dots,\theta_{N})d\theta_{1}\dots d\theta_{N}=1
$$

But we have the general formula for the left hand side in terms of the determinant. By setting $n=0$, we can compute the normalisation constant $C$. 

$$
C(2\pi)^{N} (N!) =1 \quad \Rightarrow \quad C=\frac{1}{(2\pi)^{N}N!}
$$

> [!help] Note
> We note $\det_{0\times0}(S_{N}(\theta_{k}-\theta_{j}))=1$ (see [this post](https://math.stackexchange.com/questions/1762537/why-is-the-determinant-of-the-0x0-matrix-equal-1) for guidance - essentially a $0\times 0$ matrix has to be invertible, with the inverse equalling the matrix, and so its determinant should be one to satisfy this).


Plugging this back in, we find 

$$
\begin{align}
R_{n}^{U(N)} (\theta_{1},\dots,\theta_{N})&=\overbrace{ \frac{N!}{(N-n)!} }^{ Q }\frac{{(2\pi)^N(N-n)!}}{(2\pi)^{N}N!}\det_{n\times n}(S_{N}(\theta_{k}-\theta_{j})) \\ \\

&=\det_{n\times n}(S_{N}(\theta_{k}-\theta_{j}))
\end{align}


$$

as we wanted to prove. 