---
layout: page
title: Documentation ownership
permalink: /documentation/
description: Where DigiMic platform and package documentation belongs.
---

DigiMic documentation is maintained close to the source that can verify it,
while platform-wide information has one shared home.

## Platform documentation

This website is the source of truth for the project vision, shared scientific
workflows, implementation comparisons, roadmap, training directory, funding,
team, contribution routes, and general contact information.

## Package documentation

Each package repository owns its installation instructions, compatibility and
release status, implemented equations, data conventions, API reference,
executable examples, package-specific diagnostics, and development process.

The organisation site may summarise a package and link to it. A package may
briefly explain how it fits into DigiMic and link back here. Full treatments
should not be copied between repositories.

## Shared concepts and implementation recipes

For a workflow with both scientific and software layers, this site owns the
question, assumptions, equations, interpretation, and reporting guidance. A
package owns only the instructions needed to perform that workflow using its
current public interface. Package pages must state whether an operation is a
supported API, an explicit recipe, or a proposed capability.

Independent builds and version histories remain intact. Documentation location
does not imply behavioural parity between the Python and Julia packages.
