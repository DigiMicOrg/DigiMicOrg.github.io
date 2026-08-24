---
layout: page
title: Resource-processing flux
permalink: /workflows/resource-flux/
description: Quantify uptake, retention, leakage, and maintenance in MiCRM communities.
math: true
---

Resource-processing fluxes connect consumer-resource simulations to measured
functions such as carbon retention, respiration, resource depletion, and
cross-feeding.

## Flux definitions

At consumer biomass $C_i$ and resource state $R_\alpha$, gross uptake is:

$$
F^{\mathrm{uptake}}_{i\alpha}=C_i u_{i\alpha}R_\alpha.
$$

With retained fraction
$\eta_{i\alpha}=1-\sum_\beta l_{i\alpha\beta}$, retained and leaked fluxes are:

$$
F^{\mathrm{retained}}_{i\alpha}
=C_i u_{i\alpha}R_\alpha\eta_{i\alpha},
$$

$$
F^{\mathrm{leak}}_{i\alpha\beta}
=C_i u_{i\alpha}R_\alpha l_{i\alpha\beta}.
$$

Maintenance loss is $F_i^{\mathrm{maintenance}}=m_iC_i$.

## Resource and community balance

For constant supply $\rho_\alpha$ and linear loss $\omega_\alpha R_\alpha$:

$$
\frac{dR_\alpha}{dt}=\rho_\alpha-\omega_\alpha R_\alpha
-\sum_iF^{\mathrm{uptake}}_{i\alpha}
+\sum_i\sum_\beta F^{\mathrm{leak}}_{i\beta\alpha}.
$$

At a numerical equilibrium, the residual of this balance should be small. Large
residuals indicate that the endpoint is not stationary or that the flux
calculation does not match the model's supply and loss conventions.

Community totals are obtained by summing the relevant consumer and resource
axes. A direct flux-based efficiency is:

$$
E_{\mathrm{direct}}=
\frac{F^{\mathrm{retained}}_{\mathrm{comm}}}
{F^{\mathrm{uptake}}_{\mathrm{comm}}}.
$$

For comparisons across communities, use the same declared reference resource
state and the
[carbon-use-efficiency workflow]({{ '/workflows/carbon-use-efficiency/' | relative_url }}).

Report total uptake, retained flux, leakage, maintenance or net growth,
resource drawdown, the evaluation state, and the model's resource-supply form.

## Implementation status

DigiMicPy exposes the state and parameter arrays needed to calculate these
quantities explicitly. See its
[resource-flux recipe](https://digimic.org/DigiMicPy/content/resource_flux.html).

[Back to all workflows]({{ '/workflows/' | relative_url }})
