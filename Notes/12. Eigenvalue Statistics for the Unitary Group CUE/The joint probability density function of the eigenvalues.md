---
dg-publish: true
---
#Notes 

The starting point to study statistics of eigenvalues of random matrices is the **joint probability distribution function** for the eigenvalues. This is a real positive function 

$$
P_{N2}(\theta_1, \theta_2, \dots, \theta_N)
$$

with the condition

$$
\int_0^{2\pi}\int_0^{2\pi}\cdots\int_0^{2\pi}P_{N2}(\theta_1,\theta_2,\ldots,\theta_N)d\theta_1d\theta_2\cdots d\theta_N=1
$$

The probability that a matrix, taken at random, will have the arguments of its eigenvalues lying in the intervals 

$$
\theta_{1}^{i}<\theta_{1}<\theta_{1}^{f},\quad\theta_{2}^{i}<\theta_{2}<\theta_{2}^{f},\quad\ldots,\quad\theta_{N}^{i}<\theta_{N}<\theta_{N}^{f}
$$

is given by

$$
\int_{\theta_1^i}^{\theta_1^f}\int_{\theta_2^i}^{\theta_2^f}\cdots\int_{\theta_N^i}^{\theta_N^f}P_{N2}(\theta_1,\theta_2,\ldots,\theta_N)d\theta_1d\theta_2\cdots d\theta_N
$$

For the CUE (or the unitary ensemble), we state now, without proof, that the formula for the j.p.d.f. of the eigenvalues is

$$P_{N2}(\theta_1,\ldots,\theta_N)=\frac{1}{(2\pi)^NN!}\prod_{1\leq j<k\leq N}\left|e^{i\theta_k}-e^{i\theta_j}\right|^2$$