#Notes 

In [[Spacing distribution of a Poisson sequence]] we saw that the probability density of the spacings in a *Poisson sequence* is $p(s)=e^{-s}$ (where we normalised the mean spacing to one). 

Now, we want to compute the spacing distribution of the eigenvalues of the $2\times 2$ GOE. 

For a $2\times 2$ matrix, the spacing between consecutive eigenvalues is simply $s=|\lambda_2-\lambda_1|$. Consider the j.p.d.f. for the eigenvalues

$$
P_1(\lambda_1,\lambda_2)=\frac{1}{4\sqrt{\pi}}|\lambda_2-\lambda_1|\exp\left[-\frac{1}{2}\left(\lambda_1^2+\lambda_2^2\right)\right]
$$

Let us change variables such that

$$
\mu_1=\lambda_1-\lambda_2, \quad \mu_2=\lambda_1+\lambda_2
$$

We can then find the Jacobian. 

$$
\bigg | \frac{\partial(\lambda_1,\lambda_2)}{\partial (\mu_1, \mu_2)} \bigg | = \frac{1}{2}
$$

Furthermore, we can say that $s=|\mu_1|$ and $\lambda_1^2+\lambda_2^2=\frac12 \big( s^2+\mu^2_2 \big )$. Therefore, we find

$$
P_1(s,\mu_2)=\frac{s}{8\sqrt \pi} \exp \bigg [-\frac{1}4\Big (s^2-\mu^2_2\Big )\bigg ]
$$

Now, if we integrate this over $\mu_2$ to get rid of its dependence, so we are left with a p.d.f. of only the spacings, we find

$$
p_1(s)=Cs\exp(-\alpha s^2)
$$

Here, the constants $C$ and $\alpha$ are determined by the two conditions 

$$
\int_0^\infty p_1(s)ds=1\quad\mathrm{and}\quad\int_0^\infty sp_1(s)ds=1
$$

The first condition says that the total probability of finding a spacing of any length must be one. The second fixes the mean spacing to be one (see that it looks like an expected value integral). 

The first condition then evaluates to 

$$
C\int_0^\infty s\exp(-\alpha s^2)ds=1,\quad\frac{C}{2\alpha}=1
$$

and the second 

$$
2\alpha\int_0^\infty s^2\exp\left(-\alpha s^2\right)ds=1,\quad\frac{1}{2}\sqrt{\frac{\pi}{\alpha}}=1
$$

Finally, we obtain the **Wigner sumrise**:

$$
p_1(s)=\frac{\pi s}2 \exp \Big (-\frac{\pi}{4}s^2\Big )
$$

An important thing to note here is that the Wigner sumrise is exact for $2\times 2$ matrices, but only gives a (very) good *approximation* for arbitrarily large matrices. 

We could have done this for the $2\times 2$ [[Hermitian Matrices]] (GUE). Remember here we had a j.p.d.f. of

$$
P_{2}(H)=\frac{2}{\pi^{2}}\exp\left(-\operatorname{Tr}H^{2}\right)=\frac{2}{\pi^{2}}\exp\left(-h_{11}^{2}-h_{22}^{2}-2\left|h_{12}\right|^{2}\right)
$$

The j.p.d.f. of the eigenvalues was 

$$
P_2(\lambda_1,\lambda_2)=\frac{1}{\pi}\left|\lambda_2-\lambda_1\right|^2\exp\left(-\lambda_1^2-\lambda_2^2\right)
$$

and so, the spacing distribution is 

$$
p_2(s)=\frac{32s^2}{\pi^2}\exp\left(-\frac{4s^2}{\pi}\right)
$$

It is true that as with the GOE, the spacing distribution is exact for $2\times 2$ matrices, and a good approximation for higher dimensions.
![[Screenshot 2025-02-04 at 12.20.33.png]]
*We can see the differing strengths of the repulsions between the two near zero spacing, as a result of the squared term in the GUE. It is more likely to have close spacings in the GOE than the GUE. *
