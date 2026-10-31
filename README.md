# Skill Waypoint

**Choose the skills that fit. Keep the workflow proportional to the task.**

Skill Waypoint helps an agent select complementary installed skills, resolve overlaps, and adapt its workflow as a task changes. It uses the host's current catalog rather than a hardcoded registry.

**Experimental v0.1.** This is an instruction skill, not a background service or policy enforcement engine. See the decision-only baseline, v0.1, and revised-router results in [VALIDATION.md](VALIDATION.md). Cross-host behavior and efficiency improvements remain unproven.

## Install

With the community Skills CLI:

```sh
npx skills add abhigyan6/skill-waypoint --skill skill-waypoint
```

For a global Codex installation:

```sh
npx skills add abhigyan6/skill-waypoint --skill skill-waypoint --agent codex -g
```

Review [SKILL.md](SKILL.md) before installing. Alternatively, copy this folder into your host's documented skills directory, preserving the `agents/` and `references/` folders. Installation and automatic discovery depend on the host. The CLI is an external installer, not a runtime dependency.

## Use

> Use skill-waypoint to choose the skills and workflow for fixing this dashboard's keyboard accessibility.

> Use skill-waypoint to compare these vendors and prepare a formatted decision memo.

> Use skill-waypoint to review which installed skills fit this task before starting it.

In hosts that support named invocation, use `$skill-waypoint`. Codex metadata permits automatic selection when relevant; installation does not guarantee invocation on every turn.

## How it works

1. Identify the requested outcome and applicable project rules.
2. Select an eligible specialist for the current stage; add another only for a distinct responsibility.
3. Read the selected instructions and carry out a proportionate workflow.
4. Reconsider routing when scope or evidence changes, and report verified results.

A typo can need no specialist. An accessibility defect can use one targeted skill. A research memo can use research guidance first and a document specialist later. See [worked examples](references/examples.md).

## Boundaries

- Respects explicit-only skills and local methodology preferences.
- Recognizes active plugins stored in cache directories.
- Applies documented host defaults when optional metadata is absent.
- Resolves overlaps without imposing a fixed framework.
- Falls back to ordinary capabilities when no suitable specialist exists.
- Includes no scripts, hooks, telemetry, API keys, background tasks, or automatic updates.
- Selecting a skill does not authorize installation, delegation, publication, or other external actions.

The core is Markdown with skill frontmatter; `agents/openai.yaml` adds Codex metadata. Other hosts must support loading skills and exposing a catalog. Portability is a design goal, not a claim that every agent has been tested.

## Evaluation and contributions

See the [20 concrete scenarios and baseline protocol](references/evaluation.md), [v0.1 audit and comparisons](references/audit.md), and [validation status](VALIDATION.md). Report a concrete request, relevant publicly shareable catalog metadata, expected behavior, and observed behavior. Remove secrets and private project content.

Prefer small changes supported by reproducible routing failures. Do not add hardcoded favorite skills, vendor rankings, mandatory methodologies, or automatic setup hooks. Keep optional examples outside the main instructions.

## License

[MIT](LICENSE). Other installed skills remain separate and retain their respective licenses.
