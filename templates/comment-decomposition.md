---
name: Comment — Decomposition
description: Plan module map required before work on a plan starts.
entity: comment
default: comment-decomposition
laws:
  - template-fidelity
---
| Module | Task | Owns (files) | Provides | Consumes | Wave |
| --- | --- | --- | --- | --- | --- |
| <cohesive module> | <task id> | <paths only this task writes> | <interfaces it exposes> | <interfaces it relies on> | <n> |

**Shared knowledge** — <values or rules used by several modules and the module owning each>

**Why this split** — <smallest safe decomposition; explain why one task is best when applicable>
