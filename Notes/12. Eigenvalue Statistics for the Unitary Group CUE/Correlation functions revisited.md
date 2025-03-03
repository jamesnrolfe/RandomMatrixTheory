---
dg-publish: true
---
#Notes 

In the cases that we will consider the *j.p.d.f.*, $P_N$ is invariant under the permutations of its arguments i.e.

$$
P_N(\theta_1,\theta_2,\ldots,\theta_N)=P_N(\theta_{\sigma1},\theta_{\sigma2},\ldots,\theta_{\sigma N})
$$

where $\sigma$ is any permutation of $[1,N]=\{ 1,\dots,N\}$. We then define the $n$-th correlation function as 

$$
R_n(\theta_1,\ldots,\theta_n)=\frac{N!}{(N-n)!}\int_0^{2\pi}\cdots\int_0^{2\pi}P_N(\theta_1,\ldots,\theta_N)d\theta_{n+1}\cdots d\theta_N
$$

Remember that $R_1(\theta)d\theta$ gives the expected number of arguments of the complex numbers $e^{i\theta_1}$ etc. in a small neighbourhood of $\theta$. 

For the two point correlation function, there are $N(N-1)$ ways of choosing an ordered pair of $\theta$s among $N$. Then, $R_2(\theta_1,\theta_2)d\theta_1d\theta_2$ then gives the expected number of such pairs where the first is in a small neighbourhood of $\theta_1$, and the second is in a small neighbourhood of $\theta_2$. 

This generalises to the $n$ case. 

It is interesting to note that the spacing distribution requires knowledge of all $R_n$s - that is, it incorporates information about $n$-tuples of eigenvalues for all values of $n$. 

Our main goal will be to compute

$$
R_n^{\mathrm{U}(N)}(\theta_1,\ldots,\theta_n)=\frac{N!}{(N-n)!}\int_0^{2\pi}\cdots\int_0^{2\pi}P_{N2}(\theta_1,\ldots,\theta_N)d\theta_{n+1}\cdots d\theta_N
$$