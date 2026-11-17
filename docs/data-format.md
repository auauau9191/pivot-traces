# Data format

All results live in one file: [`tests/matrix.csv`](../tests/matrix.csv). One row is one test case
for one detection. `scripts/matrix_report.py` validates the file and builds
[`results.md`](results.md) and [`results.json`](results.json).

| Column | Meaning | Example |
|---|---|---|
| `tool` | Tool tested, lower case | `ligolo-ng` |
| `version` | Exact tool version | `0.8.2` |
| `os` | Operating system of the host under test | `windows-11-24h2` |
| `scenario` | Scenario name from the tool's own documentation | `reverse-socks` |
| `variant` | `V0` to `V4`, defined in the method | `V1` |
| `detection_id` | Rule identifier or file name | `8b0e12da-d3c3-49db-bb4f-256703f380e5` |
| `detection_source` | Who publishes the detection | `SigmaHQ` |
| `result` | `fired`, `missed` or `not-applicable` | `missed` |
| `evidence` | Path to a file in `evidence/`. Required unless the result is `not-applicable` | `evidence/ligolo-ng_0.8.2_...jsonl` |
| `date` | Date of the test, ISO format | `2026-12-06` |
| `contributor` | GitHub handle of the person who ran the test | `auauau9191` |
| `telemetry` | Telemetry baseline used | `sysmon-15.15+swiftonsecurity` |
| `notes` | Free text. Avoid commas or quote the field | |

Rules:

- The same test case may appear more than once with different contributors. Repeat results are
  kept, not overwritten.
- Evidence files follow the naming rule in [`evidence/README.md`](../evidence/README.md).
- State the detection's version or commit in `notes` when the source publishes one.

`results.json` carries the same rows as a JSON array, for dashboards and other projects.
