# Tooling and templates

This section indexes the shared infrastructure used to create, build, document
and verify SCAD projects.

## Current project infrastructure

| Repository | Role |
| --- | --- |
| [`docker.scad-toolchain`](https://github.com/brainboxemb/docker.scad-toolchain) | Shared runtime/build image containing OpenSCAD, PythonSCAD and supporting tools. |
| [`docker.scad-toolchain.test`](https://github.com/brainboxemb/docker.scad-toolchain.test) | External/consumer-style verification that the runtime image provides the advertised capabilities. |
| [`tool.scad-project`](https://github.com/brainboxemb/tool.scad-project) | Reusable project CLI, repository/dependency policy, build orchestration and reusable GitHub Actions workflows. |
| [`template.scad-project`](https://github.com/brainboxemb/template.scad-project) | Reference consumer and starting point for new structured SCAD projects. |

New CAD repositories are intended to use this infrastructure.

## Classic project infrastructure

Earlier CAD projects use a different shared tooling layer:

| Repository | Role |
| --- | --- |
| [`brainboxemb.github.actions`](https://github.com/brainboxemb/brainboxemb.github.actions) | Shared OpenSCAD GitHub Actions, setup, render/export and support scripts used by the earlier project generation. |

This repository is still relevant because existing CAD projects actively refer
to it. Calling it **classic** describes the project generation; it does not mean
the repository can simply be removed.

Some still-older CAD repositories predate the shared workflow and contain no
GitHub Actions workflow at all.

## Infrastructure generations

```text
classic standalone
    project-local OpenSCAD source
    no shared GitHub workflow

classic shared-actions
    project OpenSCAD source
        -> brainboxemb.github.actions
        -> OpenSCAD runtime/setup in shared Actions tooling

current
    project.yml / structured project
        -> tool.scad-project
        -> docker.scad-toolchain
        -> OpenSCAD and/or PythonSCAD
```

The infrastructure generation and the CAD engine are separate properties. A
classic project may use OpenSCAD; a current project may use OpenSCAD,
PythonSCAD, or both.

## Ecosystem engineering

[`meta.scad-projects`](https://github.com/brainboxemb/meta.scad-projects) is
not another user-facing project tool. It maintains and observes the controlled
integration set used to evolve the current SCAD project ecosystem itself.

It deliberately does not need to include every classic tool, library or user
project. The wider inventory belongs here in `tech.scad`.

## Ownership

Each repository remains authoritative for its own:

- implementation;
- configuration;
- releases and tags;
- tests;
- detailed documentation.

This index describes roles and navigation only.
