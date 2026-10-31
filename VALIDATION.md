# Validation status

Initial publication: experimental v0.1, 2026-10-31.

## Completed

- Codex skill-creator `quick_validate.py`: passed using Python and PyYAML 6.0.3 in an isolated validation environment.
- YAML parsing, manifest identity, Codex invocation metadata, and local Markdown link checks: passed.
- Publication package checked for personal absolute paths, old draft names, unfinished placeholders, and unexpected files.
- Editorial review corrected active-plugin cache handling, missing-metadata defaults, duplicate-source resolution, and failed-route recovery.

These are structural and editorial checks. They are not behavioral benchmarks.

## Not yet established

- Independent agent runs of the scenarios in [evaluation.md](references/evaluation.md).
- Comparative task quality, token usage, or time savings against a baseline.
- Behavior across multiple agent hosts or different models.

The worked examples describe intended decisions, not recorded test outcomes. Please report reproducible failures before expanding the rules.
