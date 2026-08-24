---
layout: page
title: Effective GLV reduction
permalink: /workflows/effective-glv/
description: Reduce a MiCRM locally to effective species interactions.
math: true
---

A microbial consumer-resource model (MiCRM) tracks consumers and resources
explicitly. An effective generalised Lotka-Volterra (eGLV) reduction instead
summarises the local effects that consumers have on one another through their
shared resource environment.

The reduction is not a replacement for the MiCRM. It is tied to a specified
equilibrium and is reliable only for perturbations over which the local
linearisation remains informative.

## Species-only form

$$
\frac{dC_i}{dt}=C_i\left(r_i+\sum_j\alpha_{ij}C_j\right).
$$

Here $\alpha_{ij}$ is the effect of consumer $j$ on consumer $i$. Negative
values indicate local suppression; positive values indicate local facilitation.

For a MiCRM retained fraction
$\eta_{i\alpha}=1-\sum_\beta l_{i\alpha\beta}$, per-capita growth through
resources is:

$$
g_i(R)=\sum_\alpha u_{i\alpha}\eta_{i\alpha}R_\alpha.
$$

## Eliminate resources locally

Let $(\hat C,\hat R)$ be a verified MiCRM equilibrium and write the resource
equations as $dR/dt=F(R,C)$. The implicit function theorem gives:

$$
\frac{\partial\hat R}{\partial C}
=-\left(\frac{\partial F}{\partial R}\right)^{-1}
\frac{\partial F}{\partial C}.
$$

The local interaction matrix is then:

$$
\alpha_{ij}=\sum_\alpha u_{i\alpha}\eta_{i\alpha}
\frac{\partial\hat R_\alpha}{\partial C_j}.
$$

Choose $r$ so the reduced system shares the reference equilibrium:

$$
r_i=g_i(\hat R)-m_i-\sum_j\alpha_{ij}\hat C_j.
$$

## Workflow and interpretation

1. Simulate the MiCRM and verify the derivative norm at the endpoint.
2. Select the full or surviving consumer subsystem and record the threshold.
3. Construct the resource and consumer Jacobian blocks at the equilibrium.
4. Solve the linear system for $\partial\hat R/\partial C$; avoid forming a
   matrix inverse explicitly.
5. Calculate $\alpha$ and $r$.
6. Compare MiCRM and eGLV responses to small perturbations around the reference
   state.

Rows of $\alpha$ identify affected consumers and columns identify the consumers
causing the local effect. The result depends on the equilibrium, resource
dynamics, leakage structure, and subsystem retained for analysis.

## Implementation status

Automatic MiCRM-to-eGLV conversion is not currently part of DigiMicPy's public
API. The platform therefore owns this scientific workflow; package
documentation should link here until an implementation can be tested and
versioned.

[Continue to stability and feasibility]({{ '/workflows/stability/' | relative_url }})
