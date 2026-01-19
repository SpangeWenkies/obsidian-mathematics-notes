
# Definition: Weak derivative

**Type:** #definition  

## Definition
- Let $\Omega \subset \mathbb{R}^{n}$ be an [[Openness|open]] set
- A function $u \in L^1_{loc}(\Omega)$ has a weak derivative $D^{\alpha}u$ of order $|\alpha|$ if $\exists$ a function $v \in L^{1}_{loc}(\Omega)$ s.t.: $$\int_{\Omega}v(x)\phi(x)dx=(-1)^{|\alpha|}\int u(x)D^{\alpha}\phi(x)dx,$$ for all [[Smooth function|smooth functions]] with a [[Compact support]] in $\Omega$
- If this $v$ exists, it is unique [[almost everywhere]] and is the weak derivative $D^{\alpha}u$
- This weak derivative is written as $$D^{\alpha}u=\frac{\partial^{|\alpha|}u}{\partial x_{1}^{\alpha_{1}}\partial x_{2}^{\alpha_{2}}\dots\partial x_{n}^{\alpha_{n}}}$$

## Intuition (optional)
- The weak derivative is defined using [[Integration by parts]] , this means it exists even if classical derivatives do not exist like for e.g. $u(x)=|x|$
- Rather than requiring pointwise [[Differentiability]]  , we only require the derivative to act correctly under pairing with smooth [[Test function|test functions]] 

## Equivalent Formulations (optional)


## Related Concepts

