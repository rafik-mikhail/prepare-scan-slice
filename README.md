# Prepare Scan Slice

An agent skill that collects a small, traceable package of source evidence for an authorized defensive code review. It records the source snapshot, relevant excerpts, and missing context without deciding whether the finding is valid.

## Use the skill

Use [`SKILL.md`](SKILL.md) in your agent’s skill directory under `prepare-scan-slice/`. For scan triage, provide one existing finding, the authorized source snapshot, and a review objective. The skill does not run a new scan or modify source.

Pass the resulting handoff and the original finding to [Investigate Scan Issue](https://github.com/rafik-mikhail/investigate-scan-issue). You can paste them into the next prompt or point the agent to the files. A separate agent is optional.

## Use as agent instructions

Copy the [Prepare Scan Slice instruction gist](https://gist.github.com/rafik-mikhail/a448ba4c216e9b72c036f057665951f5) into your agent’s instruction file. The gist contains the same guidance with `applyTo: "**"` front matter for tools that support it. If your agent accepts plain Markdown instructions, copy the body without the front matter.

## How to test

Follow the [acceptance test guide](TESTING.md). It covers evidence selection, stale locations, dirty workspaces, missing dependencies, and permission boundaries.
