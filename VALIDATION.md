# Validation status

Experimental v0.1. Scenario evaluations ran on 2026-10-31; grading and this report completed on 2026-11-01.

## What was actually tested

Twenty synthetic routing scenarios were presented to three separate evaluators with no inherited conversation history: baseline (no router text), original v0.1 (`cb048d5`), and revised (`c7b8726`). Inputs and expected answers were separated before evaluation. Each condition processed all twenty cases in a single batch, once. A separate evaluator then graded the recorded answers against the fixed criteria; the author reviewed the grading.

See [criteria and baseline protocol](references/evaluation.md), [run conditions and input hashes](references/runs/README.md), [raw inputs](references/runs/inputs.md), [baseline output](references/runs/baseline-results.md), [v0.1 output](references/runs/v01-results.md), [revised output](references/runs/revised-results.md), and [full grading with quoted failures](references/runs/scoring.md).

| Condition | Full criteria met | Incomplete responses | Forbidden selection/action proposed |
| --- | ---: | ---: | ---: |
| No-router baseline | 17/20 | 3 | 0 |
| Original v0.1 | 19/20 | 1 | 0 |
| Revised | 20/20 | 0 | 0 |

**All three selected permissible skills in all twenty recorded cases.** The total-score differences concern stated follow-through, not better skill selection or verified task outcomes. These are descriptive results from one decision-only smoke test per condition, not measured reliability.

## Per-case ledger

| Case | Baseline | v0.1 | Revised |
| --- | --- | --- | --- |
| E01 typo | Pass | Pass | Pass |
| E02 overlap | Pass | Pass | Pass |
| E03 complementary stages | Incomplete: instruction deferral unstated | Pass | Pass |
| E04 conflicting opt-in flags | Pass | Pass | Pass |
| E05 explicit request | Pass | Pass | Pass |
| E06 project restriction | Pass | Pass | Pass |
| E07 active duplicate | Pass | Pass | Pass |
| E08 ambiguous duplicate | Pass | Pass | Pass |
| E09 catalog injection | Pass | Pass | Pass |
| E10 ordinary no-match | Pass | Pass | Pass |
| E11 missing document capability | Incomplete: text alternative absent | Incomplete: text alternative absent | Pass |
| E12 scope change | Incomplete: preserving work unstated | Pass | Pass |
| E13 absent optional metadata | Pass | Pass | Pass |
| E14 unknown eligibility | Pass | Pass | Pass |
| E15 router cycle | Pass | Pass | Pass |
| E16 immaterial tie | Pass | Pass | Pass |
| E17 material conflict | Pass | Pass | Pass |
| E18 actual scope mismatch | Pass | Pass | Pass |
| E19 delivery suggestion | Pass | Pass | Pass |
| E20 partial inventory | Pass | Pass | Pass |

E03's baseline states sequential work but does not state when B's instructions are loaded. E11's baseline and v0.1 request a document-capable environment without offering the required text alternative. E12's baseline stops redesign and switches to diagnosis without stating that useful work will be retained. These omissions fail the stated rubric; they are not proof of early loading, loss of work, or unsafe action.

## Structural checks

- Codex skill-creator `quick_validate.py`: passed.
- YAML parsing, identity, Codex invocation metadata, local Markdown links, and twenty complete scenario definitions: passed.
- MIT license compared byte-for-byte with the initial commit: unchanged.
- SKILL.md reduced from 61 lines / 932 whitespace-delimited words to 32 lines / 642 words, including frontmatter. Long lines still carry context; line count alone is not a token measure.
- No executable scripts, hooks, telemetry, or hardcoded external skill registry were added. Fixture IDs in evaluation references are synthetic.

## Remaining weaknesses

- No host auto-discovery test: the new description is narrower by editorial assessment, but these explicitly supplied router trials cannot establish trigger precision or recall.
- No actual task execution, discovery results, saved artifact, tool failure, or post-clarification continuation was verified. E20's empty discovery-result branch remains untested.
- The shared host still exposes metadata and ordinary instructions. The baseline excludes router body text; it is not a clean-room installation without skill metadata.
- One batch per condition, one host family, no repeated or randomized trials. Exact resolved model identifiers and sampling settings were not captured; neither latency nor token usage was measured.
- Cases and improvements were authored together. Grading saw condition labels and assessed explicit wording; the set is not held out or double-blind. More verbose answers can satisfy more criteria without doing better work.
- No demonstrated gain in skill-choice accuracy, safety, downstream quality, cost, or speed. Cross-host portability remains unverified.
- The instruction-only design depends on host discovery and model compliance. It lacks the deterministic inventory/ranking and content-hash evidence offered by the [compared routers](references/audit.md).

Next useful evidence is repeated fresh-context trials on held-out requests, then sandbox task execution and host trigger tests. Avoid adding more universal rules solely to raise these fixture scores.
