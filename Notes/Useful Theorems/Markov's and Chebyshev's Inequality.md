#Proof 

If $X:\Omega \to \mathbb{R}$ is a scalar random variable with finite $k$th moment, $\mathbb{E}\{ |X|^{k} \}<\infty$. Then, for any $\epsilon>0$,

$$
\mathcal{P}\{ |X|\geq \epsilon \}\leq \mathbb{E} \{ |X|^{k} \}\epsilon^{-k}
$$

and so: 

>[!info] Chebyshev's inequality
>For a scalar random variable $X:\Omega \to \mathbb{R}$ with finite second moment, we have
>$$\mathcal{P}( |X-\mathbb{E}\{ X \} | \geq \epsilon) \leq \frac{1}{\epsilon^{2}}\text{Var}\{ X \}
>$$
>This is **Chebyshev's inequality**. It tells us about the spread of $X$ in relation to its mean - and we can see that if the spread is bigger, i.e. $\epsilon$ is smaller, then the probability of the difference of $X$ and $\mathbb{E}\{ X \}$ being *bigger* than $\epsilon$ goes up. 

and for one with finite first moment, we have:

>[!info] Markov's inequality
>For a scalar random variable $X:\Omega \to \mathbb{R}$ with finite first moment, we have
>$$\mathcal{P}(|X|\geq\varepsilon)\leq \frac{\mathbb{E}[|X|]}{\varepsilon}$$
>This is **Markov's inequality**.

