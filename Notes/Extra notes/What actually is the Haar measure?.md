---
dg-publish: true
---
A **measure** provides a description for how things are distributed in a mathematical set or space. 

For example, consider integrating some function in spherical coordinates. 

$$
\int_{r}\int_{\theta}\int_{\phi} f(r,\theta,\phi) \cdot r^{2}\sin \theta dr d\theta d\phi
$$

The "measure" part of this is 

$$
 r^{2}\sin \theta dr d\theta d\phi
$$

which we can see is related to the Jacobian. It tells us how the "stuff" on the surface of the sphere is distributed in *spherical coordinates*.

This might also be a measure on a probability distribution, or even the **Gibbs measure**

$$
p(x)=\frac{e^{-BE(x)}}{Z(\beta)}
$$

in thermodynamics. 

The **Haar measure** is simply a measure that tells us about $N\times N$ unitary matrices. In other words, if we want to integrate a function over $N\times N$ unitary matrices, or sample from the set of all unitary matrices, we need the Haar measure. 

![](https://www.youtube.com/watch?v=d4tdGeqcEZs)

