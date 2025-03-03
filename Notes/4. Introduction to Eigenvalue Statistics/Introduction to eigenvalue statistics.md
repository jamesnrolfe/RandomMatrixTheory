#Notes

A unitary matrix $U$ with dimensions $N\times N$ will have $N$ eigenvalues lying on the **unit circle** in the complex plane. This stems from the fact that unitary matrices describe complex rotations.

These eigenvalues will be of the form

$$ e^{i\theta_1}, e^{i\theta_2}, \dots,e^{i\theta_N} $$

We can order the arguments such that

$$ \theta_1 \leq \theta_2 \leq \dots \leq \theta_N $$
![[Pasted image 20250204105934.png]]
*We can see that the eigenvalues tend to “repel” each other - this leads to the spacing between them being more consistent. This should be a surprising result, given the matrix was initially randomized.*

We can see that the eigenvalues tend to “repel” each other - this leads to the spacing between them being more consistent. This should be a surprising result, given the matrix was initially randomized.

Let’s imagine we wrote some computer code to generate $N\times N$ unitary matrices. Each matrix will give us a list of eigenangles as before, which lie in the range

$$ 0<\theta_1\leq \theta_2\leq \dots \leq \theta_N\leq 2\pi $$

They will have a density of $N/2\pi$ - this is clear if you imagine that all the angles ($N$ angles) must be within the unit circle ($0\to2\pi$).

Often in statistics here we scale the eigenvalues such that _on average_, the spacing between them is $1$. This can be done simply by multiplying each eigenangle by the density.

$$ \phi_1=\theta_1 \frac{N}{2\pi}, \dots,\phi_N=\theta_N\frac{N}{2\pi} $$

This allows us to compare matrices of different sizes more easily.

Now let’s find the spacing between consecutive eigenvalues

$$ \phi_2-\phi_1, \phi_3-\phi_2,\dots,\phi_N-\phi_{N-1} $$

and then make a histogram of these differences, which we can normalize to have area $1$ such that it approximates the probability density of the eigenangle spacings. This is sometimes called the **spacing distribution**.
![[Pasted image 20250204110221.png]]*We can demonstrate the difference between the spacing distribution of the eigenangles (a) to uncorrelated points (b).*
