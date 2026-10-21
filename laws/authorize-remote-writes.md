---
name: Authorize remote writes
severity: error
---
1. **Proceed on reversible local work.** Make local edits, branches, commits, task splits, and comments within the request without waiting for another confirmation; present the result and preserve completed work unless the user names a revert.
2. **Authorize every remote write.** Never run `git push`, `git push --force`, `gh pr create`, `gh pr edit`, `gh pr merge`, or another remote mutation without explicit user authorization in this conversation. Each remote action needs its own approval.
