# Tooling and templates

This section indexes the shared infrastructure used to create, build, document
and verify SCAD projects.

| Repository | Role |
| --- | --- |
| [`docker.scad-toolchain`](https://github.com/brainboxemb/docker.scad-toolchain) | Shared runtime/build image containing OpenSCAD, PythonSCAD and supporting tools. |
| [`docker.scad-toolchain.test`](https://github.com/brainboxemb/docker.scad-toolchain.test) | External/consumer-style verification that the runtime image provides the advertised capabilities. |
| [`tool.scad-project`](https://github.com/brainboxemb/tool.scad-project) | Reusable project CLI, repository/dependency policy, build orchestration and reusable GitHub Actions workflows. |
| [`template.scad-project`](https://github.com/brainboxemb/template.scad-project) | Reference consumer and starting point for a new structured SCAD project. |

## Ecosystem engineering

[`meta.scad-projects`](https://github.com/brainboxemb/meta.scad-projects) is
not another user-facing project tool. It maintains and observes the controlled
integration set used to evolve the SCAD project ecosystem itself.

It deliberately does not need to include every library or every user project.
The wider inventory belongs here in `tech.scad`.

## Ownership

Each repository remains authoritative for its own:

- implementation;
- configuration;
- releases and tags;
- tests;
- detailed documentation.

This index describes roles and navigation only.
