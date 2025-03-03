#Notes 

Many random matrix ensembles have a beautiful structure that we can exploit to calculate eigenvalue statistics. In particular, the j.p.d.f. and correlation function can often be written as determinants. Let’s explore this. 

Let’s get some notation sorted first.

If $f(x,y)$ is a function of two variables, then we denote a square matrix $(f(x_j,x_k))$ where

$$
(f(x_j,x_k))=\begin{pmatrix}f(x_1,x_1)&\cdots&f(x_1,x_n)\\\vdots&\ddots&\vdots\\f(x_n,x_1)&\cdots&f(x_n,x_n)\end{pmatrix}
$$

This could be of any dimensions. If we add indicies e.g. $(f(x_j,x_k))_{lm}$, we mean the term on $l$-th row and $m$-th column. 

We often need to denote the determinants of matrices of different sizes, and so we say

$$
\det_{n\times n} (f(x_j,x_k))
$$

denotes the determinant of the above matrix with a size $n\times n$. 

We are aiming for

1. Prove that 
    
    $$
    \prod_{1\leq j<k\leq N}\left|e^{i\theta_k}-e^{i\theta_j}\right|^2=(2\pi)^N\det_{N\times N}\left(S_N(\theta_k-\theta_j)\right)
    $$
    
    where 
    
    $$
    S_N(\theta)=\frac{1}{2\pi}\frac{\sin\left(\frac{N\theta}{2}\right)}{\sin\frac{\theta}{2}}
    $$
    
2. Show that
    
    $$
    R_n^{\mathrm{U}(N)}(\theta_1,\ldots,\theta_n)=\det_{n\times n}\left(S_N(\theta_k-\theta_j)\right)
    $$
    

A very important point is that $R^{U(N)}_n$ *only* depends on the difference of the arguments $\theta_j$. This is a consequence of the fact that the LHS of the above is invariant under mapping $\theta_j \mapsto\theta_j+\alpha$.