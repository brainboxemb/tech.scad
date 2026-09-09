# tech.scad

Central catalog and documentation hub for the SCAD ecosystem: tooling, libraries, templates, and user projects.

## Purpose

`tech.scad` is the broad entry point for SCAD-related work.

It provides one place to discover:

- reusable SCAD libraries;
- project/build tooling;
- project templates;
- user CAD projects;
- documentation about how these parts relate.

The repository is an **information and catalog layer**. It is not a runtime
dependency of SCAD projects and does not own the implementation of the
repositories it lists.

## Navigation

- [Repository catalog](catalog.yml)
- [Tooling and templates](tooling/README.md)
- [Reusable libraries](libraries/README.md)
- [User projects](projects/README.md)
- [Architecture and repository boundaries](docs/architecture.md)

## Relationship with meta.scad-projects

[`meta.scad-projects`](https://github.com/brainboxemb/meta.scad-projects) and
`tech.scad` deliberately have different scopes.

`meta.scad-projects` is the engineering and integration repository for the
**SCAD project ecosystem itself**. It maintains a small controlled set of
repositories needed to develop and verify the runtime, project tool, template
and representative library integration.

`tech.scad` has the broader view. It catalogs all relevant SCAD technology,
libraries and user projects, including repositories that do not need to be part
of the meta integration test set.

In short:

```text
meta.scad-projects
    maintain and verify the SCAD development ecosystem

tech.scad
    catalog and document the complete SCAD landscape
```

## Repository model

The curated repository inventory lives in [`catalog.yml`](catalog.yml).

The catalog records membership and high-level role only. Detailed source,
configuration, releases, implementation documentation and project status remain
owned by each repository itself.

This distinction keeps `tech.scad` useful as a central overview without
creating a second source of truth for every project.

## Current areas

### Tooling

Shared runtime and project workflow infrastructure, including
`docker.scad-toolchain`, `tool.scad-project` and the reference template.

See [tooling/README.md](tooling/README.md).

### Libraries

Reusable CAD/reference geometry intended for consumption by multiple projects.

Current libraries include:

- `lib.scad.clamps`
- `lib.scad.hub75`

See [libraries/README.md](libraries/README.md).

### User projects

Concrete CAD projects remain independent repositories. They can use the shared
tooling and libraries where appropriate, but inclusion in this catalog does not
imply that a project has already been migrated to the latest project structure.

See [projects/README.md](projects/README.md).

## Future automation

The initial repository deliberately starts with a small curated catalog.

Later automation can use `catalog.yml` to generate repository status,
documentation indexes or dashboards. Live status should be generated from the
repositories themselves rather than maintained manually in multiple places.
