# pivot-traces

**Do public detections for pivoting tools actually fire? A tested, evidence-backed reference.**

Tunnelling and pivoting tools such as Chisel, Ligolo-ng and SSH port forwarding are standard in
penetration tests and are also used by real intruders. Plenty of indicator lists and detection
rules for them are public. Very few come with proof: the tool version tested, the logs and packet
captures behind each claim, or a record of what happens when an operator renames the binary or
changes a port.

This repository tests those claims in a small reproducible lab and publishes the results.

> **Status: in progress.** Nothing in this repository is verified until it appears in
> [`docs/results.md`](docs/results.md) with evidence. Pages marked `UNVERIFIED` list claims
> collected from other sources that have not been tested here yet.

## What you get

| Part | Location | Contents |
|---|---|---|
| Results matrix | [`docs/results.md`](docs/results.md) | Tool x version x variant x detection: fired or not, with a link to evidence |
| Tool pages | [`tools/`](tools/) | Host and network traces per tool, graded by how well they survive simple operator changes |
| Detections | [`rules/`](rules/) | Sigma rules and Splunk queries. A rule is added only after it passes the test method |
| Evidence | [`evidence/`](evidence/) | Sanitised logs and packet captures behind every claim |
| Method | [`docs/methodology.md`](docs/methodology.md) | How tests are run, so anyone can repeat or challenge a result |
| Lab | [`docs/lab-setup.md`](docs/lab-setup.md) | The lab design and telemetry sources |
| Prior art | [`docs/prior-art.md`](docs/prior-art.md) | What already exists and what this adds |

## Who it is for

- **Detection engineers and SOC analysts:** which public rules to trust, and behavioural signals to add.
- **Incident responders:** what these tools leave on disk, in logs and on the wire.
- **Penetration testers:** what your tooling exposes, so you can tell clients what their SOC should have seen.

## Scope

First release: **Chisel**, **Ligolo-ng**, and **SSH port forwarding** (OpenSSH and Plink).
Planned next: DNS tunnelling.

Out of scope: modifying tools to avoid detection. Variants are limited to changes an operator can
make with the tool's own documented options or by renaming a file. See the method.

## Responsible use

Everything here was produced in an isolated lab that the author owns. No data from client
networks, training-provider labs or third-party systems is included. The content is intended for
defence, authorised testing and education.

## Credits

This project was inspired by the trace-based approach of
[Impacket-IoCs](https://github.com/ThatTotallyRealMyth/Impacket-IoCs) and builds on public rules
from SigmaHQ and Elastic and on the LOTTunnels catalogue. Sources are listed in
[`docs/prior-art.md`](docs/prior-art.md).

## Licence

To be decided before first release. See the note in [`ROADMAP.md`](ROADMAP.md).
