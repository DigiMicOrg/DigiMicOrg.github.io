---
layout: page
title: Temperature scaling
permalink: /workflows/temperature/
description: Shared assumptions and reporting guidance for temperature-dependent microbial models.
math: true
---

Temperature can affect microbial uptake, maintenance, leakage, resource supply,
and resource loss. A temperature-aware workflow must say which traits respond,
which response curve and units are used, and whether temperature is fixed or
changes during a simulation.

## Define the thermal response

A common trait response combines Boltzmann-Arrhenius activation with
high-temperature deactivation:

$$
B(T)=B_0
\frac{
\exp\left[-\frac{E}{k_B}\left(\frac{1}{T}-\frac{1}{T_{\mathrm{ref}}}\right)\right]
}{
1 + \frac{E}{E_D-E}
\exp\left[\frac{E_D}{k_B}\left(\frac{1}{T_{\mathrm{pk}}}-\frac{1}{T}\right)\right]
}.
$$

Record the interpretation and units of every term:

| Symbol | Meaning |
|---|---|
| $T$ | Evaluation temperature, normally kelvin |
| $T_{\mathrm{ref}}$ | Reference temperature |
| $T_{\mathrm{pk}}$ | Temperature of peak performance |
| $B_0$ | Trait normalisation at the chosen reference scale |
| $E$ | Activation energy |
| $E_D$ | High-temperature deactivation energy |
| $k_B$ | Boltzmann constant in units consistent with the energies |

Do not mix Celsius inputs with a Boltzmann constant that assumes absolute
temperature. Fit or justify trait-specific parameters and avoid extrapolating
beyond the observed temperature range.

## Map temperature to the model

State exactly which parameter families change. Possibilities include uptake
$u_{i\alpha}(T)$, maintenance $m_i(T)$, leakage
$l_{i\alpha\beta}(T)$, resource supply $\rho_\alpha(T)$, and resource loss
$\omega_\alpha(T)$. Scaling uptake and maintenance alone represents a different
biological hypothesis from allowing carbon-use efficiency or environmental
supply to change as well.

For comparisons between fixed temperatures, generate the structural community
once and change only the declared thermal traits. This separates physiological
effects from stochastic differences in community construction.

## Distinguish temperature regimes

For fixed temperature, construct one parameter set for each temperature and run
the autonomous model. For a step, seasonal cycle, heatwave, or empirical time
series, the differential equation is non-autonomous: temperature and all
dependent traits must be evaluated at the solver time.

Do not approximate a time-varying regime by a fixed-temperature helper unless
that approximation is part of the stated experimental design.

## Validate and report

Report at least:

- temperature units, range, reference temperature, and regime;
- response-curve equation, parameter values, and evidence or fitting method;
- every model parameter that changes with temperature;
- whether structural parameters and initial conditions are held constant;
- numerical method, tolerances, and endpoint or equilibrium checks; and
- whether results represent acute physiology, adaptation, or species sorting.

Inspect trait curves across the complete simulated range before integrating.
Compare fixed-temperature cases before adding temporal variation, and test
sensitivity to thermal parameters and solver tolerances.

## Package implementations

Package documentation owns the supported functions and executable instructions
for a particular version. Check the
[DigiMicPy documentation]({{ site.digimicpy_docs_url }}/) and
[DigiMic.jl repository](https://github.com/DigiMicOrg/DigiMic) before assuming
that a thermal workflow is implemented or behaves identically across languages.

[Back to all workflows]({{ '/workflows/' | relative_url }})
