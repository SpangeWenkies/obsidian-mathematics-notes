
# Definition: Lebesgue measure

**Type:** #definition  

## Definition
- A standard way of assigning a [[measure]] to subsets of higher dimension [[Euclidean space|Euclidean spaces]] 
	- for $n=1,2,3$ it corresponds to the length, area and volume of a space
	- Often denoted by $\lambda$

- If a set $A$ can be assigned a Lebesgue measure, then it is Lebesgue measurable and we get $\lambda(A)$ as the Lebesgue measure

- It is used for defining [[Lebesgue integration]] 

- First for $n=1$, take any interval $I=[a,b]$ or $I=(a,b)$ in $\mathbb{R}$, let $l(I)=b-a$ be its length
	Then for any subset $E \subseteq \mathbb{R}$, the Lebesgue [[Outer measure]] denoted as $\lambda^{*}(E)$ is defined as the following [[Infimum]]: $$\lambda^{*}(E)= \inf \left\{  \sum^{\infty}_{k=1} l(I_{k}): (I_{k})_{k \in \mathbb{N}} \text{ is a sequence of open intervals with }E \subset \bigcup^{\infty}_{k=1}I_{k} \right\}$$

- Now generalised to n dimensions, take any rectangular [[cuboid]] $C$ as the Cartesian product of [[Openness|open]] intervals defined as $C=I_{1}\times\dots \times I_{n}$ and $\text{vol}(C)= l(I_{1})\times\dots \times l(I_{n})$ as its volume.
	$\forall E \subseteq \mathbb{R}^n$: $$\lambda^{*}(E)= \inf \left\{  \sum^{\infty}_{k=1} \text{vol}(C_{k}): (C_{k})_{k \in \mathbb{N}} \text{ is a sequence of products of open intervals with }E \subset \bigcup^{\infty}_{k=1}C_{k} \right\}$$

- Set $E$ satisfies the [[Carathéodory criterion]] whenever,  $\forall A \subseteq \mathbb{R}^n$, we have that $$\lambda^{*}(A)= \lambda^{*}(A \cap E) + \lambda^{*}(A \cap E^C)$$
	The sets $E$ are then always Lebesgue-[[Measurability|measurable]] 
		The set of all of such $E$ forms a [[Sigma algebra]]
	The Lebesgue measure of such a set $E$ then equals its Lebesgue [[Outer measure]], i.e., $$\lambda(E)=\lambda^{*}(E)$$

## Intuition (optional)
- It is the universal "background" measure for real analysis

## Equivalent Formulations (optional)


## Related Concepts

