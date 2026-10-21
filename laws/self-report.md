---
name: Self-report
severity: error
---
1. **Record a repeated failure.** The second failed fix attempt is the trigger: call `okt error record` with a one-line description, context, and tags, then attach the working resolution with `okt solution add`.
2. **Record a user correction.** Before continuing after the user corrects how work was done, record the mistaken action with tag `agent-correction` and add the required behavior as its solution.
3. **Confirm reuse.** When a recorded solution applies again, find it with `search(query, entity_types=["error"])` and confirm it with `okt solution confirm`.

Bad: attempt 1 failed; attempt 2 worked — moved on without recording.
Good: before attempt 2, ran `search(query, entity_types=["error"])`; attempt 2 worked — `okt error record` with symptom and tags, then `okt solution add` with the resolution.

Single-attempt fixes without a user correction do not need recording; keep the log signal-rich.
