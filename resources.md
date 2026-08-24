---
layout: page
title: Resources
permalink: /resources/
description: DigiMic packages, documentation, research workflows, and training materials.
---

DigiMic is a gateway to independently maintained modelling packages and the
resources around them. Package documentation is versioned and validated in the
repository that owns each implementation.

## Packages and documentation

<div class="gateway-grid resource-grid">
  <article class="gateway-card gateway-card-featured">
    <span class="status-pill">Python 3.11+</span>
    <h3>DigiMicPy</h3>
    <p>The Python implementation, with validated MiCRM parameters, reproducible
    parameter generators, consumer-resource simulation, examples, and a
    package-owned Jupyter Book.</p>
    <div class="card-links">
      <a href="{{ site.digimicpy_docs_url }}/">Read the documentation <span aria-hidden="true">→</span></a>
      <a href="https://github.com/DigiMicOrg/DigiMicPy">Browse the source <span aria-hidden="true">↗</span></a>
    </div>
  </article>

  <article class="gateway-card">
    <span class="status-pill">Julia 1.8+</span>
    <h3>DigiMic.jl</h3>
    <p>The Julia implementation, distributed from source and imported as
    <code>MiCRM</code> for compatibility with existing users.</p>
    <div class="card-links">
      <a href="https://github.com/DigiMicOrg/DigiMic">Setup and source <span aria-hidden="true">↗</span></a>
    </div>
  </article>

  <article class="gateway-card gateway-card-wide parameterisation-card" id="tpcp">
    <span class="status-pill">Incoming package · GEM → CRM</span>
    <h3>TPCP: GEM-based CRM parameterisation</h3>
    <p>TPCP is a separate, general-purpose parameterisation package under
    development. It will translate genome-scale metabolic models (GEMs) and
    supporting biological or environmental information into parameters for
    consumer-resource models (CRMs) used by DigiMicPy or DigiMic.jl.</p>
    <p>Temperature-aware growth and metabolic responses are a key application,
    not the package's only focus. Its wider scope includes resource uptake,
    secretion and leakage, biomass production, maintenance, and medium
    constraints. The package manual will live with its own source when the
    repository is brought under DigiMicOrg.</p>
  </article>
</div>

The [documentation ownership policy]({{ '/documentation/' | relative_url }})
defines the boundary between this platform and package-owned implementation
documentation.

## Workflows

The platform owns the scientific definitions, assumptions, interpretation, and
reporting guidance for workflows that may span more than one implementation.
Package documentation explains how to carry them out with a supported API.

- [Community coalescence]({{ '/workflows/coalescence/' | relative_url }})
- [Carbon-use efficiency]({{ '/workflows/carbon-use-efficiency/' | relative_url }})
- [Resource-processing flux]({{ '/workflows/resource-flux/' | relative_url }})
- [Effective GLV reduction]({{ '/workflows/effective-glv/' | relative_url }})
- [Stability and feasibility]({{ '/workflows/stability/' | relative_url }})
- [Temperature scaling]({{ '/workflows/temperature/' | relative_url }})
- [Spatial coupling (integration documentation)](https://github.com/DigiMicOrg/DigiMicPy/blob/docs/package-api/docs/content/spatial.md)

## Training and support

- [Installation and first simulation]({{ site.digimicpy_docs_url }}/content/useinfo.html)
- [Model theory]({{ site.digimicpy_docs_url }}/content/theo.html)
- [Python API reference (integration documentation)](https://github.com/DigiMicOrg/DigiMicPy/blob/docs/package-api/docs/content/api.md)
- [Examples in the DigiMicPy repository](https://github.com/DigiMicOrg/DigiMicPy/tree/main/examples)
- [Questions and feature requests](https://github.com/DigiMicOrg/DigiMicPy/issues)
- [Platform support, funding, and contact]({{ '/support/' | relative_url }})

The packages are early-stage research software. Check each repository's README
and release history before depending on an API for a long-lived workflow.
