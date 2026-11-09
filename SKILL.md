---
name: traffic-light-guidelines
description: Use for long-running builds, tests, or dependent tasks when repeated status checks or large logs would consume context, in one session or across agents.
---

# Traffic Light Guidelines

## One status source per task

Reuse the original process handle, task ID, or existing status summary. Agree on the evidence needed to proceed. Use existing tools first. Write a small task-specific helper only when the task needs it.

## Act on the light

- **YELLOW — Wait.** While the result is pending, wait on the same handle. If only polling is available, space checks by expected duration and urgency. Check when the result can change your next action, a deadline approaches, or the task appears stalled.
- **GREEN — Proceed.** Continue dependent steps after the task succeeds and the agreed checks pass.
- **RED — Diagnose.** On task or check failure, pause dependent steps. Read the error summary and relevant log excerpt. Verify which completed work can be reused before retrying.

## Across agents

Give each task one status owner and one shared status source. Prefer an existing completion notification or a designated waiter. Hand off the task ID, state, and artifact location or error summary. Keep independent work moving.

For a five-minute build, launch once and wait on its handle. Check the exit code and required test report on completion. Read relevant logs if the build fails or appears stalled.
