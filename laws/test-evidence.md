---
name: Test evidence
severity: error
---
1. **Ship reproducible evidence.** A behavioral change has a failing-then-passing test in the same diff, or a `#tests-passing` comment with the command, output snippet, and duration. “Tested locally” is not evidence.
2. **Prove the real artifact.** Check a delivery claim by running the delivered server, CLI, or concurrent path under the condition claimed, not only through test doubles.
3. **Read state independently.** Confirm a write through a new request, connection, or process, never only through that write's response.
4. **Wait for evidence.** Wait for the state, output, or signal that proves completion; a deadline bounds failure and is never a settle-time sleep.
5. **Break the test once.** Remove its guard or invert its condition and run the narrowest test to prove it fails; revert the mutation without weakening the assertion.
