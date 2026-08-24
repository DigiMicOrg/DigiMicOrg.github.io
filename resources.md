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
    <p>The tested Python implementation, with core MiCRM simulation,
    temperature scaling, spatial coupling, examples, and a Jupyter Book.</p>
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

  <article class="gateway-card" id="tpcp">
    <span class="status-pill">Separate package · migration planned</span>
    <h3>TPC Prediction Package (TPCP)</h3>
    <p>A separate sequence-informed package for predicting microbial growth
    temperature-performance curves. Its package manual will live with its own
    source when the repository is brought under DigiMicOrg.</p>
  </article>
</div>

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
