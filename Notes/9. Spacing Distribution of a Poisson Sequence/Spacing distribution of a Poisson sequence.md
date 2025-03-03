#Notes 

Consider $N$ *independent, identically distributed* random points in the interval $[0,L]$. This is akin to saying that we’ve randomly (uniformly) selected $N$ points from $0$ to $L$. 

$$
0 \leq x_1,x_2,\dots,x_N\leq L
$$

The probability measure of each $x_j$ is the uniform distribution $p(x_j)=1/L=\rho$, where $\rho$ is kind of like a density. 

Since these points are independent, their probability distributions multiply into the joint probability density function.

$$
p(x_1,\dots,x_N)=\frac{1}{L^N}
$$

and the one-level density is 

$$
R_1(x)=\frac N{L^N}\int^L_0\dots\int^L_0 dx_2\dots dx_N=\frac{N}{L}
$$

where all the $N-1$ integrals evaluate to $L$, giving us $NL^{N-1}/L^N=N/L$. We can see that this is the density we would expect points to exhibit on the line - $N$ points in a distance $L$. 

The number of expected points in an interval $I=[a,b]$ of length $l=b-a$ is 

$$
\frac{N}{L}\int^b_a dx=\frac{Nl}{L}
$$

which is a density times a length - gives us a number. 

We can generalise this to an infinite sequence of random points. Let

$$
\dots x_j<x_{j+1}<x_{j+2}<\dots<x_{j+N}\dots
$$

have the following properties.

1. The probability that the interval $(x,x+dx)$ contains a point is $\rho dx$ and is independent of $x$ (i.e. is constant).
2. The above probability does not depend on the positions of other points (i.e. they are uncorrelated).

Now we can consider the sequence of the distances between adjacent points: $s_j=x_{j+1}-x_j$. We will call these the $s_j$ spacings. 

The question we want to answer is, what is the probability that a spacing $s$ should have a certain value? That is, what is the probability that given a point at $x$, the interval $(x,x+s)$ is empty and there is a point in the interval $(x+s,x+s+ds)$?

The above is a mathematical way of asking what is the probability of the spacing between two points being a certain value (that there are no points in that spacing, and at the end of it, there is one). 

To figure this out, let’s work through the following steps. First, we divide the interval $s$ into $n$ parts, each of which will have a length $s/n$. An interval of length $s/n$ is either empty or contains one or more point. If $s/n$ is small enough, we can neglect the probability that it contains more than one point. 

The probability that $s/n$ contains a point is $\rho(s/n)$ - remember we said this was $\rho dx$ with $dx$ being some small interval - and the probability that it is empty is hence $1-\rho(s/n)$. Therefore, the probability that $(x,x+s)$ is empty is given by the probability that each of the $n$ parts are empty, i.e.

$$
\bigg (1-\rho\frac sn \bigg )^n
$$

This is looking familiar. Let’s take the limit as $n\to\infty$ (and hence our approximation becomes fact) and we see

$$
\lim_{n\to\infty} \bigg (1-\rho \frac sn \bigg )^n=e^{-\rho s}
$$

This is the probability that the interval $(x,x+s)$ is empty. 

The probability that there is point in $(x+s,x+s+ds)$ is $\rho ds$. So, combining these two probabilities (they are of course independent so we just multiply them), the probability that given a point at $x$ the next point is at $(x+s, x+s+ds)$ is

$$
p(s)ds=\rho e^{-\rho s}ds
$$

Note that we have 

$$
\int_0^\infty p(s)ds=\rho\int_0^\infty e^{-\rho s}ds=1
$$

We can rescale the coordinates $x_j\mapsto \rho x_j$ such that the average spacing is $1$, and we find our p.d.f. to be $p(s)=e^{-s}$.
![[Pasted image 20250204121731.png]]
*We can see the exponential decay on the random uniformly generated points.*