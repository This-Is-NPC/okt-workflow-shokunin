---
name: okt-reflect
description: Turn recorded corrections and guard friction into proposed changes to the preset or project instructions.
schema_version: 2
command:
  name: okt-reflect
  parameters:
    - name: period
      type: string
      required: false
  next:
    - name: okt-task-create
      context: bare
      when: The user approved a change to implement
---
Propose rule changes from what went wrong. Read-only: propose; the user decides.

1. **Collect corrections.** Run `okt error list --tag agent-correction`, find the expected behavior with `okt search "<description>" --entity-type solution`, and rank confirmed remedies with `okt solution list-top`.
2. **Collect friction.** Run `okt insights summary`, `okt logs list --category guard --since <period>` (default `7d`), and `okt metrics summary --period <period>`.
3. **Group by cause.** Use one group for each missing rule, ambiguous rule, conflicting rule, or product/workflow gap that a rule cannot fix.
4. **Propose the smallest change.** Identify whether it belongs in a preset law, skill, template, guard, the project's `AGENTS.md`, or an Omakiten issue. Prefer a guard, template, or check over more prose.
5. **Present evidence and exact changes.** Include record IDs, counts, and proposed text or YAML. Apply nothing.
