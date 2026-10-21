---
name: okt-audit
description: Independently audit integrated plan work against its goal and quality attributes.
schema_version: 2
role_affinity:
  - Reviewer
command:
  name: okt-audit
  next:
    - name: okt-run
      context: bare
      when: Blocking audit tasks were added
---
Audit one completed plan or task. Read-only for code: post findings; do not fix them.

1. **Read the standard.** For a plan, read `okt plan show <slug>`, its goal and quality attributes, council decisions, module map, task scopes, and the integrated diff on the integration branch. For a task, read its task body, scope, and diff.
2. **Verify the artifact independently.** Run the delivered system as it will be used, exercise every named quality attribute, run the full suite once, and read state through a separate request, connection, or process. Probe external boundaries from transport and encoding inward.
3. **Create blocking work.** For each user- or data-affecting defect, unmet quality attribute, or discarded council point that caused a defect, create one task and place it in a final audit-fixes wave.
4. **Record non-blocking work.** Post all non-blocking findings as one follow-up plan comment.
5. **Publish the verdict.** Fill `comment-audit` with the verdict, integrated head, suite result, findings, created tasks, follow-up link, and boundaries probed.
