#Notes 

Suppose we are investigating some quantity $X$ that takes values in $\mathbb{R}$. This might be, for example, the time spent queueing at a bus stop.

Any well behaved, non-negative, real function $p(x)$ normalized to one defines a probability **measure** on the line (line because we are in one dimension).

Measure is another way of saying **probability distribution**, and $p(x)$ is a **probability distribution function** (p.d.f.).

We denote the measure of an infinitesimal interval $(x,x+dx)$ by

$$ d\mu(x)=p(x)dx $$

The p.d.f. is normalized to one if

$$ \int^\infty_{-\infty}p(x)dx=1 $$

For any interval $I=(a,b)$, the probability that $X$ lines inside the interval $I$ is written as

$$ P\{X\in I\}=\mu(I)=\int_Ip(x)dx=\int^b_ap(x)dx \geq 0 $$

Probability density functions give us the information required to calculate probabilities.