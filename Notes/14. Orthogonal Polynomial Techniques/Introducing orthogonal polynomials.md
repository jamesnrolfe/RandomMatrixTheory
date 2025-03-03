#Notes 

We have the following theorem.

Given an arbitrary weighting function $w(\lambda)$ (see [[Orthogonal polynomial techniques]]), there exists a unique (up to a constant of proportionality) sequence of polynomials such that 

$$
(p_{j}, p_{k})=\int _{J} w(\lambda)p_{j}(\lambda)p_{k}(\lambda)d\lambda=N_{k} \delta_{jk}
$$

The sequence $p_{j}(\lambda)$ are called **orthogonal polynomials** with weight $w(\lambda)$. $p_{j}(\lambda)$ is a polynomial of order $j$ i.e. 

$$a_{j}\lambda^j+a_{j-1}\lambda^{j-1}+\dots+a_{1}\lambda+a_{0}$$

We will fix the arbitrary constant of proportionality by setting the coefficient of $\lambda^k$ in $p_{k}(\lambda)$ equal to one (so in the above, we would say $a_{k}=1$). When we do this, we call the polynomials we arrive at **monic polynomials**.

We can denote $(p_{j-1}(\lambda_{k}))$ by the matrix

$$
(p_{j-1}(\lambda_{k}))=\begin{pmatrix}
p_{0}(\lambda_{1}) & p_{0}(\lambda_{2}) & \dots & p_{0}(\lambda_{n}) \\
p_{1}(\lambda_{1}) & p_{1}(\lambda_{2}) & \dots & p_{1}(\lambda_{n}) \\ 
p_{2}(\lambda_{1}) & p_{2}(\lambda_{2}) & \dots & p_{2}(\lambda_{n}) \\  
\vdots & \vdots & \vdots & \vdots \\
p_{n}(\lambda_{1}) & p_{n}(\lambda_{2}) & \dots&p_{n}(\lambda_{n})
\end{pmatrix}
	$$

where $p_{j}(\lambda)$ is a polynomial of degree $j$. 

We have already seen matrices of this form! If we set $p_{j}(\lambda)=\lambda^j$ then we get the *determinant of theVandermonde matrix*, as seen in [[The joint probability density function for the eigenvalues]]. 

$$
V^t=\begin{pmatrix}1&1&1&\cdots&1\\\lambda_1&\lambda_2&\lambda_3&\cdots&\lambda_n\\\lambda_1^2&\lambda_2^2&\lambda_3^2&\cdots&\lambda_n^2\\\cdots&\cdots&\cdots&\cdots&\cdots&\\\lambda_1^{n-1}&\lambda_2^{n-1}&\lambda_3^{n-1}&\cdots&\lambda_n^{n-1}\end{pmatrix}
$$

We thus introduce another theorem.

If $\{p_{j}(\lambda)\}_{j=0,\dots,n-1}$ is a sequence of *monic* polynomials we have

$$
\det_{n\times n}(p_{j-1}(\lambda_{k})) = \det_{n\times n} (\lambda_{k}^{j-1})=\prod _{1\leq j<k\leq n} (\lambda_{k}-\lambda_{j})
$$

To see this, let 

$$
p_{j}(\lambda)=\lambda^j+a_{j-1}\lambda^{j-1}+\dots+a_{1}\lambda+a_{0}
$$

where the coefficients may be different for each polynomial $p_{j}(\lambda)$. The determinant of a matrix does not change if we add to a row a linear combination of the other rows. This will be important. 

At this point, our matrix looks like 

$$
\begin{pmatrix}
p_0(\lambda_1)&p_0(\lambda_2)&\ldots&p_0(\lambda_n)\\p_1(\lambda_1)&p_1(\lambda_2)&\ldots&p_1(\lambda_n)\\\vdots&\vdots&\ddots&\vdots\\p_{n-1}(\lambda_1)&p_{n-1}(\lambda_2)&\ldots&p_{n-1}(\lambda_n)\end{pmatrix}
$$

but we know that all the $p_{0}(\lambda)$s are equal to one, and so we have 

$$
\begin{pmatrix}
1 & 1 & \cdots & 1\\p_1(\lambda_1)&p_1(\lambda_2)&\ldots&p_1(\lambda_n)\\\vdots&\vdots&\ddots&\vdots\\p_{n-1}(\lambda_1)&p_{n-1}(\lambda_2)&\ldots&p_{n-1}(\lambda_n)\end{pmatrix}
$$

The idea now is that each polynomial can be expressed in terms of the previous polynomials using a *recurrence relation*.

Consider $p_{n-1}(\lambda)$, which has the form

$$
p_{n-1}(\lambda)= \lambda^{n-1}+a_{n-2}\lambda^{n-2}+\dots+a_{1}\lambda+a_{0}
$$

We want to take linear combinations of the previous rows to eliminate the lower order terms. We will first multiply the first row by $a_{0}$, the second by $a_1$ and so on to get 

$$
\begin{pmatrix}
a_{0} & a_{0} & \dots & a_{0} \\
a_{1}p_{1}(\lambda_{1}) & a_{1}p_{1}(\lambda_{2}) & \dots & a_{1}p_{1}(\lambda_{n}) \\
\vdots&\vdots&\ddots&\vdots \\
p_{n-1}(\lambda_{1}) & p_{n-1}(\lambda_{2}) & \dots & p_{n-1}(\lambda_{n})
\end{pmatrix}
$$

Then we transform the final row by turning it into 

$$
p_{n-1}(\lambda) \mapsto p_{n-1}(\lambda) -\sum^{n-2}_{j=0} a_{j}\lambda^{j}= \lambda^{n-1}
$$

which as we stated earlier, should not change the determinant. Notice how this is essentially taking away all the rows above the last row from the last row, leaving only the leading term and since the polynomials are monic, we should just end up with the last row being

$$
(\lambda_{1}^{n-1}, \lambda_{2}^{n-1},\dots,\lambda_{n}^{n-1})
$$

which is looking like the Vandermonde matrix! We can do the same thing for the other rows, and thus its determinant becomes 

$$
\det_{n\times n}(p_{j-1}(\lambda_{k})) = \det_{n\times n} (\lambda_{k}^{j-1})=\prod _{1\leq j<k\leq n} (\lambda_{k}-\lambda_{j})
$$

where the matrix in the second term *is the Vandermonde matrix*, with its determinant being the third term.