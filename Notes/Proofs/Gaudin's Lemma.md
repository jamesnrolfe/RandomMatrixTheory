---
dg-publish: true
---
#Proof 

**Gaudin's lemma** states that if we have a function of two variables $f(x,y)$ which is integrable on an interval $J$ and such that 

$$
\int_{J}f(x,y)f(y,z)dy=Kf(x,z)
$$

for all $x$ and $z$ and where $K=K(f,J)$ is a constant, and that 

$$
\int_{J}f(y,y)dy=D
$$

where $D=D(f,J)$ is also a constant, then

$$
\int_{J}\det_{n\times n}(f(x_{j},x_{k}))dx_{n}=(D-(n-1)K)\det_{(n-1)\times(n-1)}(f(x_{j},x_{k}))
$$

