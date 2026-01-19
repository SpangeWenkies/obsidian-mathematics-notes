
# Theorem: Dynkin's theorem

**Type:** #theorem  

## Statement
- If $\pi$ is some $\pi$-system, $\lambda$ is some $\lambda$-system and $\pi \subseteq \lambda$ then $$\sigma(\pi)\subseteq \lambda$$
- i.e., the smallest $\lambda$-system containing a $\pi$-system is a [[Sigma algebra]]

## Proof Idea (optional)


## Consequences / properties
- If we now want to prove properties requiring generation of a $\sigma$-algebra, we do the following:
	- Start with a $\pi$-system
	- consider all sets in that system satisfying the property to prove
	- Show these sets together form a $\lambda$-system
	- Dynkin's theorem give the collection of these sets contain the complete $\sigma$-algebra, so the property also holds for the $\sigma$-algebra, being a subset of the $\lambda$-system

## Examples
- e.g., showing uniqueness of a [[Measure]] on $X$:
	- Suppose $\mu$ and $\nu$ are probability measures s.t. $\mu(A)=\nu(A), \forall A\in \pi$
	- Define $\mathcal{D}=\{ A:\mu(A)=\nu(A) \}$
	- We can check that $\mathcal{D}$ is a $\lambda$-system, as
		- $X \in\mathcal{D}$
		- it is closed under complements
		- it is closed under disjoint countable unions
	- Now as $\pi \subseteq \mathcal{D}$ and $\pi$ is by assumption a. $\pi$-system we get
		$\implies$ $\sigma(\pi)\subseteq\mathcal{D}$
			$\implies$ the measures are equal on the complete $\sigma$-algebra, as measures are uniquely determined by their values on a $\pi$-system

- More results from Dynkin's theorem:
	- [[Measurability]] of a [[Kernel]]
		- if measurability holds for a generating $\pi$-system it holds everywhere
	- uniqueness of a [[Transition kernel]]
		- a kernel is uniquely determined by its values on a $\pi$-system
	- uniqueness of [[Resolvant]] and of [[Markov semi-group]]/[[Semigroup]]
		- if their equations hold for [[Generator||generators]] on a $\pi$-system, then they hold for all measurable sets
	- construction of [[Product sigma algebra]] 
		- Rectangles $A\times B$ form a $\pi$-system, and the $\sigma$-algebra they generate is a [[Borel algebra]]
## Related Definitions
- [[π-system]]
- [[λ-system]]
- 
