---
layout: page
title: Project overview
permalink: /about/
---

**DigiMic (Digital Microbiome)** is an open modelling framework for exploring
how microbial communities assemble, respond to environmental change, and
process carbon. It connects mechanistic models of microbial metabolism with
community dynamics and, ultimately, observations from laboratory and natural
ecosystems.

## Why model resources?

Microbes do not interact in isolation. They consume shared resources, retain
some of that material for growth, and release metabolic by-products that other
organisms may use. These flows create competition when organisms require the
same resources and cross-feeding when the products of one organism support
another.

DigiMic represents these processes with microbial consumer-resource models
(MiCRMs). Uptake parameters describe resource consumption, leakage parameters
describe the release of metabolic by-products, and retained uptake contributes
to growth. Resource supply, environmental loss, and microbial mortality
complete the community dynamics. This mechanistic structure lets researchers
ask how traits, metabolism, and environmental conditions shape whole-community
behaviour.

[![Conceptual DigiMic workflow linking metabolic parameterisation, predictive microbiome modelling, and validation against laboratory and real-world microbiome data.]({{ '/assets/img/digimic-workflow.jpg' | relative_url }}){: width="1800" height="1045" loading="lazy" }]({{ '/assets/img/digimic-workflow.jpg' | relative_url }}){: aria-label="Open the DigiMic workflow figure at full size" }

*The DigiMic vision connects metabolic parameterisation to predictive community
models and validation against laboratory and field observations. Metabolic-model
interfaces and automated omics-based parameterisation are development goals
rather than current package features.*

## From omics to community dynamics

The long-term DigiMic workflow connects three layers:

1. **Metabolic parameterisation:** use strain-level measurements, traits, taxonomic information, omics data, and genome-scale metabolic models to derive biologically grounded uptake, secretion, and biomass-production parameters.
2. **Microbiome modelling:** use those parameters in consumer-resource models to predict changes in community composition, resource chemistry, and carbon processing under different environmental conditions.
3. **Data and validation:** compare predictions with laboratory experiments and observations from real microbial communities, then use discrepancies to refine model assumptions and parameterisation.

The modelling layer is available today. Current simulations use synthetic
parameter generators or parameters supplied by the researcher. TPCP is being
developed as a separate, general parameterisation package to translate
genome-scale metabolic models (GEMs) and supporting biological or environmental
information into consumer-resource model parameters usable by either DigiMicPy
or DigiMic.jl. Temperature-aware parameterisation is a key application within
that broader GEM-to-CRM bridge, rather than its sole purpose.

## What is available today?

DigiMic currently has independent Python and Julia implementations that share
scientific aims. Numerical and API parity between them has not been established.

### DigiMicPy

The tested Python package supports:

- synthetic microbial communities with modular resource preferences;
- simulation of consumer and resource trajectories;
- configurable uptake, leakage, mortality, resource supply, and loss.

Fixed-temperature scaling and conservative spatial coupling are under active
integration. Package documentation records which capabilities are present in
the version or branch being used.

The platform documentation defines shared workflows for community coalescence,
carbon-use efficiency, resource-flux summaries, effective generalised
Lotka-Volterra reductions, and stability analysis. Package documentation records
which parts have a supported implementation.

[Read the DigiMicPy documentation]({{ site.digimicpy_docs_url }}/){: .button .button-primary }
[View the Python source](https://github.com/DigiMicOrg/DigiMicPy){: .button .button-secondary }
[Explore shared workflows]({{ '/workflows/' | relative_url }}){: .button .button-secondary }

### DigiMic.jl

The Julia implementation provides parameter generation, SciML-based
consumer-resource simulations, local stability analysis, and experimental
stressor utilities. The repository is branded DigiMic.jl, while the package
name used in Julia imports (`using MiCRM`) and its UUID remain `MiCRM` for
compatibility with existing users.

[Explore DigiMic.jl](https://github.com/DigiMicOrg/DigiMic){: .button .button-secondary }

## An open framework

DigiMic is intended as a transparent foundation for collaboration across
microbiology, ecology, metabolic modelling, bioinformatics, and environmental
science. Planned extensions include metabolic-model interfaces, new
parameterisation methods, inference tools, experimental-design workflows, and
validation against measurements of community composition, resource chemistry,
and carbon fluxes.

Contributions can take the form of code, independently developed extensions,
examples, datasets, or feature requests motivated by concrete research
questions. The project will keep implemented capabilities and research
directions clearly distinguished as the framework develops.
