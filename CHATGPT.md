# CHATGPT.md

## Repository purpose

`tech.scad` is the central catalog and knowledge hub for the complete SCAD
landscape: tooling, templates, reusable libraries and user CAD projects.

Its scope is intentionally broader than `meta.scad-projects`.

## Critical boundary with meta.scad-projects

Do not turn `tech.scad` into a second integration repository.

`meta.scad-projects` exists to maintain and verify a small controlled set for
the **current** SCAD project infrastructure: runtime, runtime tests, project
tooling, reference template and representative library integration.

`tech.scad` also includes classic infrastructure and all relevant user
projects.

## Project infrastructure generations

Keep these concepts distinct:

```text
classic standalone
    older CAD project without shared project workflow

classic shared-actions
    CAD project using brainboxemb/brainboxemb.github.actions

current
    project using tool.scad-project + docker.scad-toolchain
```

`brainboxemb.github.actions` remains relevant tooling while classic projects
still consume it. Do not remove it from the catalog merely because new projects
use the current infrastructure.

## SCAD engine verification rule

Do not infer OpenSCAD/PythonSCAD use from a repository name such as `.cad.`.

Before adding or classifying a user CAD repository, inspect its contents.

Acceptable OpenSCAD evidence includes actual `.scad` project source and/or an
OpenSCAD build invocation.

For PythonSCAD, a `.py` extension by itself is insufficient. Look for
PythonSCAD-specific source/API usage, project configuration declaring the
PythonSCAD engine, or a PythonSCAD build/render invocation.

Record engines separately from infrastructure generation. A project can use
OpenSCAD or PythonSCAD regardless of whether it is classic or current.

## Catalog source

`catalog.yml` is the curated source of truth for membership, broad role,
detected engine and project-infrastructure classification.

When adding a repository:

1. inspect the repository for actual SCAD-engine evidence;
2. determine its infrastructure generation/provider from configuration and
   workflows;
3. add it to `catalog.yml`;
4. add/update the appropriate human-readable index;
5. link to the owning repository rather than copying detailed implementation
   documentation.

## Ownership rule

The listed repository remains authoritative for code/CAD geometry, project
status, dependency versions, releases, detailed documentation, tests and
generated evidence.

Avoid manually duplicating volatile facts such as latest tag, latest commit or
CI state. Generate those later if needed.

## Dependency rule

`tech.scad` is an information layer, not a project dependency.

Current consumer projects should depend directly on `tool.scad-project` and
specific `lib.scad.*` libraries. Classic projects may consume
`brainboxemb.github.actions` directly.

Do not introduce a requirement for projects to checkout or include
`tech.scad`.

## Initial automation rule

Keep the first implementation deliberately simple and curated. A future
status/dashboard should read `catalog.yml` and inspect/query the owning
repositories rather than creating hand-maintained status copies.

## Documentation style

Use English for repository documentation to match the surrounding SCAD
repositories. Prefer concise role descriptions, direct links, Mermaid for
architecture diagrams and explicit source-of-truth boundaries.
