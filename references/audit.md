# v0.1 audit — 2026-10-31

Audited the original SKILL.md, README.md, VALIDATION.md, references, and agent metadata before editing. Original commit: `cb048d540b834eb3a08ae70d403be0ed42d40e0d`.

## Findings

1. **Trigger ambiguity.** “Several skills overlap” does not explicitly tie overlap to the current request. A large catalog almost always contains overlaps. “Spans specialties” can also include an ordinary question. The exclusion helps, but actual host selection reliability is untested. Narrow the trigger to a routing decision the current task needs; place a no-specialist exit first.
2. **Unmeasurable evaluation.** The original twelve rows and four appended cases have no concrete catalog, expected set, or scoring protocol. They cannot establish accuracy or baseline improvement.
3. **Context overhead.** The six-row workflow table and general completion advice repeat common agent behavior. Move examples out of the core; retain instructions that affect selection, permissions, and recovery.
4. **Unstable reporting.** “Name selected skills when useful” permits silent or verbose outputs, making comparisons difficult. Define one compact route line without requiring it for ordinary trivial tasks.
5. **Ambiguity gap.** Source/version disambiguation exists, but equally suitable candidates without a material conflict have no tie-break. Prefer host resolution or existing project convention; if still equal, choose one and state the assumption. Ask only when the difference affects the outcome.
6. **Conflicts and missing skills.** Instruction hierarchy, missing-capability fallback, and permission boundaries already exist and should survive compression. Missing optional metadata must remain distinct from unknown eligibility.
7. **Scope changes.** Re-routing and preserving completed work already exist. Make stopping the obsolete stage explicit; a new user objective should not leave old skills driving the task.
8. **No hard enforcement.** Safety rules remain instructions interpreted by a model. Catalog injection, duplicate ambiguity, and host defaults need behavioral tests, not only manifest validation.

## Comparison

Sources inspected on 2026-10-31; upstream claims below were not independently reproduced.

| Aspect | Waypoint v0.1 | Agent-Nova skill-router-mcp | Smart Route Skill-Router |
| --- | --- | --- | --- |
| Mechanism | Markdown guidance using host catalog | Local Node MCP metadata/workflow index and deterministic ranking | Python manifest router, hashes, assignment JSON, optional LLM fallback |
| Intended use | Proportionate task-stage selection | Candidate discovery across large collections | Preselect skills before subagent handoff |
| Evidence | Structural checks only | Repository has discovery, frontmatter, ranking tests | Reports a 15-task benchmark; perfect-fallback rows explicitly upper bounds |
| Duplicate handling | Agent follows host source/version resolution | Exposes duplicate paths and invocation modes | Content hashes identify selected skill content |
| Waypoint advantage | No runtime setup; no required delegation; task-size exit | Requires MCP runtime and configured roots | Requires CLI/runtime and a manifest for its main workflow |
| Waypoint weakness | No reproducible search score, inventory, content hash, or enforced gate | Better inspectable discovery evidence | Better structured handoff and executable measurement |

References: [Agent-Nova README](https://github.com/Agent-Nova-107/skill-router-mcp/blob/main/README.md), [Agent-Nova skill](https://github.com/Agent-Nova-107/skill-router-mcp/blob/main/skills/skill-router/SKILL.md), [Smart Route README](https://github.com/smart-route-skills/Skill-Router/blob/main/README.md), [Smart Route skill](https://github.com/smart-route-skills/Skill-Router/blob/main/agent-skills/skill-router/SKILL.md), [Smart Route comparison](https://github.com/smart-route-skills/Skill-Router/blob/main/docs/comparison-with-without-router.md).

Smart Route's timing comparison is a small upstream demonstration, not evidence that Waypoint will save time. Avoid copying its performance claims. Its fallback benchmark's upper bounds are not measured live-model accuracy.
