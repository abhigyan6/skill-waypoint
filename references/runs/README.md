# Decision-only evaluation artifacts

Three separate evaluators ran on 2026-10-31 with no conversation history forked. Each received [inputs.md](inputs.md), containing only requests, catalogs, and relevant context; expected answers were withheld. Baseline received no router. The other evaluators also received the complete original or revised SKILL.md. They were instructed to read no other project files or installed skills, report choices and reasons for all twenty cases, and execute no scenario actions.

- [Baseline decisions](baseline-results.md)
- [Original v0.1 decisions](v01-results.md), router from commit `cb048d5`
- [Revised decisions](revised-results.md), router from commit `c7b8726`

The input SHA256 was `632226b1d5156bc3d3d95f29198c1ae9d63ac62ae08b97ade3e2aba601f507fb`; revised SKILL.md SHA256 was `559df0796ac38d7f35c843e82b31d049dc639be5299774efad88805aca90a91d`.

Each condition processed the twenty cases together in a single batch, once. Evaluators inherited the parent agent configuration; exact resolved model identifiers, sampling settings, latency, and token counts were not captured. They shared the host's underlying instruction constraints, but were instructed not to load the installed router or other skill bodies for the baseline. This is a no-router-text baseline, not a clean-room host lacking skill metadata.

A separate evaluator graded the recorded answers against the frozen [criteria](../evaluation.md) on 2026-11-01 without reading the router instructions. The author reviewed the scores. See the [complete grading record](scoring.md). The grader necessarily saw condition labels; this was not double-blind. The cases and improvements were authored together, so this set is not held-out evidence.

See [VALIDATION.md](../../VALIDATION.md) for the score ledger, concrete failures, and limits. These files preserve proposed decisions, not proof of task execution or automatic triggering.
