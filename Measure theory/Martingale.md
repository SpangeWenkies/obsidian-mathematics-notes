
# Definition: Martingale

**Type:** #definition  

## Definition
- A [[Stochastic process]] $Y:T\times \Omega\mapsto S$, where $S$ is a [[Banach space]] with norm $||.||_{S}$ is a Martingale w.r.t. its [[Filtration]] $\Sigma_{*}$ and probability [[Measure]] $\mathbb{P}$ if:
	- $\Sigma_{*}$ is a filtration of the under the probability [[Measure space]] $(\Omega ,\Sigma,\mathbb{P})$
	- $Y$ is [[Adapted to]] filtration $\Sigma_{*}$ , i.e., $\forall t\in T$, where $T$ is an [[Index set]], $Y_{t}$ is a $\Sigma_{t}$-[[Measurable function]] 
	- $\forall t, Y_{t}\in L^{1}(\Omega, \Sigma_{t}, \mathbb{P};S)\text{, i.e., }E_{\mathbb{P}}[||Y_{t}||_{S}]<\infty$
	- $\forall \{s,t|s<t\}$ and all $F\in \Sigma_{S}$, we have the [[Martingale property]], i.e., $$E_{\mathbb{P}}[[Y_{t}-Y_{s}]_{\chi_{F}}]=0,\text{ where }\chi_{F}\text{ is an indicator function of event }F$$ $$\iff$$ $$Y_{s}=E_{\mathbb{P}}[Y_{t}|\Sigma_{S}]$$
	- A stochastic process could have the martingale property w.r.t. one measure but not another
	- [[Girsanov's theorem]] gives a way to find a measure to which some [[Itō process]] is a martingale
 
## Intuition (optional)


## Equivalent Formulations (optional)


## Related Concepts

