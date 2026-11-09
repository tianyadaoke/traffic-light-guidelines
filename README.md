# Traffic Light Guidelines

A short Agent Skill for long-running builds, tests, and dependent tasks. It gives a single session or a team of agents the same decision rules for when to wait, proceed, or diagnose a failure.

## Use it

**Project guidance.** Merge the body of [SKILL.md](SKILL.md) into your existing `AGENTS.md` or `CLAUDE.md`. Apply the rules to tasks that may outlast a tool call or block another step.

**On-demand skill.** Place the `traffic-light-guidelines` folder in your agent's skills directory. For a long build or test, ask your agent to apply it.

> Use traffic-light-guidelines for this build and test run.

## Why it exists

In the project where these rules originated, I used traffic-light states, a single status source per task, and local process waiting. I observed fewer repeated status and log reads and lower token consumption. That workflow used a runner to wait and advance steps. This skill extracts the decision rules so agents can apply them with the tools available in their own environment.

## What to expect

The biggest opportunity is a task that spans several tool calls, gates another step, or produces logs too large to review routinely. A short command that already returns its result in one call gains little from additional coordination. Continuous waiting, completion notifications, and process handles depend on the host. The token savings attributable to this skill and its effects across hosts have yet to be measured.

## Contributing

Pull requests are welcome. Describe the situation your change addresses and what the agent would do differently. Prefer edits that clarify a decision or simplify an existing rule. Keep the skill concise and self-contained.
