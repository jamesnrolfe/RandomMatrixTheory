#Notes 

To prove the first result in this section, we need the following proposition.

>[!info] Proposition 18.8
>[[Technical preparations#^4247d5|The Stieltjes transform of the normalised eigenvalue counting measure]] $S_{N}(z)$ *for the GUE* has the following properties:
>1. For all $\mathrm{Im}(z) \geq 2$,
>$$\lim_{ N \to \infty } \mathbb{E}_{N}[S_{N}(z)]=f(z)$$
>exists, where $f=f(z)$ is the unique solution of the equation
>$$f^{2}+2zf+2=0$$
>subject to 
>$$\mathrm{Im}(f(z))\times \mathrm{Im}(z)>0  \text{ for } \mathrm{Im}(z)\geq 2\quad\text{and}\quad  \lim_{ \eta \to +\infty } \eta|f(i\eta)|=1 $$
>2. For all $\mathrm{Im}(z)\geq 2$ and $N\in \mathbb{N}$,
>$$\text{Var}_{N}(S_{N}(z))=\mathbb{E}_{N}[|\gamma_{N}(z)|^{2}]\leq \frac{1}{24N^{2}}$$
>with $\gamma_{N}(z)$ the centered version of the random variable $S_{N}(z)$ i.e.
>$$\gamma_{N})(z):= S_{N}(z)-\mathbb{E}_{N}[S_{N}(z)]$$
>(*proof non examinable, see lecture notes page 68*)

>[!info] Corollary 18.9
>Consider the GUE and let $\bar{\mathcal{N}}_{N}$ be the normalised counting measure of its eigenvalues. Then, for $\sigma(x)=\sigma_{\frac{1}{2}}(x)$ the semicircle density with $t=\frac{1}{2}$,
>$$\mathcal{P}_{N}\Big(\lim_{ N \to \infty } \bar{\mathcal{N}}_{N}(\Delta)=\int_{\Delta}\sigma(x)dx\Big)=1$$
>for any interval $\Delta \subset \mathbb{R}$. 
>(*proof non examinable, see lecture notes page 72*)

