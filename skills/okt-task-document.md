---
name: okt-task-document
description: Bring user-facing documentation in line with a task's change.
schema_version: 2
role_affinity:
  - Scribe
  - Reviewer
command:
  name: okt-task-document
  next:
    - name: okt-task-commit
      context: bare
      when: Documentation is ready to commit
---
Update documentation for what the task changed. Write documentation, not production code.

1. **Read the change.** Read the task, its `#scope`, and `git diff main..HEAD` on the task branch.
2. **Update user-facing pages.** Update `README.md`, `docs/`, and relevant top-level documentation for changed behavior, commands, settings, and errors. Derive facts and displayed output from code or a real run.
3. **Commit documentation.** Use `docs(<scope>): …` on the task branch.
4. **Record evidence.** Fill `comment-documentation` and post it as `#documentation`.
