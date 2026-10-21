---
name: Comment — Audit
description: Independent plan audit of integrated work and its quality attributes.
entity: comment
default: comment-audit
laws:
  - template-fidelity
  - findings-actionable
---
**Verdict** — <complete | blocked: N blocking findings>

**Integrated head** — `<commit audited>` · **Suite** — `<command>` → <result>

**Blocking findings → tasks**

| path:line | severity | problem | task |
| --- | --- | --- | --- |
| <path:line> | error | <problem> | #<id> |

**Non-blocking** — <follow-up link or "none">

**Boundaries probed** — <entry points and classes independently checked>
