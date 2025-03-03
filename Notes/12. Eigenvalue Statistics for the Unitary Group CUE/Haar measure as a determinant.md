#Notes 

See [[What actually is the Haar measure?]]

The first step to compute the $n$-point correlations as a determinant (step 2 in [[Where we are headed]]) is to show that

$$
\prod_{1\leq j<k\leq N}\left|e^{i\theta_{k}}-e^{i\theta_{j}}\right|^{2}=(2\pi)^{N}\det_{N\times N}\left(S_{N}(\theta_{k}-\theta_{j})\right)
$$

and from this, we can prove 

$$
R_n^{\mathrm{U}(N)}(\theta_1,\ldots,\theta_n)=\det_{n\times n}\left(S_N(\theta_k-\theta_j)\right)
$$

First off, let's consider the matrix $(\psi_{j}(x_{k}))$, which written out is

$$
(\psi_{j}(x_{k}))=\begin{pmatrix}\psi_1(x_1)&\cdots&\psi_1(x_n)\\\vdots&\ddots&\vdots\\\psi_n(x_1)&\cdots&\psi_n(x_n)\end{pmatrix}
$$

As seen in [[The joint probability density function for the eigenvalues]], the transpose of the **Vandermonde matrix** $V^t$, where 

$$
V^t=\begin{pmatrix}1&1&1&\cdots&1\\x_1&x_2&x_3&\cdots&x_n\\x_1^2&x_2^2&x_3^2&\cdots&x_n^2\\\cdots&\cdots&\cdots&\cdots&\cdots&\cdots\\x_1^{n-1}&x_2^{n-1}&x_3^{n-1}&\cdots&x_n^{n-1}\end{pmatrix}
$$

is of this type, with $\psi_{j}(x_{k})=x_{k}^{j-1}$.

We will now provide the **Transposing Lemma** (see [[The Transposing Lemma|proof]]).

$$
\det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))=\det_{n\times n} \left( \sum^n_{l=1}\psi_{l}(x_{j})\phi_{l}(x_{k}) \right)
$$
We then have 

$$
\begin{aligned}\prod_{1\leq j<k\leq N}\left|e^{i\theta_{k}}-e^{i\theta_{j}}\right|^{2}&=\Delta(e^{i\theta_{1}},\ldots,e^{i\theta_{N}})\Delta(e^{-i\theta_{1}},\ldots,e^{-i\theta_{N}})\\&=\det_{N\times N}\left(e^{i(j-1)\theta_{k}}\right)\det_{N\times N}\left(e^{-i(j-1)\theta_{k}}\right)\end{aligned}
$$

> [!help] Note
> To see this, look at [[Linear Algebra.pdf|Eq. (7) in Linear Algebra]], where it states that the determinant of a matrix is the product of its eigenvalues. Here, we have separated the modulus squared as $|\psi |^{2}=\psi\psi^*$ and turned it into two determinants.


Let's set $(\psi_{j}(\theta_{k}))=e^{i(j-1)\theta_{k}}$ and $\phi_{j}(\theta_{k})=e^{-i(j-1)\theta_{k}}$. We can then apply the transposing lemma.

$$
\det_{N\times N}\left(e^{i(j-1)\theta_{k}}\right)\det_{N\times N}\left(e^{-i(j-1)\theta_{k}}\right)=\det_{N\times N}\left( \sum^{N}_{l=1}e^{i(l-1)\theta_{j}}e^{-i(l-1)\theta_{k}} \right) = \det_{N\times N}\left( \sum_{l=1}^N e^{i(l-1)(\theta_{k}-\theta_{j})}\right)
$$

and so clearly

$$
\prod_{1\leq j<k\leq N}\left|e^{i\theta_{k}}-e^{i\theta _{j}}\right|^2=\det_{N\times N}\left( \sum_{l=1}^N e^{i(l-1)(\theta_{k}-\theta_{j})}\right)
$$

The matrix elements in the right hand term are geometric sums, and so we can apply the formula for this.

$$
\sum^{N-1}_{k=1}x^k=\frac{{1-x^N}}{1-x}
$$

to obtain 

$$
\sum_{l=1}^{N}e^{i(l-1)(\theta_{k}-\theta_{j})}=\sum_{l=0}^{N-1}e^{il(\theta_{k}-\theta_{j})}=\begin{cases}\frac{1-e^{iN\left(\theta_{k}-\theta_{j}\right)}}{1-e^{i\left(\theta_{k}-\theta_{j}\right)}}&\mathrm{if~}\theta_{k}\neq\theta_{j}\\N&\mathrm{if~}\theta_{k}=\theta_{j}&\end{cases}
$$

> [!Help] Note
> This is because if $\theta_{k}=\theta_{j}$, then the term inside the sum goes to $1$, and so we end up with just a sum of ones up to $N$. If this isn't the case, then we use the geometric sum above. 

In the case $\theta_{k}\neq \theta_{j}$, we can take the result further.

$$
\begin{aligned}\frac{1-e^{iN(\theta_k-\theta_j)}}{1-e^{i(\theta_k-\theta_j)}}&=e^{i\frac{N-1}{2}(\theta_k-\theta_j)}\frac{e^{iN(\theta_k-\theta_j)/2}-e^{-iN(\theta_k-\theta_j)/2}}{e^{i(\theta_k-\theta_j)/2}-e^{-i(\theta_k-\theta_j)/2}}\\&=e^{i\frac{N-1}{2}(\theta_k-\theta_j)}\frac{\sin\left(N\left(\theta_k-\theta_j\right)/2\right)}{\sin\left(\left(\theta_k-\theta_j\right)/2\right)}\\&=2\pi e^{i\frac{(N-1)\theta_{k}}{2}}S_{N}(\theta_{k}-\theta_{j})e^{-i\frac{(N-1)\theta_{j}}{2}}\end{aligned}
$$

where we have used the fact that $S_N(\theta)=\frac{1}{2\pi}\frac{\sin\left(\frac{N\theta}{2}\right)}{\sin\frac{\theta}{2}}$ from [[Where we are headed]]. Then, combining this formula with what we worked out above, we can clearly see that 

$$
\begin{align}
\prod_{1\leq j<k\leq N}\left|e^{i\theta_{k}}-e^{i\theta _{j}}\right|^{2}&= \det_{n\times n}(2\pi e^{i(N-1)\theta_{k}/2}S_{N}(\theta_{k}-\theta_{j})e^{-i(N-1)\theta_{j}/2}) 
 \\
&= (2\pi)^{N}\prod_{n=1}^{N}e^{i(N-1)\theta_{n}/2}\prod_{n=1}^{N} e^\frac{-i(N-1)\theta_{m}}{2}\det_{N\times N}(S_{N}(\theta_{k}-\theta_{j})) \\
 \\
&= (2\pi)^{N} \det_{N\times N} (S_{N}(\theta_{k}-\theta_{j}))
\end{align}

$$

> [!help] Note
> The products and power of $N$ here arise because we are taking a determinant, and essentially these terms (not including $S_{N}$) are coefficients of each term in the matrix, and so we are going to have them in our determinant calculation $N$ times. 


which is what we set out to prove. 