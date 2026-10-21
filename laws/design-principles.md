---
name: Design principles
severity: warning
---
Apply a principle only where its condition holds, and record the decision it changed.

1. **Model the domain in structure.** When state or a shape branches in several places, encode it once as a state machine, typed model, or table rather than scattered conditionals.
2. **Parse at the boundary.** Turn untrusted input into a domain type at the outermost boundary, including transport and encoding; reject what cannot parse there, and ensure the rejection path cannot fail.
3. **Make retried work converge.** When an operation can be retried or interrupted, make it idempotent and atomic; skip this only when no retry or crash path exists.
4. **Subtract before adding.** Remove dead code and redundant checks in the affected area before building on the simpler base.
