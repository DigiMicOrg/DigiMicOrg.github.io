---
layout: page
title: Carbon-use efficiency
permalink: /workflows/carbon-use-efficiency/
description: Species-level and community-level carbon-use efficiency in DigiMic workflows.
math: true
---

Carbon-use efficiency (CUE) measures how much consumed carbon is retained for
biomass production rather than leaked, respired, or otherwise unavailable for
growth. A DigiMic analysis should distinguish an individual consumer's
efficiency from a community summary.

## Species-level efficiency

For consumer $i$ taking up resource $\alpha$, define the retained fraction:

$$
\eta_{i\alpha}=1-\sum_\beta l_{i\alpha\beta}.
$$

For a declared reference environment $R^0$, potential uptake and retained flux
are:

$$
U_i^0=\sum_\alpha u_{i\alpha}R_\alpha^0,\qquad
G_i^0=\sum_\alpha u_{i\alpha}\eta_{i\alpha}R_\alpha^0.
$$

Gross and maintenance-adjusted forms are:

$$
\epsilon_i^{\mathrm{gross}}=\frac{G_i^0}{U_i^0},\qquad
\epsilon_i^{\mathrm{net}}=\frac{G_i^0-m_i}{U_i^0}.
$$

State which form is used and how zero or negligible uptake is handled.

## Community summaries

A biomass-weighted mean describes the efficiency of abundant surviving taxa:

$$
E_{\mathrm{biomass}}=
\frac{\sum_i C_i^*\epsilon_i}{\sum_i C_i^*}.
$$

A flux-weighted mean emphasizes consumers that process more resources:

$$
E_{\mathrm{flux}}=
\frac{\sum_i C_i^*U_i^0\epsilon_i}{\sum_i C_i^*U_i^0}.
$$

These answer different questions and should not be reported interchangeably.
The first is a community-trait summary; the second is closer to retained carbon
per unit of potential consumption.

## Choose the reference environment

Using a common $R^0$ prevents the efficiency metric from being defined by the
post-assembly outcome it is intended to explain. Suitable choices include the
initial medium, a chemostat carrying-capacity vector, a mean environment across
scenarios, or a measured experimental medium. Use the same reference when
comparing communities.

Report the reference resources, gross or net convention, extinction threshold,
weighting method, and treatment of near-zero denominators.

## Implementation status

DigiMicPy exposes the uptake, leakage, mortality, and equilibrium arrays needed
for these calculations but has no dedicated CUE helper. Its
[package recipe]({{ site.digimicpy_docs_url }}/content/cue.html) shows the
current NumPy calculation.

[Back to all workflows]({{ '/workflows/' | relative_url }})
