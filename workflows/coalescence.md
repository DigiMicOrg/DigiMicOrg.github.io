---
layout: page
title: Community coalescence
permalink: /workflows/coalescence/
description: A shared workflow for combining assembled microbial communities.
math: true
---

Community coalescence asks what happens when two previously assembled
microbiomes enter a shared environment. In a microbial consumer-resource model
(MiCRM), the workflow combines their consumers and resource-processing traits,
then measures the composition and function of the resulting community.

Use coalescence experiments to ask whether one parent dominates, whether
resource complementarity supports coexistence, and how competition,
cross-feeding, carbon-use efficiency, or stability change after mixing.

## Define the parental systems

For parent communities 1 and 2, record their consumer sets, ordered resource
sets, uptake matrices $u$, leakage tensors $l$, mortality vectors $m$, supply
and loss terms, and equilibrium states $(\hat C, \hat R)$. Do not merge systems
until each parental endpoint has passed the chosen equilibrium diagnostic.

If both parents use the same ordered resources, stack consumer-specific
parameters:

$$
u^{(3)} = \begin{bmatrix}u^{(1)} \\ u^{(2)}\end{bmatrix},\qquad
l^{(3)} = \begin{bmatrix}l^{(1)} \\ l^{(2)}\end{bmatrix},\qquad
m^{(3)} = \begin{bmatrix}m^{(1)} \\ m^{(2)}\end{bmatrix}.
$$

A common biomass initial condition is the concatenated parental equilibrium:

$$
C^{(3)}(0) = \begin{bmatrix}\hat C^{(1)} \\ \hat C^{(2)}\end{bmatrix}.
$$

Choose the initial resource state explicitly: a standard medium, one parent's
state, an average of both parents, or a measured post-mixing environment. This
choice changes the initial invasion conditions and must be reported.

## Reconcile resource identities

For partially overlapping resource sets, construct a union with stable resource
identifiers and embed both parents into that common ordering. Zero uptake for a
resource that a parent could not use before mixing; do not silently reinterpret
matrix columns by position.

The resource-overlap ratio is:

$$
\Omega_R = \frac{|R^{(1)} \cap R^{(2)}|}{|R^{(1)} \cup R^{(2)}|}.
$$

Higher overlap can increase direct competition. Lower overlap can support
complementarity when one parent's leaked products match the other's demand.

## Quantify mechanisms and outcomes

Uptake similarity provides a simple competition proxy:

$$
\mathrm{competition} = \frac{2}{N(N-1)}\sum_{i<j}
\frac{u_i\cdot u_j}{\lVert u_i\rVert\,\lVert u_j\rVert}.
$$

An uptake-weighted leakage profile is
$L^{\mathrm{eff}}_{i\beta}=\sum_\alpha u_{i\alpha}l_{i\alpha\beta}$.
Comparing this profile with other consumers' uptake identifies potential
cross-feeding, but it does not prove that the corresponding flux occurs in the
simulated resource state.

Report at least:

- the equilibrium and extinction criteria used for both parents and the merge;
- the initial post-mixing resource state and resource-identity mapping;
- survivors and biomass contribution from each parent;
- similarity of the merged community to each parent;
- residual resources or resource drawdown; and
- any competition, facilitation, carbon-use-efficiency, or stability metric.

## Implementation status

DigiMicPy can express this workflow by constructing a combined
`MiCRMParameters` object and calling its existing solver, but it does not yet
provide a dedicated coalescence helper. See the
[DigiMicPy package documentation]({{ site.digimicpy_docs_url }}/content/coalescence.html)
for the current Python recipe.

[Back to all workflows]({{ '/workflows/' | relative_url }})
