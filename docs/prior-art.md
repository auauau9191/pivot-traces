# Prior art and the gap

Checked on 17 November 2026. This is a first survey, not an exhaustive review. Update it before
each release.

## What exists

| Source | What it offers | Limit |
|---|---|---|
| [SigmaHQ: PUA - Chisel Tunneling Tool Execution](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_pua_chisel/) | Process-creation rule on the image name `chisel.exe` or on command-line strings | Strings only. No network or behavioural signal. The rule itself notes possible false positives |
| [SigmaHQ: Port Forwarding Activity Via SSH.EXE](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_ssh_port_forward) and [Suspicious Plink Port Forwarding](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_plink_port_forwarding/) | Process-creation rules for SSH and Plink forwarding flags | Not yet reviewed in detail here |
| [Elastic: Potential SSH Reverse Port Forwarding](https://detection.fyi/elastic/detection-rules/windows/command_and_control_openssh_reverse_port_forwarding/) | Prebuilt rule for OpenSSH reverse forwarding on Windows | Not yet reviewed in detail here |
| [Elastic: Potential Protocol Tunneling via Chisel Server](https://detection.fyi/elastic/detection-rules/_deprecated/command_and_control_linux_chisel_server_activity/) | Linux rule for a Chisel server | Listed as deprecated |
| [NHIMG: Detecting Ligolo-ng, Chisel and frp](https://nhimg.org/ligolo-ng-chisel-and-frp-detection-guide) | Host, network and configuration indicators for three tools | No tested rules, sample logs, packet captures, TLS fingerprints or tool versions |
| [LOTTunnels](https://lottunnels.github.io/) | Catalogue of 82 tunnelling tools and how they are abused | The index carries no detection content. Per-tool pages not yet reviewed |
| Vendor threat pages (example: [Hunt.io on Ligolo-ng](https://hunt.io/malware-families/ligolo-ng)) | General descriptions | No concrete indicators |

## The gap this project fills

1. **Proof.** Public indicators are rarely published with the evidence that supports them.
2. **Versions.** Tools change. Few sources say which version a claim was tested on.
3. **Robustness.** Most public rules match file names and command-line strings. Nobody publishes
   what happens to them after a rename or a port change.
4. **One place.** Host traces, network traces, rules and evidence for the same test run, together.

## Still to check

- Per-tool pages on LOTTunnels.
- Vendor EDR query libraries and the Splunk Security Content repository.
- Incident write-ups that include these tools (for example The DFIR Report).
- Conference talks on tunnel detection from the last two years.
