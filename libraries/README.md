# Reusable libraries

SCAD libraries contain geometry, reference models or APIs intended to be
consumed by multiple CAD projects.

## Current libraries

| Repository | Purpose |
| --- | --- |
| [`lib.scad.clamps`](https://github.com/brainboxemb/lib.scad.clamps) | Reusable parametric clamp designs and public library API. |
| [`lib.scad.hub75`](https://github.com/brainboxemb/lib.scad.hub75) | Reusable HUB75 LED-panel reference geometry and mechanical dimensions/API. |

## Library boundary

A library owns its reusable geometry and public API. A consuming project should
depend directly on the library it needs; it should not depend on `tech.scad`.

```text
user project
    ├── tool.scad-project
    ├── lib.scad.clamps
    └── lib.scad.hub75

tech.scad
    observes and catalogs these repositories
```

Library-specific design documentation, tests, generated build output and
versioning policy remain in the library repository itself.
