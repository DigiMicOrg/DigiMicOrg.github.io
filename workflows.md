---
layout: page
title: Workflows
permalink: /workflows/
description: Shared DigiMic scientific workflows, assumptions, and reporting guidance.
---

DigiMic workflows connect microbial consumer-resource models to research
questions about community assembly, carbon processing, interaction structure,
and stability. These pages define the implementation-independent concepts and
reporting choices. Package documentation owns executable instructions for a
specific language or API.

<div class="gateway-grid resource-grid">
  <article class="gateway-card gateway-card-featured">
    <h2>Community coalescence</h2>
    <p>Combine assembled communities, define their shared resource environment,
    and quantify survival, dominance, competition, and facilitation.</p>
    <a href="{{ '/workflows/coalescence/' | relative_url }}">Read the workflow <span aria-hidden="true">→</span></a>
  </article>
  <article class="gateway-card">
    <h2>Carbon-use efficiency</h2>
    <p>Distinguish species, biomass-weighted, and flux-weighted measures of
    carbon retained for growth.</p>
    <a href="{{ '/workflows/carbon-use-efficiency/' | relative_url }}">Read the workflow <span aria-hidden="true">→</span></a>
  </article>
  <article class="gateway-card">
    <h2>Resource-processing flux</h2>
    <p>Track uptake, retention, leakage, maintenance, and resource balance from
    species to whole communities.</p>
    <a href="{{ '/workflows/resource-flux/' | relative_url }}">Read the workflow <span aria-hidden="true">→</span></a>
  </article>
  <article class="gateway-card">
    <h2>Effective GLV reduction</h2>
    <p>Summarise resource-mediated effects as local species interactions near a
    specified MiCRM equilibrium.</p>
    <a href="{{ '/workflows/effective-glv/' | relative_url }}">Read the workflow <span aria-hidden="true">→</span></a>
  </article>
  <article class="gateway-card">
    <h2>Stability and feasibility</h2>
    <p>Check equilibria, local recovery, transient amplification, and positive
    coexistence in full and reduced models.</p>
    <a href="{{ '/workflows/stability/' | relative_url }}">Read the workflow <span aria-hidden="true">→</span></a>
  </article>
  <article class="gateway-card">
    <h2>Temperature scaling</h2>
    <p>Define thermal trait responses, distinguish fixed and time-varying
    environments, and report biological and numerical assumptions.</p>
    <a href="{{ '/workflows/temperature/' | relative_url }}">Read the workflow <span aria-hidden="true">→</span></a>
  </article>
</div>

## Implementations

The [DigiMicPy documentation]({{ site.digimicpy_docs_url }}/) provides the
current Python model API and executable examples. The
[DigiMic.jl repository](https://github.com/DigiMicOrg/DigiMic) documents the
Julia implementation. Shared scientific aims do not imply numerical or API
parity; check the relevant package documentation before applying a workflow.
