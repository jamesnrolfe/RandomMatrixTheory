#Proof

The **Transposing Lemma** states that 

$$
\det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))=\det_{n\times n} \left( \sum^n_{l=1}\psi_{l}(x_{j})\phi_{l}(x_{k}) \right)
$$

To prove the transposing Lemma, we will use the fact that

$$
\det A \det B = \det A^{t}\det B=\det A^tB
$$

which we are allowed to do, because $\det A=\det A^t$. 

Consider $\det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))$.

$$
\begin{align}
\det_{n\times n}(\psi_{m}(x_{p}))\det_{n\times n}(\phi_{m}(x_{p}))&= \det_{n\times n}(\psi_{m}(x_{p}))^t\det_{n\times n}(\phi_{m}(x_{p})) \\
 \\
&= \det_{n\times n} (\psi_{m}(x_{p}))^t(\phi_{m}(x_{p}))
\end{align}
$$

Furthermore, we can take the term inside the determinant in the final line further.

$$
\begin{align}
((\psi_{m}(x_{p}))^{t(\phi_{m}(x_{p})) )_{jk}}&= \sum_{l=1}^{n} (\psi_{m}(x_{p}))^{t}_{jl}\cdot (\phi_{m}(x_{k}))_{lk} \\
 \\
&= \sum^n_{l=1}(\psi_{m}(x_{p}))_{lj}\cdot(\phi_{m}(x_{p}))_{lk} \\
 \\
&= \sum^n_{l=1}\psi_{l}(x_{j})\phi_{l}(x_{k})
\end{align}
$$
~={Grey}*See below for intuition on where the sum introduced here comes from.*=~

and so clearly 

$$
\det_{n\times n}(\psi_{j}(x_{k}))\det_{n\times n}(\phi_{j}(x_{k}))=\det_{n\times n} \left( \sum^n_{l=1}\psi_{l}(x_{j})\phi_{l}(x_{k}) \right)
$$

---

To see how the sum works in the above equation, consider two $2\times 2$ matrices.

$$
X=\begin{pmatrix}
x_{00} & x_{01} \\x_{10} & x_{11}
\end{pmatrix}, \quad

Y=\begin{pmatrix}
y_{00} & y_{01} \\ y_{10} & y_{11}
\end{pmatrix}
$$

Now consider what happens when we compute $X^{t}Y$.

$$
M=X^{t}Y=\begin{pmatrix}
x_{00}y_{00}+x_{10}y_{10}&x_{00}y_{01}+x_{10}y_{11} \\ x_{01}y_{00}+x_{11}y_{10}&x_{01}y_{01}+x_{11}y_{11}
\end{pmatrix}
$$

Simply by inspection, we can say that $(M_{jk})=x_{0j}y_{0k}+x_{1j}y_{1k}$. And so we can write each term as 

$$
(M_{jk})=\sum^{1}_{l=0}x_{lj}y_{lk}
$$

which we can generalise to a $n\times n$ matrix as 

$$
(M_{jk})=\sum^{n-1}_{l=0}x_{lj}y_{lk}
$$

which is exactly what we see in the above proof, where instead we use $x_{jl}^t=x_{lj}$. Note that we also start indexing at one in the above, so $n-1\to n$.