---
layout: home
title: Digital microbiome platform
description: The authoritative gateway to DigiMic packages, shared scientific workflows, and training resources.
---

<section class="hero" aria-labelledby="hero-title">
  <p class="eyebrow">The Digital Microbiome Platform</p>
  <h1 id="hero-title">Open tools and shared workflows for predictive microbiome science</h1>
  <p class="hero-lead">DigiMic is the authoritative gateway to microbial
  modelling packages, implementation-independent scientific workflows,
  training materials, and project support.</p>
  <div class="action-row">
    <a class="button button-primary" href="{{ '/resources/' | relative_url }}">Choose a package</a>
    <a class="button button-secondary" href="{{ '/workflows/' | relative_url }}">Explore workflows</a>
  </div>
</section>

<section class="section-block" aria-labelledby="packages-heading">
  <p class="eyebrow">Packages and tools</p>
  <h2 id="packages-heading">From biological parameterisation to community simulation</h2>
  <p class="section-intro">Choose a modelling implementation, or follow the
  emerging GEM-based parameterisation layer that will supply biologically
  grounded consumer-resource model parameters to either language.</p>

  <div class="gateway-grid">
    <article class="gateway-card gateway-card-featured">
      <span class="status-pill">Python 3.11+ · active development</span>
      <h3>DigiMicPy</h3>
      <p>Construct validated MiCRM parameters, generate reproducible synthetic
      communities, and simulate consumer-resource dynamics in Python.</p>
      <div class="card-links">
        <a href="{{ site.digimicpy_docs_url }}/">Package documentation <span aria-hidden="true">→</span></a>
        <a href="https://github.com/DigiMicOrg/DigiMicPy">Source code <span aria-hidden="true">↗</span></a>
      </div>
    </article>

    <article class="gateway-card">
      <span class="status-pill">Julia 1.8+ · early stage</span>
      <h3>DigiMic.jl</h3>
      <p>Generate model parameters, run SciML-based consumer-resource
      simulations, and explore analysis and environmental-stressor utilities.</p>
      <div class="card-links">
        <a href="https://github.com/DigiMicOrg/DigiMic">Source and setup <span aria-hidden="true">↗</span></a>
      </div>
    </article>

    <article class="gateway-card gateway-card-wide parameterisation-card">
      <span class="status-pill">Incoming package · GEM → CRM</span>
      <h3>TPCP: GEM-based CRM parameterisation</h3>
      <p>TPCP is being developed as a general parameterisation package that
      translates genome-scale metabolic models (GEMs) and supporting biological
      or environmental information into parameters for consumer-resource models
      (CRMs). Its outputs are intended for use with either DigiMicPy or
      DigiMic.jl.</p>
      <p>Temperature-aware growth and metabolic responses are a key use case,
      alongside parameterisation of resource uptake, secretion and leakage,
      biomass production, maintenance, and medium constraints.</p>
      <a class="text-link" href="{{ '/resources/' | relative_url }}#tpcp">TPCP migration status <span aria-hidden="true">→</span></a>
    </article>
  </div>
</section>

<section class="section-block documentation-boundary" aria-labelledby="documentation-heading">
  <p class="eyebrow">Documentation ownership</p>
  <h2 id="documentation-heading">Shared science here, implementation details with each package</h2>
  <p class="section-intro">This platform owns the project vision, shared
  scientific definitions, interpretation, reporting guidance, team, training
  directory, and support routes. Each package owns its installation, API,
  implemented equations, executable examples, and development documentation.</p>
  <a class="text-link" href="{{ '/documentation/' | relative_url }}">Read the documentation policy <span aria-hidden="true">→</span></a>
</section>

<section class="section-block section-tinted" aria-labelledby="workflows-heading">
  <p class="eyebrow">Shared scientific workflows</p>
  <h2 id="workflows-heading">One reference across implementations</h2>
  <p class="section-intro">Use the platform pages for scientific assumptions,
  interpretation, and reporting choices, then follow package documentation for
  executable instructions.</p>
  <ul class="workflow-link-grid">
    <li><a href="{{ '/workflows/coalescence/' | relative_url }}">Community coalescence <span aria-hidden="true">→</span></a></li>
    <li><a href="{{ '/workflows/carbon-use-efficiency/' | relative_url }}">Carbon-use efficiency <span aria-hidden="true">→</span></a></li>
    <li><a href="{{ '/workflows/resource-flux/' | relative_url }}">Resource-processing flux <span aria-hidden="true">→</span></a></li>
    <li><a href="{{ '/workflows/effective-glv/' | relative_url }}">Effective GLV reduction <span aria-hidden="true">→</span></a></li>
    <li><a href="{{ '/workflows/stability/' | relative_url }}">Stability and feasibility <span aria-hidden="true">→</span></a></li>
    <li><a href="{{ '/workflows/temperature/' | relative_url }}">Temperature scaling <span aria-hidden="true">→</span></a></li>
  </ul>
</section>

<section class="section-block" aria-labelledby="pathways-heading">
  <p class="eyebrow">Start with what you need</p>
  <h2 id="pathways-heading">Find the right route through DigiMic</h2>
  <div class="pathway-grid">
    <article>
      <span class="pathway-number" aria-hidden="true">01</span>
      <h3>Choose an implementation</h3>
      <p>Compare the available Python and Julia packages and find their owned documentation.</p>
      <a href="{{ '/resources/' | relative_url }}">Packages and training <span aria-hidden="true">→</span></a>
    </article>
    <article>
      <span class="pathway-number" aria-hidden="true">02</span>
      <h3>Apply a workflow</h3>
      <p>Start from a shared scientific definition before selecting package-specific instructions.</p>
      <a href="{{ '/workflows/' | relative_url }}">Research workflows <span aria-hidden="true">→</span></a>
    </article>
    <article>
      <span class="pathway-number" aria-hidden="true">03</span>
      <h3>Get help or contribute</h3>
      <p>Report a package issue, propose a model extension, or bring a dataset or research question.</p>
      <a href="{{ '/support/' | relative_url }}">Support and contribution <span aria-hidden="true">→</span></a>
    </article>
  </div>
</section>

<section class="section-block project-vision" aria-labelledby="vision-heading">
  <div>
    <p class="eyebrow">Project vision</p>
    <h2 id="vision-heading">A bridge from metabolism to microbiome prediction</h2>
    <p>DigiMic is developing the parameterisation and modelling layers needed
    to connect biological information with community-scale predictions and
    experimental validation.</p>
    <a class="text-link" href="{{ '/about/' | relative_url }}">See what exists today and what comes next <span aria-hidden="true">→</span></a>
  </div>
  <img src="{{ '/assets/img/digimic-workflow.jpg' | relative_url }}"
       alt="DigiMic workflow from metabolic parameterisation through microbiome modelling to experimental validation"
       width="1800" height="1045" loading="lazy">
</section>
