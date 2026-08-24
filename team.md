---
layout: page
title: Team
permalink: /team/
description: People and package contributors building the DigiMic platform.
---

DigiMic is an open collaboration across microbial ecology, mathematical
modelling, bioinformatics, and research software. Repository histories preserve
the full record of code-level contributions.

## Project team

The project team comprises the maintainers working across the DigiMic platform
and its independently maintained packages.

<div class="team-grid">
{% for person in site.data.team.team %}
<article class="team-card">
  {% if person.img %}
    <img class="team-photo" src="{{ person.img | relative_url }}" alt="{{ person.alt }}" width="460" height="460" loading="lazy">
  {% else %}
    <div class="team-avatar" aria-hidden="true">{{ person.name | slice: 0 | upcase }}</div>
  {% endif %}
  <div class="team-details">
    <h3>{{ person.name }}</h3>
    <p class="team-role">{{ person.role }}</p>
    <p class="team-position">{{ person.position }}</p>
    <div class="team-links">
      {% if person.github %}
        <a href="{{ person.github }}">GitHub <span aria-hidden="true">↗</span></a>
      {% endif %}
      {% if person.profile %}
        <a href="{{ person.profile }}">{{ person.profile_label | default: "Profile" }} <span aria-hidden="true">↗</span></a>
      {% endif %}
    </div>
  </div>
</article>
{% endfor %}
</div>

## Package contributors

Each package has its own contributor section because its repository history and
technical ownership are independent. The listed people are the human
contributors currently verified from GitHub and local repository history;
linked histories remain the complete source of truth.

{% for package in site.data.team.package_contributors %}
<section class="package-contributors" aria-labelledby="package-{{ forloop.index }}-heading">
  <h3 id="package-{{ forloop.index }}-heading">{{ package.name }} contributors</h3>
  <p>{{ package.description }}</p>
  <div class="team-links">
  {% if package.repository %}
    <a href="{{ package.repository }}">Package source <span aria-hidden="true">↗</span></a>
  {% endif %}
  {% if package.history %}
    <a href="{{ package.history }}">View repository history <span aria-hidden="true">↗</span></a>
  {% endif %}
  </div>
  <div class="team-grid">
  {% for person in package.contributors %}
    <article class="team-card">
      <div class="team-avatar" aria-hidden="true">{{ person.name | remove: '@' | slice: 0 | upcase }}</div>
      <div class="team-details">
        <h4>{{ person.name }}{% if person.handle %} ({{ person.handle }}){% endif %}</h4>
        <p class="team-role">{{ person.role | default: "Contributor" }}</p>
        <a href="{{ person.github }}">GitHub profile <span aria-hidden="true">↗</span></a>
      </div>
    </article>
  {% endfor %}
  </div>
</section>
{% endfor %}

<section class="contributor-note" aria-labelledby="contributors-heading">
  <h2 id="contributors-heading">Open collaboration</h2>
  <p>Contributor listings are snapshots, while repository histories preserve
  complete authorship and credit as the project grows. TPCP will gain its own
  canonical history when its source repository is migrated into DigiMicOrg.</p>
  <ul>
    <li><a href="https://github.com/DigiMicOrg/DigiMicPy/graphs/contributors">DigiMicPy contributors</a></li>
    <li><a href="https://github.com/DigiMicOrg/DigiMic/graphs/contributors">DigiMic.jl contributors</a></li>
    <li><a href="https://github.com/DigiMicOrg/DigiMicOrg.github.io/graphs/contributors">Platform website contributors</a></li>
  </ul>
</section>
