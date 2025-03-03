#Notes 

We are now going to define correlation functions for unitary matrices. This tells us information about the probability of eigenstates being where they are, relative to other eigenstates. 

Consider the eigenvalues $e^{i\theta_1},\dots,e^{i\theta_N}$ for a $N\times N$ unitary matrix $U$. Take the arguments, which here *don’t have to be in order*

$$
0 \leq \theta_1,\dots,\theta_N \leq 2\pi
$$

The j.p.d.f. of the $\theta_1,\dots,\theta_N$ for $U(N)$ (which is the set of all $N\times N$ unitary matrices) with **Haar (uniform) measure** is

$$
P_{N2}(\theta_1,\dots,\theta_N)=\frac{1}{(2\pi)^NN!}\prod_{1\leq j < k \leq N} \big |e^{i\theta_k}-e^{i\theta_j}\big |^2
$$

We wont prove this, but let’s see if this would give us the result that we would expect. We saw in [4.1: Unitary matricies](https://www.notion.so/4-1-Unitary-matricies-17d420b0cf9f80d6a68fdb0349c7bfdf?pvs=21) that the eigenvalues from a random matrix are spaced out evenly. We can indeed see this here - for consecutive eigenangles, the probability is largest when they are further apart (if $e^{i\theta_k} \approx e^{i\theta_j}$ then we get a probability of $\approx 0$). So, we can see the repulsion here that we expected. 

We can also note that this is *symmetric in the eigenangles*. If we swapped $\theta_1$ and $\theta_2$, then the product wouldn’t change. 

$$
P_{N2}(\theta_1,\theta_2,\dots,\theta_N)= P_{N2}(\theta_2, \theta_1,\dots,\theta_N)
$$

The measure on the infinitesimal interval, which would be a $N$-dimensional “volume” $(\theta_1,\theta_1+d\theta_1)\times (\theta_2,\theta_2+d\theta_2)\times \dots \times (\theta_N,\theta_N+d\theta_N)$ would be 

$$
P_{N2}(\theta_1,\dots,\theta_N)d\theta_1\dots d\theta_N
$$

In other worlds, this is the *probability of finding the eigenangle $\theta_j$ in the infinitesimal interval $(\theta_j,\theta_j+d\theta_j)$ for $j=1,\dots,N$.* Note that to make this a probability, we must include the $d\theta_1\dots d\theta_N$. 

The probability that a random matrix from $U(N)$ with Haar measure has eigenangle $\theta_1$ in the interval $(a_1,b_1)$, as well as $\theta_2$ in $(a_2,b_2)$ and so on until $\theta_N$ in $(a_N,b_N)$ is

$$
\int^{b_1}_{a_1}\int^{b_2}_{a_2}\dots \int^{b_N}_{a_N}P_{N2}(\theta_1,\dots,\theta_N)d\theta_1\dots d\theta_N
$$

We will now define the $n$**-point correlation function**. 

$$
R_n(\theta_1,\dots,\theta_n)=\frac{N!}{(N-n)!}\int^{2\pi}_{0}\int^{2\pi}_{0}\dots \int^{2\pi}_{0}P_{N2}(\theta_1,\dots,\theta_N)d\theta_{n+1}\dots d\theta_N
$$

This function tells us how likely that *any $n$* eigenvalues lie near $\theta_1,\dots\theta_n$. So for example, if we looked at $R_2(\theta_1,\theta_2)$ with $N=4$, then we would get back some result which tells us how likely $\theta_3$ is to be near $\theta_1$, and how likely $\theta_4$ is to be near $\theta_2$ (or $\theta_4$ near $\theta_1$, $\theta_3$ near $\theta_2$). 

Perhaps a better way to put it is to say that $R_n(\theta_1,\dots,\theta_n)$ is the joint probability density that *any $n$* of the $N$ total eigenangles are simultaneously near $\theta_1,\dots,\theta_n$, while the remaining $N-n$ can be anywhere.

Note that the correlation functions are *not* normalized to one, because of the pre-factor $N!/(N-n)!$. 

We can then define the **one-point correlation** or **one-level density**,

$$
R_1(\theta)=N\int^{2\pi}_{0}\dots \int^{2\pi}_{0}P_{N2}(\theta,\dots,\theta_N)d\theta_{2}\dots d\theta_N
$$

where we can see that $N!/(N-1)!=N$. Based on the description above, this can be thought of as the probability that any eigenangle is near $\theta$. $R_1(\theta)$ is normalized to $N$ such that

$$
\int^{2\pi}_0R_1(\theta)d\theta =N
$$

If we let $I=[a,b]$ be an interval within $[0,2\pi)$. We can state that the expected number of eigenangles in $I$ is

$$
\int^b_aR_1(\theta)d\theta
$$

Naturally then, we could consider the **two-point correlation function** or **pair correlation**. 

$$
R_2(\phi, \chi)=N(N-1)\int^{2\pi}_{0}\dots \int^{2\pi}_{0}P_{N2}(\phi, \chi,\theta_3,\dots,\theta_N)d\theta_{3}\dots d\theta_N
$$

Since now we consider pairs, we can think of the pre-factor of saying that there are $N$ ways to chose the first eigenangle, and then $N-1$ ways to chose the second. We have now labelled the eigenstates differently (as $\phi$ and $\chi$) to highlight that these are the angles we are searching the neighborhood of, if you like. 

$R_2$ is normalized such that

$$
\int^{2\pi}_0\int^{2\pi}_0R_2(\phi,\chi) d\phi d\chi=N(N-1)
$$

is the total number of ordered pairs of eigenvalues. The reason they are ordered is convention - if they weren’t we would need an extra factor to account for this, as we could have $\theta_3$ then $\theta_4$ *and $\theta_4$* then $\theta_3$. Instead, we stick to only including $\theta_3$ then $\theta_4$ if $\theta_3<\theta_4$. Ultimately, it doesn’t matter how its done, just that we are consistent. 

If we let $I_1=[a,b)$ and $I_2=[c,d)$ be two intervals in $[0,2\pi)$, then the integral

$$
\int^b_a\int^d_cR_2(\phi,\chi)d\phi d\chi
$$

is the expected number of pairs of eigenangles in $I_1\times I_2$.