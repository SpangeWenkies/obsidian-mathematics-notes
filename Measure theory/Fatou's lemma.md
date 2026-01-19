
# Lemma: Fatou's lemma

**Type:** #lemma  

## Statement
- Let $f_{n}\geq0$ be a non-negative [[Measurable function]] $$\implies \int \varliminf_{n \to \infty}f_{n} d\mu \leq \varliminf_{n \to \infty}\int f_{n}d\mu,$$ where $\varliminf$ is the [[Limit inferior]] 
- This is because of the [[Lower semi-continuity property]] of the integral

## Graphically
- the limit inferior catches the eventually lowest values, integrating these can not exceed the limit inferior of the integrals. See the difference in bottom right between the graph edges
![[Fatou's lemma liminf.png]]

## Proof (optional)

## Intuition
- Looking at the limit inferior inside the integral gives a value smaller than or equal to the limit inferior of the integrals
- Weaker than MCT and DCT, but thus requires fewer assumptions on the measurable function

## Used In
- [[Lebesgue integration]]
- Proof of MCT and DCT
- Showing [[Semi-continuity]] of the [[Dirichlet form]]
- Establishing existence of [[Minimizer|minimizers]] 
- [[Potential]] theory
- [[Capacity]] estimates

## Related
- [[Monotone convergence theorem]]
- [[Dominated convergence theorem]] 
