# Roadmap

Effort figures are estimates for a few hours per weekend.

## Scope tiers

| Tier | Tools | Why |
|---|---|---|
| 1 | Ligolo-ng, Chisel, SSH port forwarding (OpenSSH, Plink) | Common in testing. Ligolo-ng has the largest gap in public rules found so far |
| 2 | ngrok, Cloudflared, frp | Named in incident reporting. Public rules exist to test |
| 3 | VS Code remote tunnels, Microsoft dev tunnels, DNS tunnelling tools | Legitimate services and a different protocol. Harder to test well |

## Steps to the first release

| Step | Outcome | Effort |
|---|---|---|
| 0 | Method, data format, principles, coverage inventory, contribution process | Done |
| 1 | Lab built, versions recorded, baseline captured | 1 weekend |
| 2 | Ligolo-ng: all variants run, tool page and evidence published | 1 weekend |
| 3 | Chisel: same, public rule tested | 1 weekend |
| 4 | SSH and Plink: same | 1 weekend |
| 5 | Findings offered upstream, first release and write-up | 1 weekend |

The route after the first release is in [`docs/impact-plan.md`](docs/impact-plan.md).

## Decisions before the first release

- **Licence.** Common choices: MIT for scripts and text. The Detection Rule License (DRL 1.1) is
  what SigmaHQ uses for rules. Check the licence of any public rule before copying it here.
- **Primary query language** for published detections: Splunk or Elastic.
- **Telemetry baseline:** which public Sysmon configuration.
- **Name.** `pivot-traces` is a working name.
- **Maintainer name** for the citation file and commit history.
