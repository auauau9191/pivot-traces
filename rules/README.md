# Detections

A rule lives here only after it has passed the test method in `docs/methodology.md`:
it fired on the default variant and at least one other, stayed quiet on the baseline, and has
evidence for both.

- `sigma/` - Sigma rules. Each rule's `references` field links to its rows in `docs/results.md`.
- `splunk/` - Splunk queries for signals that Sigma cannot express well (timing, session length).

Every rule file states: tool versions tested, telemetry required, known false positives, and the
variants it does not catch.
