
# Theorem: Lebesgue integration

**Type:** #theorem  

## Statement
- Classical [[Riemann integration]] has its limitations, it can not handle:
	- Functions with many [[Discontinuity|discontinuities]] 
	- Thin or badly shaped sets
	- Function [[Limit|limits]] 

- Lebesgue's idea:
	- Instead of slicing the [[Domain]] of a function into intervals, slice the [[Range]] of the functions into horizontal strips

- To Lebesgue integrate we need to integrate to a [[Lebesgue measure]] instead of the normal Riemann-style dx

- Lebesgue integration refers to integration with respect to a measure in general, not necessarily just the Lebesgue measure

- How would we get the [[Lebesgue sigma algebra]] to which the Lebesgue measure is defined?
	- First look at simple geometric objects like
		- intervals $(a,b)$
		- rectangles
		- boxes in $\mathbb{R}^n$
		$\implies$ we assign these the usual volumes
	- Extend these volume assignments to the smallest [[Sigma algebra]] containing these sets to get the [[Borel algebra]]
	- Now for integration we need to have the limits of measurable sets themselves be measurable, so we extend beyond [[Borel set|Borel sets]] to get [[Lebesgue measure|Lebesgue measurable]]
		- To do this we must complete the [[Borel measure]] to get $$\text{Lebesgue measurable sets = Borel sets + all subsets of null sets}$$
		- Now these Lebesgue measurable sets give us the Lebesgue $\sigma$-algebra
		$\impliedby$ This extension is done by the [[Carathéodory extension theorem]]

- The role of a Lebesgue measure in the integration:
	- During Riemann integration we had that $\int^{b}_{a}f(x)dx \approx \sum f(x_{i})\Delta x_{i}$ 
	- Now we look at all points where a function takes certain values like
		- e.g. the horizontal slice $A_{t}=\{ x \in \mathbb{R}:f(x)>t \}$ and look at all $A_{t}\subseteq \mathbb{R}$
	- To integrate using these slices we must know their "size", which is their Lebesgue measure denoted by $m$

- What the integration then looks like:
	- first look at the [[Simple function]] their Lebesgue integration
		- $s(x)=\sum^{n}_{i=1}a_{i}1_{A_{i}}(x)$, where $A_{i}$ is an arbitrary [[Measurability|measurable]] set related to $a_{i}$
		- Then Lebesgue integral becomes $$\int s \text{ }dm =\sum^{n}_{i=1}a_{i}m(A_{i})$$
	- now look at integration of non-negative [[Measurable function|measurable functions]] $f\geq0$ $$\int f\text{ }dm=\sup\left\{  \int s \text{ }dm : 0\leq s\leq f  \right\}$$
	- now look at general measurable functions
		- we can write $f = f^{+} - f^{-}$, where these two are non-negative functions and then define $$\int f\text{ }dm = \int f^{+}\text{ }dm = \int f^{-} dm$$
		and evaluate the two terms the non-negative measurable functions way.

## Consequences / properties
- It makes us able to measure "sizes" ([[Lebesgue measure]]) of function range defined sets, e.g., $\left\{  x:f(x) > \frac{1}{2}  \right\}$ , when Riemann integrals could not do so.
- Lebesgue measures make statements like [[almost everywhere]] (a.e.) and [[Measure zero]] more precise.
- Lebesgue integration makes us able to integrate a broader class of functions, e.g.:
	- indicator of a [[Fractal set]]
	- functions with [[Denseness|dense]] discontinuities
	- [[Characteristic function|characteristic functions]]  of "weird" sets of [[Measure zero]]

- Lebesgue integration has the [[Lebesgue identity]], which gives that the vertical area is actually equal to the sum over the horizontal slices

- Lebesgue integration satisfies convergence theorems/lemma's that are not true for Riemann integrals:
	- [[Monotone convergence theorem]] (MCT)
	- [[Dominated convergence theorem]] (DCT)
	- [[Fatou's lemma]] 
	These are essential to [[Markov process|Markov processes]] and [[functional analysis]]

- Due to [[Invariance]] of the Lebesgue measure, i.e., $m(A+x) = m(A)$, we see intuition lines up when using Lebesgue integration for things like [[Energy form|energy forms]] their [[Partial differential equation|PDE's]] , as indeed energy should be independent of some coordinate system
- [[Heat kernel|Heat kernels]], [[Laplacian|Laplacians]], [[Brownian motion|Brownian motions]] all make use of this invariance property aswell
## Related Definitions

