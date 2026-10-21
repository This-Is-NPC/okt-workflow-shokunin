---
name: Comment — Boundary
description: Input-domain analysis required before documentation begins.
entity: comment
default: comment-boundary
laws:
  - template-fidelity
  - design-principles
---
One row per input class at every boundary the change touches. Start with transport and encoding, then domain fields, and include the rejection response.

| Boundary | Input class | Handled by | Evidence |
| --- | --- | --- | --- |
| <entry point> | <valid / invalid / edge class> | type (unrepresentable) · parse (rejected at boundary) · test | <type, parser, or test name> |

**Unhandled** — <classes with no handling, as findings; "none">

Write `n/a: <reason>` when the change touches no external input.
