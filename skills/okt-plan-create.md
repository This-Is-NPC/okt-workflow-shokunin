---
name: okt-plan-create
description: Author a WBS-style plan grouping child tasks into ordered waves with a goal body.
schema_version: 2
role_affinity:
  - Owner
command:
  name: okt-plan-create
  next:
    - name: okt-plan-show
      context: bare
      when: Verify the assembled plan
    - name: okt-run
      context: bare
      when: The plan is verified
---
Author a WBS-style plan that groups child tasks into ordered waves. The plan is complete only after waves, assignments, dependencies, a goal, and its decision records are persisted.

1. **Set identity and goal.** Choose a unique kebab-case slug and name. Fill `okt template show plan-goal` with the outcome, scope, quality attributes and verification, and out-of-scope work; pass it to `okt plan create`.
2. **Build waves.** Add each ordered wave with `okt plan wave-add <slug> "<name>"` and assign every task with `okt plan assign <slug> <wave-id> <task-id>`.
3. **Persist ordering.** Add every dependency with `okt depend add <task> --on <blocker>`; waves do not replace the dependency graph.
4. **Map modules.** Fill `comment-decomposition` and post it to the plan with `okt comment add --scope plan --plan <slug> -a agent -T decomposition -b "<map>"`.
5. **Record deliberation.** Fill `comment-council` with every council point and post it as the plan's `#council` comment.
6. **Check.** Run `okt plan show <slug>` and `okt depend list <id>` for each task. No wave is empty, no task is unassigned, and no ordering edge is implicit.

**Decompose by modules, not steps.** Give each task one cohesive module and exclusive file ownership. Parallel tasks have disjoint files; define interfaces in an earlier wave than their consumers; give shared knowledge one owner.
