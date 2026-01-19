
# Definition: Polish space

**Type:** #definition  

## Definition
- A space is a Polish space if it is a [[Separability|separable]] completely metrizable [[Topological space]], i.e., a space that is [[Homeomorphic]] to a [[Completeness|complete]] [[Metric space]] that contains a [[Countability|countable]] [[Denseness|dense]] subset.

## Intuition (optional)
Polish spaces are the spaces where both **topology** and **measure theory** behave extremely well:
- they are “nice enough” to support probability theory, [[Borel measure|Borel measures]], [[Kernel||kernels]], [[Disintegration]], etc.,
- but much more general than [[Euclidean space|euclidean spaces]].

A Polish space is:
- large enough to include infinite-dimensional examples, but
- structured enough that [[Borel set|Borel sets]] enjoy powerful [[Regular conditional probability|regularity]] properties.

Many deep theorems in probability and descriptive set theory **require Polish spaces** because they guarantee:
- good [[Measurable selection|measurable selection]] results,
- existence/regularity of conditional probabilities,
- topological regularity of Borel sets,
- [[Canonical representation|canonical representations]] via [[Standard Borel space|standard Borel spaces]].

## Equivalent Formulations (optional)
- A general version of a Polish space is a [[Radon space]]

- A space $X$ is a Polish space iff any of the following hold:
	- There exists a [[Metric|metric]] $d$ on $X$ that induces the [[Topology]] and makes the topological space $(X,d)$ a complete seperable metric space
	- $X$ is homeomorphic to a [[G-delta]] $G_{\delta}$ subset of some [[Compactness|compact]] metric space
	- $X$ is homeomorphic to a Borel subset of a [[Hilbert cube]] $[0,1]^{\mathbb{N}}$ 
	- $X$ is a standard Borel space equipped with a topology that makes it completely metrizable
## Properties
- Standard Borel structure arises from polish spaces
- [[Markov kernel|Markov kernels]] on Polish spaces are [[Measurability|measurable]] in both arguments.
- They produce nice [[Borel algebra]] needed for most results in [[Dirichlet form|Dirichlet forms]], [[Resolvant|resolvents]] and kernels
- [[Hunt process|Hunt processes]] and [[General Markov process|general Markov processes]] behave best on Polish spaces (or [[Lusin space|Lusin spaces]])

- Between any two uncountable Polish spaces there is Borel [[Isomorphism]], s.s., every uncountable Polish space has the [[Cardinality of the continuum]] 
## Examples
- $\mathbb{R}^{n}$
- Any separable [[Banach space]] with its [[Norm topology]]
- [[Countability|Countable]] [[Discrete space|discrete spaces]] 
- [[Cantor set]] 

## Non-examples
- Uncountable discrete spaces
- A complete metric space with no countable dense subset

## Related Concepts


