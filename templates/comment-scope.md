---
name: Comment — Scope
description: Task scope and module ownership required before development starts.
entity: comment
default: comment-scope
laws:
  - template-fidelity
  - scope-from-paths
---
**Module** — <one cohesive module this task delivers>

**Owns** — <files only this task writes; parallel tasks do not touch them>

**Interfaces** — consumes: <contracts it relies on> · provides: <contracts it exposes>

**Data shape** — <domain type or structure organizing the logic>

**Parallelism** — blockers: <…> · independent of: <tasks> · shared state: <none | how it is separated or serialized>

**Done signal** — <observable outcome and narrowest proving test>

**Principles applied** — <principle → changed decision>

Write `n/a: <reason>` for an inapplicable field; do not omit it.
