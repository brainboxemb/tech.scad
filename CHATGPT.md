# CHATGPT.md

## Repository purpose

`tech.scad` is the central catalog and knowledge hub for the complete SCAD
landscape: tooling, templates, reusable libraries and user CAD projects.

Its scope is intentionally broader than `meta.scad-projects`.

## Critical boundary with meta.scad-projects

Do not turn `tech.scad` into a second integration repository.

`meta.scad-projects` exists to maintain and verify a small controlled
development ecosystem: runtime, runtime tests, project tooling, reference
template and representative library integration.

`tech.scad` catalogs the wider landscape, including all relevant libraries
and user projects.

A repository may belong in `tech.scad` without belonging in the
`meta.scad-projects` integration set.

## Catalog source

`catalog.yml` is the curated source of truth for **membership and broad role**
inside the SCAD landscape.

When adding a repository:

1. add it to `catalog.yml`;
2. add/update the appropriate human-readable index;
3. link to the owning repository rather than copying detailed implementation
   documentation.

## Ownership rule

The listed repository remains authoritative for:

- code and CAD geometry;
- project status;
- dependency versions;
- releases/tags;
- detailed documentation;
- tests and generated evidence.

Avoid manually duplicating volatile facts such as latest tag, latest commit or
CI state in `tech.scad`. If those become useful here, generate them from the
source repositories.

## Dependency rule

`tech.scad` is an information layer, not a project dependency.

Consumer projects should depend directly on `tool.scad-project` and the
specific `lib.scad.*` libraries they consume.

Do not introduce a requirement for projects to checkout or include
`tech.scad`.

## Initial automation rule

Keep the first implementation deliberately simple and curated.

Do not add submodules, status workflows or repository synchronization merely
because they exist in `meta.scad-projects`. Add automation here only when it
serves the broad catalog/knowledge role.

A future generated status/dashboard should read `catalog.yml` and query the
owning repositories rather than creating hand-maintained status copies.

## Documentation style

Use English for repository documentation to match the surrounding SCAD
repositories.

Prefer:

- concise role descriptions;
- direct links to owning repositories;
- Mermaid for architecture diagrams;
- clear distinction between source-of-truth information and generated/live
  information.
