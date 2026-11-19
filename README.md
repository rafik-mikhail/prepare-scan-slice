# Prepare Scan Slice

An agent skill that turns one existing automated security-scan finding into a traceable evidence handoff. It records the source snapshot, relevant excerpts, and evidence gaps without deciding whether the finding is valid.

## Use the skill

Use [`SKILL.md`](SKILL.md) in your agent’s skill directory under `prepare-scan-slice/`. Provide one existing scanner finding or faithful export, access to the corresponding source, and the authorized read and write boundary. The full scan report is optional. A source directory alone does not activate the skill.

The skill produces a `handoff.md` for [Investigate Scan Issue](https://github.com/rafik-mikhail/investigate-scan-issue), with the original finding or export and any necessary redactions. If the agent cannot write the file, it returns the complete redacted handoff inline instead.

## Use as agent instructions

Copy the [Prepare Scan Slice instruction gist](https://gist.github.com/rafik-mikhail/a448ba4c216e9b72c036f057665951f5) into your agent’s instruction file. The gist contains the same guidance with `applyTo: "**"` front matter for tools that support it. If your agent accepts plain Markdown instructions, copy the body without the front matter.

## How to test

The [original acceptance test guide](TESTING.md) targets `1.0.0`. It covers evidence selection, stale locations, dirty workspaces, missing dependencies, and permission boundaries. It has not been revised for this version.
