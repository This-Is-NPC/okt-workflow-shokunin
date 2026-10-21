---
name: okt-task-create
description: PLAN → DO handoff — author the task with an INVEST-checked story; record prioritization when alternatives exist.
schema_version: 2
role_affinity:
  - Ideator
  - Owner
command:
  name: okt-task-create
  next:
    - name: okt-task-implement
      context: bare
      when: The task is in development
---
Author a task; do not implement it.

1. **Check feasibility.** Stop and report technical blockers and alternatives when the request is infeasible; create no task.
2. **Write the story.** Fill `okt template show user-story` as an INVEST-checked description, then create it with `okt task create`.
3. **Surface ambiguity.** Present `confirmation` and `similar_tasks` from the response verbatim; never choose silently.
4. **Declare scope.** Fill `comment-scope`, post it as `#scope`, then post `#self-branch` before moving the task to development.
5. **Handoff.** Continue with `okt-task-implement` only after the development guards are satisfied.
