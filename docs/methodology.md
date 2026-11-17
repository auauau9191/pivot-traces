# Test method

The goal is that anyone can repeat a test and reach the same result, or show why it differs.

## 1. Unit of testing

One **test case** is: tool + exact version + operating system + scenario + variant + detection.

- **Scenario:** one documented way of using the tool, named after the tool's own documentation
  (for example "reverse SOCKS proxy"). This repository does not teach tool usage. See each tool's
  own README for commands.
- **Variant:** a simple change an operator can make without modifying the tool.

| Variant | Change |
|---|---|
| V0 | Defaults. Original file name, default port, default options |
| V1 | Binary renamed |
| V2 | Non-default port |
| V3 | Alternate transport or TLS option that the tool itself offers |
| V4 | Launched from a service or scheduled task instead of an interactive shell |

Modifying source code, packing or obfuscating a tool is out of scope.

## 2. Telemetry collected for every run

| Layer | Source |
|---|---|
| Windows host | Sysmon (process, network, file, registry, DNS events) and Security log process and filtering events |
| Linux host | auditd (execve and connect) and shell-independent process accounting |
| Network | Full packet capture at the pivot host, plus Zeek logs generated from that capture |

Record the Sysmon configuration and Zeek version used. A result is only meaningful against a
stated telemetry baseline.

## 3. Grading a trace

| Grade | Meaning |
|---|---|
| A - standalone | Survives V1 to V4 and is rare in normal activity. May justify an alert on its own |
| B - correlate | Survives some variants, or is common enough to need a second signal |
| C - context | Defeated by a rename or port change. Useful for triage, not for alerting |

## 4. Grading a detection

For each detection and each variant, record one of: `fired`, `missed`, `not-applicable`.
A detection is published in `rules/` only when:

1. it fired on V0 and at least one other variant, and
2. it stayed quiet during a baseline period of ordinary lab activity (state the length), and
3. the evidence for both is in `evidence/`.

Public rules that fail are still recorded in the results matrix. A documented miss is a result.

## 5. Evidence rules

- Every claim on a tool page links to a file in `evidence/`.
- File naming: `<tool>_<version>_<os>_<scenario>_<variant>.<pcap|evtx|json|log>`
- Sanitise before commit: lab-only IP ranges, no real hostnames, usernames, keys or tokens.
- Never include data from client networks or from training-provider labs.

## 6. Limits to state in every release

- Lab size and operating system versions tested.
- Telemetry that was not available (for example no EDR, no TLS inspection).
- Baseline length. A short baseline cannot prove a low false-positive rate in production.
