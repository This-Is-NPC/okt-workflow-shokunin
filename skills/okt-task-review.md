---
name: okt-task-review
description: Walk the diff through Fowler/Beck/Martin/Feathers lens and surface findings + refactor opportunities.
schema_version: 2
role_affinity:
  - Reviewer
command:
  name: okt-task-review
  next:
    - name: okt-task-implement
      when: Findings need fixes
      context: bare
---
Review the diff. Read-only: post findings; do not edit or commit.

1. **Read every hunk.** Run `git diff <base>..HEAD` (default `main`; use staged only when explicit).
2. **Pass in order.** Review correctness, security, smells, refactoring opportunities, and scalability or performance. Name an applicable method and tag every finding `error`, `warning`, or `info`.
3. **Probe boundaries.** For every external input touched, derive valid, invalid, and edge equivalence classes. Record in `comment-boundary` whether each class is unrepresentable by type, rejected at parse, or covered by a test; an external-input error reaching an internal layer is blocking.
4. **Post a fresh verdict.** Fill and post `comment-review-findings`, `comment-refactor-opportunities` when needed, and the `#boundary` analysis for the commit under review now. Do not make file edits or commits.
