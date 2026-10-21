---
name: Workflow enforced
severity: error
---
1. **Use explicit transitions.** Move tasks only through declared workflow transitions; satisfy guards rather than bypassing or weakening them.
2. **Preview before moving.** Run `okt move <id> --to <bucket> --dry-run` to see missing evidence, then use `okt task continue <id>` for the current task's available moves.
3. **Follow the reported repair.** When a move fails, run the `fix` command from its error details instead of guessing syntax.
4. **Finish integrated work only.** Before done, verify the reviewed commit is on the integration branch with `git branch --contains <commit>`; an isolated worktree or unpushed branch is not complete.
