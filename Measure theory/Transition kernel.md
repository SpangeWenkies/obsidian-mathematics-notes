
# Definition: Transition kernel

**Type:** #definition  

## Definition
- Written often as either $K(x,A)$ or $K(x,dy)$ or $P(x,A)$
- Used to define [[Markov process]] and is then called a [[Markov kernel]]
- A transition kernel is a function $K:X \times \Sigma_{Y} \mapsto [0,1]$ satisfying:
	- for each fixed $x \in X$, the mapping $A \mapsto K(x,A)$ is a probability [[Measure]] on $Y$
	- for each fixed [[Measurability|measurable]] set $A \in \Sigma_{Y}$, the mapping $x \mapsto K(x,A)$ is measurable
- Sometimes transition kernels are written as their transition densities together with their integral measure as $K_{t}(x,dy)=p_{t}(x,y)m(dy)$

## Intuition (optional)
- We can see $X$ as the set of current states
- $A \subseteq X$ is the set of possible next states
- mapping $K$ is a function from current states to probability measures

- We like transition kernels to be measurable in its first argument s.t. the following function is measurable as well $$Tf(x)=\int f(y)K(x,dy)$$
	These functions are needed in defining and results of
	- Expectations of functions of a random variable
	- [[Markov semi-group]]/[[Semigroup]]
	- [[Resolvant]]
	- [[Generator]] 
	- [[Dirichlet form representation]]
	

## Examples
- Markov transition matrix
- [[Brownian motion]] kernel:
	- For a brownian motion in $\mathbb{R}^n$ we have $$K_{t}(x,dy)=p_{t}(x,y)dy,$$
		where $p_{t}(x,y)$ is the [[Heat kernel]] 
	- $\forall x \in X$ fixed:
		- $A \mapsto K_{t}$ is a probability density / transition density
		- for each fixed [[Borel set]] $A$ , the mapping $x \mapsto K_{t}(x,A)$ is [[Measurability|measurable]] 

## Equivalent Formulations (optional)


## Related Concepts

