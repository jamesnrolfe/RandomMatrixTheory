---
dg-publish: true
---
#Notes 

From [[Where we are headed]], we gave the equation 

$$
R_n^{\mathrm{U}(N)}(\theta_1,\ldots,\theta_n)=\det_{n\times n}\left(S_N(\theta_k-\theta_j)\right)
$$

which we will accept for now. We will prove this later on. 

Recall as well that 

$$
S_N(\theta)=\frac{1}{2\pi}\frac{\sin\left(\frac{N\theta}{2}\right)}{\sin\frac{\theta}{2}}
$$

For a $1\times 1$ matrix, $(S_N(\theta_k-\theta_j))$ is simply

$$
S_N(\theta_1-\theta_1)=S_N(0)=\lim_{\theta\to0} \frac{1}{2\pi}\frac{\sin\Big(\frac{N\theta}{2}\Big )}{\sin \Big (\frac \theta 2 \Big)}=\frac{N}{2\pi}
$$

To see this, remember that as we under small $\theta$, we can use the small angle approximation, to say that $\sin(x) = x$. 

We can then clearly see that 

$$
R_1^{U(N)}(\theta)=\frac N {2\pi}
$$

This becomes more complicated for the two point correlation function, where $n=2$. 

Remember our notation. We then have 

$$
(S_N(\theta_k-\theta_j))=\frac{1}{2\pi}\begin{pmatrix}N&\frac{\sin\left(\frac{N\langle\theta_1-\theta_2\rangle}{2}\right)}{\sin\left(\frac{\theta_1-\theta_2}{2}\right)}\\\frac{\sin\left(\frac{N\langle\theta_2-\theta_1\rangle}{2}\right)}{\sin\left(\frac{\theta_2-\theta_1}{2}\right)}&N\end{pmatrix}
$$

*The diagonal terms are $N$ because in this case, we have $S_N(0)$ again, which we already showed above was $N/2\pi$ (we take the $1/2\pi$ outside the matrix).* 

We can then take the determinant of this matrix to find the two point correlation function as

$$
R_2^{\mathrm{U}(N)}(\theta_1,\theta_2)=\det_{2\times2}(S_N(\theta_k-\theta_j))
$$

and as such

$$
R_2^{U(N)}(\theta_1, \theta_2)=\frac{N^{2}}{(2\pi)^{2}}\left[1-\left(\frac{\sin\left(\frac{N(\theta_{2}-\theta_{1})}{2}\right)}{N\sin\left(\frac{\theta_{2}-\theta_{1}}{2}\right)}\right)^{2}\right]
$$

We have used the fact that $\sin(-x)=\sin(x)$ here to show that the off-diagonal terms are in fact, equal.

- We also took $N^2$ outside
    - We also divided by $N$ in the second term since we need to be consistent with this.