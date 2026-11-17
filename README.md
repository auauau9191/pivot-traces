# pivot-traces

**An open, evidence-backed record of whether public detections for tunnelling and pivoting tools actually fire.**

Tunnelling tools such as Chisel, Ligolo-ng, Cloudflared, ngrok and SSH port forwarding are used in
penetration tests and in real intrusions. Public detection rules and indicator lists exist for
many of them. Very few come with proof: the tool version tested, the logs and packet captures
behind each claim, or a record of what happens when an operator renames a file or changes a port.

This project collects that proof, in one format, from anyone who can run a lab.

> **Status: early.** The method, data format and a first inventory of public rules are published.
> No lab results have been recorded yet. Nothing here is verified until it appears in
> [`docs/results.md`](docs/results.md) with evidence.

## Why it matters

- A CISA ransomware advisory names Ligolo and Cloudflared among the tools actors used for
  tunnelling. In a first survey for this project, no public Sigma rule for Ligolo-ng was found.
  See [`docs/coverage-inventory.md`](docs/coverage-inventory.md) for what was checked.
- Most public rules reviewed so far match file names and command-line text. Nobody publishes how
  they hold up after simple operator changes.
- Defenders in small teams depend on public rules and cannot test them all.

## What is here

| Part | Location | Contents |
|---|---|---|
| Coverage inventory | [`docs/coverage-inventory.md`](docs/coverage-inventory.md) | Which public rule sets have detections for which tool |
| Results | [`docs/results.md`](docs/results.md), [`docs/results.json`](docs/results.json) | Tool x version x variant x detection: fired or missed, with evidence |
| Method | [`docs/methodology.md`](docs/methodology.md) | How a test is run, so anyone can repeat or challenge a result |
| Principles | [`docs/principles.md`](docs/principles.md) | What a result means, what it does not mean, and how the project stays fair |
| Data format | [`docs/data-format.md`](docs/data-format.md) | The one file that holds every result |
| Tool pages | [`tools/`](tools/) | Traces per tool, graded by how well they survive simple changes |
| Lab | [`docs/lab-setup.md`](docs/lab-setup.md) | A lab design that fits on one laptop |
| Prior art | [`docs/prior-art.md`](docs/prior-art.md) | Related work and what this adds |
| Plan | [`ROADMAP.md`](ROADMAP.md), [`docs/impact-plan.md`](docs/impact-plan.md) | Scope tiers and the route to adoption |

## Contribute

You can help without writing code:

- **Add to the inventory.** Tell us about a public rule we missed.
- **Submit a result.** Run one test case in your own lab and send the outcome with evidence.
- **Challenge a result.** Repeat a test and report a different outcome.

Start with [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Scope

First release: **Ligolo-ng**, **Chisel**, and **SSH port forwarding** (OpenSSH and Plink).
Later tiers are listed in [`ROADMAP.md`](ROADMAP.md).

Out of scope: modifying tools to avoid detection, and instructions for using the tools. Variants
are limited to changes an operator can make with a tool's own documented options or by renaming a
file.

## Responsible use

Results come from isolated labs that contributors own. No data from client networks,
training-provider labs or third-party systems is accepted. The content is for defence, authorised
testing and education. See [`SECURITY.md`](SECURITY.md).

## Credits

Inspired by the trace-based approach of
[Impacket-IoCs](https://github.com/ThatTotallyRealMyth/Impacket-IoCs). Builds on public rules
from SigmaHQ, Elastic and Splunk and on the LOTTunnels catalogue.

## Licence

To be decided before the first release. See [`ROADMAP.md`](ROADMAP.md).
