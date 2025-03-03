#Notes 

We will often encounter integrals of the form 

$$
\frac{1}{n!} \int_{J^{n}} \prod_{k=1}^{n}f(x_{k}) \det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))dx_{1}\dots dx_{N}
$$

These are difficult to solve in general. But, we can use a couple of tricks - [[Andreief's Identity]].

$$
\frac{1}{n!} \int _{J^{n}} \det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))dx_{1}\dots dx_{n} =\det_{n\times n}\left( \int_{J}\psi_{j}(x)\phi_{k}(x)dx \right)
$$

as well as 

$$
\prod_{k=1}^{n}f(x_{k}) \det_{n\times n} (\psi_{j}(x_{k}))=\det_{n\times n}(f(x_{k})\psi_{j}(x_{k}))
$$

To see this second trick, consider a simple $2\times 2$ matrix with the form $(f(x_{k})\psi_{j}(x_{k}))$.

$$
\begin{pmatrix}
f(x_{0})\psi_{0}(x_{0})&f(x_{1})\psi_{0}(x_{1}) \\
f(x_{0}) \psi_{1} (x_{0}) & f(x_{1}) \psi_{1} (x_{1})
\end{pmatrix}
$$

Then 

$$

\begin{align}
\det_{2\times 2} \begin{pmatrix}
f(x_{1})\psi_{1}(x_{1})&f(x_{2})\psi_{1}(x_{2}) \\
f(x_{1}) \psi_{2} (x_{1}) & f(x_{2}) \psi_{2} (x_{2})
\end{pmatrix}&= \big(f(x_{1})\psi_{1}(x_{1})f(x_{2}) \psi_{2} (x_{2})\big)-\big(f(x_{2})\psi_{1}(x_{2})f(x_{1}) \psi_{2} (x_{1})\big) \\
&= f(x_{1})f(x_{2}) \det_{2\times 2}(\psi_{j} (x_{k}))  \\
&= \prod_{k=1}^{n}f(x_{k})\det_{2\times 2}(\psi_{j} (x_{k})) 
\end{align}

$$

which of course generalises to $n\times n$ matrices.

Hence, the integral above becomes 

$$
\begin{align}
\frac{1}{n!} \int_{J^{n}} \prod_{k=1}^{n}f(x_{k}) \det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))dx_{1}\dots dx_{N} &= \frac{1}{n!}\int_{J^{n}}\det_{n\times n}(f(x_{k})\psi_{j}(x_{k}))\det _{n\times n}(\phi_{j}(x_{k}))dx_{1}\dots dx_{N} \\
&= \det_{n\times n} \left( \int_{J} f(x) \psi_{j}(x) \phi_{k} (x)dx\right)
\end{align}

$$

which is obviously much easier to solve. To do this, we can create what is known as a **Toeplitz matrix**, which is essentially a matrix of all the integrals for each $(j,k)$.

$$
A_{n}=\begin{pmatrix} 
 \int_{J} f(x) \psi_{1}(x) \phi_{1} (x)dx &  \dots & \int_{J} f(x) \psi_{j_{1}}(x) \phi_{n} (x)dx \\
  \vdots &\ddots & \vdots   \\
 \int_{J} f(x) \psi_{n}(x) \phi_{1} (x)dx & \dots &  \int_{J} f(x) \psi_{n}(x) \phi_{n} (x)dx
\end{pmatrix} 

$$

Often it is the case that the Toeplitz matrix will simplify to a *tridiagonal matrix*

$$
A_{n}=\begin{pmatrix}
a & b & 0 & 0&\dots & 0 \\
b & a & b & 0 & \dots & 0  \\
0 & b & a & b  & \dots & 0 \\
&&  & \ddots   &  & a \\
0 &  \dots&0 & 0 & b & a
\end{pmatrix}
$$

If we define $\det A_{n}=x_{n}$, then these matrices obey the recurrence relation

$$
x_{n}=ax_{n-1}-b^2x_{n-2}
$$

with $x_{1}=a$ and $x_{2}=a^2-b^2$.

Let's go back to average functions. Let's imagine $f(\theta_{1},\dots,\theta_{N})=\prod^{N}_{j=1} f(\theta_{j})$ (a common form for these problems). To average this function over $U(N)$, we must compute 

$$
\begin{align}
 \langle f\rangle &= \frac{1}{(2\pi)^{N}N!} \int_{[0,2\pi)^{N}} \left( \prod^{N}_{j=1} f(\theta_{j}) \right) \prod_{0\leq j<k\leq N} \bigg| e^{i\theta_{k}} - e^{i\theta_{j}} \bigg|^{2}d\theta_{1}\dots d\theta_{N}\\
&= \frac{1}{(2\pi)^{N}N!} \int_{[0,2\pi)^{N}} \prod_{j=1} ^{N} f(\theta_{j}) \det_{N\times N}(e^{i(j-1)\theta_{k}}) \det_{N\times N}( e^{-i(j-1)\theta_{k}}) d\theta_{1}\dots d\theta_{N} \\
&= \det_{N\times N} \left(  \frac{1}{2\pi} \int_{0}^{2\pi} f(\theta) e^{i(j-k)\theta}d\theta \right)
\end{align}
	$$

> [!help] Note
> The second line involves expanding out the second product, which we did in [[Haar measure as a determinant]]. We have made $\psi_{j}(\theta_{k})=e^{i(j-1)\theta_{k}}$ and $\phi_{j}(\theta_{k})=e^{-i(j-1)\theta_{k}}$ as before. 

This is sometimes called **Heine's identity**.


> [!Example] See [[Example - Average over U(N)]].




