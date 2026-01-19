
# Theorem: Radon-Nikodym theorem

**Type:** #theorem  

## Statement
- When can we write some [[Measure]] as an integral against some other measure?

- Suppose you have measures $\nu$ and $\mu$ on the same [[Measurability|measurable]] space
- if $\nu$ lives in $\mu$ , i.e., $\nu(A)=0 \text{ whenever }\mu(A)=0$ 
	$\implies \exists f \text{ s.t. } \nu(A)=\int_{A}fd\mu$, where $f=\frac{d\nu}{d\mu}$

- here $f$ is the Radon-Nikodym derivative, which is like the density of $\nu$ w.r.t. $\mu$

- This theorem holds if $\nu$ is [[Absolute continuity|absolutely continuous]] to $\mu$
## Proof Idea (optional)


## Consequences / properties
- All [[Hilbert space]] have the Radon-Nikodym property
- If $\mu$ is a measure on $(X,\Sigma)$, then $B$ has the Radon-Nikodym property w.r.t. $\mu$ if for every [[Countability|countably]]-additive vector measure $\gamma$ on $(X,\Sigma)$ with values $B$, which is of [[Bounded variation]] and is of [[Absolute continuity]] w.r.t. $\mu$ , there is a $\mu$-integrable function $g:X \mapsto B$ s.t.$$\gamma(E)=\int_{E}gd\mu,\text{ }\forall \text{ measurable sets } E \in \Sigma$$
- The [[Banach space]] $B$ has the R-N property if $B$ has the R-N property w.r.t. every finite measure, or equivalently either of the following:
	- [[Totally bounded|bounded]] discrete-time [[Martingale|martingales]] in $B$ converge [[Almost surely]]
	- Functions of [[Bounded variation]] into $B$ are [[Differentiability|differentiable]] [[almost everywhere]] 
	- For every bounded subset $D \subseteq B, \exists f \in B^{*}, \delta \in \mathbb{R}^{+} \text{ s.t. }$ $$\{ x:f(x)+\delta > \sup f(D) \}\subseteq D \text{ has arbitrarily small diameter}$$
- $L^{\infty}(\Omega), L^{1}(\Omega)\text{ for } \Omega$ being an [[Openness|open]] bounded subset of $\mathbb{R}^{n}$ do **not** have the R-N property
- [[Reflexive space|Reflexive spaces]] have the R-N property, which include, s.s., [[Hilbert space]]
- R-N theorem is needed in stochastics for [[Girsanov's theorem]], [[Lévy measure|Lévy measures]] 
- [[Killing density|Killing densities]] in Dirichlet forms are R-N derivatives

## Related Definitions

