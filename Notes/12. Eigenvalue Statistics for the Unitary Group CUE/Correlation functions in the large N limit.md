---
dg-publish: true
---
#Notes 

Sometimes, we want to compare $R^{U(N)}_{2}(\theta_{1},\theta_{2})$, or more generally $R_{n}^{U(N)}$, for different values of $N$. In order to do this, we need to have a way to properly compare them, which requires us to scale each function such that the *average spacing* is equal to $1$.

We do this by changing variables to $x_{j} = \frac{N\theta_{j}}{2\pi}$, such that we then have $\theta_j=\frac{2\pi x_{j}}{N}$.

Then, we can see that 

$$
\begin{aligned}

\tilde{R}^{U(N)}_{1} (x_{1})&= \frac{2\pi}{N}R_{1}^{U(N)} \left( \frac{2\pi x}{N}  \right)

\\ 

\tilde{R}_{2}^{U(N)}(x_{1},x_{2}) &= \left( \frac{2\pi}{N} \right)^{2} R_{2}^{U(N)}\left( \frac{2\pi x_{1}}{N}, \frac{2\pi x_{2}}{N}\right)

\\

\tilde{R}_{n}^{U(N)}(x_{1},x_{2},\dots,x_{n})&= \left(\frac{2\pi}{N}\right)^nR_{n}^{U(N)}\left( \frac{2\pi x_{1}}{N},\dots,\frac{2\pi x_{n
}}{N} \right)
\end{aligned}
$$

The factor out the front of each term comes from the normalisation constraint

$$
\int^N_{0}\dots \int^{N}_{0}\tilde{R}_{n}^{U(N)}(x_{1},\dots,x_{n})dx_{1}\dots dx_{n}=\frac{N!}{(N-n)!}
$$

where we realise that

$$
	d\theta_{1}\dots d\theta _{n}= \left( \frac{2\pi}{N} \right)^ndx_{1}\dots dx_{n}
$$
(we can see where the constant is introduced into the integral as a result of changing variables, and then where it goes afterwards.)

So, we have successfully found a way to scale the eigenvalues such that the average spacing is equal to $1$. 

When we take the limit of $N\to \infty$, we can see that the limit of the normalisation constraint integral doesn't exist. However, we will soon see that the limit

$$
R_{n}(x_{1},\dots, x_{n})=\lim_{ N \to \infty }\tilde{R}_{n}^{U(N)}(x_{1},\dots ,x_{n}) 
$$

We currently have, from [[Correlation functions for the CUE ensemble]], that 

$$
R_2^{U(N)}(\theta_1, \theta_2)=\frac{N^{2}}{(2\pi)^{2}}\left[1-\left(\frac{\sin\left(\frac{N(\theta_{2}-\theta_{1})}{2}\right)}{N\sin\left(\frac{\theta_{2}-\theta_{1}}{2}\right)}\right)^{2}\right]
$$

Let's set $r=N(\theta_{2}-\theta_{1}) / 2\pi$ and then manipulate the second term in the brackets.

$$
\begin{aligned}

\frac{\sin\left( \frac{N(\theta_{2}-\theta_{1})}{2} \right)}{N\sin\left( \frac{\theta_{2}-\theta_{1}}{2} \right)} &= \frac{\sin(\pi r)}{N\sin\left( \frac{\pi r}{N} \right)}=\frac{\sin(\pi r)}{\pi r-\frac{1}{N^{2}}\frac{(\pi r)^3}{3!}+O\left( \frac{1}{N^4} \right)}

\end{aligned}
$$

where we have Taylor expanded the bottom $\sin$ function.

One thing to note about $r$ is that it doesn't go to infinity as $N$ gets big, since the eigenvalue spacing goes to zero when $N$ is large.

We can go one step further, and Taylor expand the bottom again under

$$
\frac{1}{1-x}=1+x+x^2+O(x^3)
$$

to find

$$
\frac{\sin\left( \frac{N(\theta_{2}-\theta_{1})}{2} \right)}{N\sin\left( \frac{\theta_{2}-\theta_{1}}{2} \right)}
=\frac{\sin(\pi r)}{\pi r} \left( 1+\frac{1}{N^{2}} \frac{(\pi r)^{2}}{3!}+O\left( \frac{1}{N^4} \right) \right)
$$

Where we are *neglecting* high order terms. 

Therefore, going back to our original equation above, we find

$$
\left( \frac{2\pi}{N} \right)^2R_{2}^{U(N)}\left( \frac{2\pi r}{N} \right)=1-\left( \frac{\sin(\pi r)}{\pi r} \right)^2+O\left( \frac{1}{N^2} \right)
$$


> [!help] Note
> Here we have taken the factor in front of the large brackets above to the other side, and made sure to ensure our normalisation constant is kept.


By taking the limit as $N\to \infty$, we obtain

$$
R_{2}(r) = 1-\left( \frac{\sin(\pi r)}{\pi r} \right)^2
$$

To see what the behaviour of this is like, let's expand this second term around zero.

$$
\frac{\sin(\pi r)}{\pi r}=\frac{\pi r-\frac{(\pi r)^3}{3!}+O((\pi r)^5)}{\pi r}=1-\frac{(\pi r)^2}{3!}
$$

And so it behaves quadratically for small eigenvalue differences!

$$
\text{For } r \text{ small:   } R_{2}(r) \approx \frac{\pi r^2}{3} 
$$


> [!help] Note
> To find this out, we have squared the term, however we still exclude higher order terms. (I think this is where the factorial goes).


This quadratic behaviour can be seen in the following figure.
![[Screenshot 2025-02-04 at 16.58.07.png]]
*We can see for the CUE pair correlation function, we behave as a quadratic for small $r$, and then become a sinc function centered on 1.*

This is a consequence of the square in 

$$
\prod_{1\leq j<k\leq N} \bigg|e^{i\theta_{k}}-e^{i\theta_{j}}\bigg|^2
$$

We could similarly do this for the $n$-point correlation function. The limit as $N\to \infty$ of 

$$
\left( \frac{2\pi}{N} \right)^nR_{n}^{U(N)}\left( \frac{2\pi x_{1}}{N},\dots, \frac{2\pi x_{n}}{N}\right)
$$

can be taken in the same way as for the pair correlation above. We have that

$$
S_{N}(\theta)=\frac{1}{2\pi} \frac{\sin\left( \frac{N\theta}{2} \right)}{\sin \frac{\theta}{2}}
$$

By then using the more general substitution 

$$
r_{jk}=\frac{N(\theta_{k}-\theta_{j})}{2\pi}
$$

We can say that 

$$
\begin{aligned}

(S_{N}(\theta_{k}-\theta_{j})) &= \left( S_{N}\left( \frac{2\pi r_{kj}}{N} \right) \right)

\\

& = \frac{N}{2\pi} \begin{pmatrix}
\frac{\sin(\pi r_{11})}{N\sin \frac{\pi r_{11}}{N}} & \dots & \frac{\sin(\pi r_{1n})}{N\sin \frac{\pi r_{1n}}{N}} \\
\\   \vdots &\ddots & \vdots \\
\\ \frac{\sin(\pi r_{n1})}{N\sin \frac{\pi r_{n1}}{N}} & \dots & \frac{\sin(\pi r_{nn})}{N\sin \frac{\pi r_{nn}}{N}}
\end{pmatrix}

\end{aligned}
$$


> [!help] Note
> Here notice how we have factored out the $N / 2\pi$ for all the values.


We then define 

$$
S(r)=\lim_{ N \to \infty } \frac{\sin(\pi r)}{N\sin \frac{\pi r}{N}}=\frac{\sin(\pi r)}{\pi r}
$$

and finally, we can obtain

$$
\begin{aligned}
R_{n}(x_{1},\dots,x_{n})&=\lim_{ N \to \infty } \left( \frac{2\pi}{N} \right)^{n}R_{n}^{U(N)}\left( \frac{2\pi x_{1}}{N},\dots, \frac{2\pi x_{n}}N \right)
\\
&=\lim_{ N \to \infty } \left( \frac{2\pi}{N} \right)^{n}\det_{n\times n}S_{N}\left( \frac{2\pi r_{kj}}{N} \right)
\\
&= \det_{n\times n}(S(r_{kj}))
\end{aligned}

$$


> [!help] Note
> In the second line, we used point 2 from [[Where we are headed]] (not proven just yet).


