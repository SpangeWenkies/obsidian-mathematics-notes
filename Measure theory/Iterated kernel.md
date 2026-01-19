
# Definition: Iterated kernel

**Type:** #definition  

## Definition
- by repeated [[Kernel composition]] we can build an $n$-step [[kernel]]/[[Transition kernel]] (discrete) or a $t$-step kernel (continuous)
	- Discrete: $$K^{n}=K*K*\dots*K\text{ , giving }K^{n}(x,A)=\int K^{n-1}(y,A)K(x,dy)$$ is the probability of going from $x$ to set $A$ in $n$ steps
	- Continuous: Let $K_{t}$ be the kernel for time $t$, then by [[Chapman-Kolmogorov]]: $$K_{t+s}(x,A)=\int_{Y}K_{s}(x,dy)K_{t}(y,A)$$, which is just continuous kernel composition and this gives $K_{nt}=K^{n}_{t}$

## Intuition (optional)


## Equivalent Formulations (optional)


## Related Concepts

