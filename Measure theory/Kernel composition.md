
# Definition: Kernel composition

**Type:** #definition  

## Definition
- Take two [[Kernel|kernels]], e.g., [[Transition kernel]] $K_{1}:X\mapsto Y$ and $K_{2}:Y\mapsto Z$ 
- We then define their composition as $$(K_{1},K_{2})(x,C)=\int_{Y}K_{2}(y,C)K_{1}(x,dy),$$
	For some [[Measurability|measurable]] $C \subseteq Z$ 
- Now $(K_{1},K_{2})(x,C)$ is itself a [[Kernel]]/[[Transition kernel]]
## Intuition (optional)
- This composition comes from [[Chapman-Kolmogorov]] equation: $$P(X_{2}\in C|X_{0}=x)=\int_{Y}P(X_{2}\in C|X_{1}=y)P(X_{1}\in dy|X_{0}=x)$$
- It describes a two-step transition and we preserve measurability (see [[Fubini's theorem]]/[[Tonelli's theorem]]/measurability of the integrand)

## Equivalent Formulations (optional)


## Related Concepts

