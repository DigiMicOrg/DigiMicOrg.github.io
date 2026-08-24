---
layout: page
title: Stability and feasibility
permalink: /workflows/stability/
description: Analyse local stability, reactivity, and feasibility in full and reduced community models.
math: true
---

Stability analysis asks whether a small perturbation decays back toward a
reference equilibrium. DigiMic distinguishes the full consumer-resource system
from a local species-only effective GLV reduction.

## Verify the reference state

For $x^*=[C^*,R^*]^T$, require a derivative residual appropriate to the model's
units and numerical tolerances:

$$
\max_k\left|\frac{dx_k}{dt}\right|<\epsilon.
$$

Report $\epsilon$, the integration interval, solver tolerances, and the
extinction threshold used to select surviving consumers.

## Full MiCRM stability

The full Jacobian has consumer and resource blocks:

$$
J=\begin{bmatrix}J_{CC}&J_{CR}\\J_{RC}&J_{RR}\end{bmatrix}.
$$

For retained fraction
$\eta_{i\alpha}=1-\sum_\beta l_{i\alpha\beta}$, common MiCRM terms include:

$$
(J_{CR})_{i\alpha}=C_i^*u_{i\alpha}\eta_{i\alpha},
$$

$$
(J_{RC})_{\alpha i}=-u_{i\alpha}R_\alpha^*
+\sum_\beta u_{i\beta}R_\beta^*l_{i\beta\alpha}.
$$

The remaining terms depend on the exact consumer growth, resource supply, and
loss equations. Derive or differentiate the implemented right-hand side rather
than substituting a Jacobian from a different MiCRM convention.

The equilibrium is locally stable when:

$$
\max_k\operatorname{Re}(\lambda_k(J))<0.
$$

Reactivity measures possible initial amplification using the symmetric part
$H=(J+J^T)/2$. A positive leading eigenvalue of $H$ means that some perturbation
directions initially grow even if the equilibrium is asymptotically stable.

## Effective GLV stability

For the [effective GLV reduction]({{ '/workflows/effective-glv/' | relative_url }}),
the surviving-species Jacobian at equilibrium is:

$$
J^{\mathrm{GLV}}=\operatorname{diag}(C^*)\alpha.
$$

Apply the same leading-real-eigenvalue criterion. Agreement with the full MiCRM
is not guaranteed outside the local regime used to construct the reduction.

A feasible GLV equilibrium has positive biomass for every included consumer:

$$
C^*=-\alpha^{-1}r,\qquad C_i^*>0\ \text{for all }i.
$$

Feasibility and stability answer different questions; report them separately.

## Recommended reporting

- equilibrium residual and survivor threshold;
- analytic, automatic-differentiation, or finite-difference Jacobian method;
- finite-difference step or differentiation settings where applicable;
- leading real eigenvalue and, when relevant, reactivity;
- full MiCRM or reduced subsystem dimensions; and
- comparison between full and reduced results only around the same equilibrium.

## Implementation status

DigiMicPy exposes a pure MiCRM right-hand side that can be differentiated
numerically, but it does not yet provide public Jacobian, eGLV, stability,
reactivity, or feasibility helpers. Its package documentation retains only the
Python-specific diagnostic recipe and links to this shared workflow.

[Back to all workflows]({{ '/workflows/' | relative_url }})
