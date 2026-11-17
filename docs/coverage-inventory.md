# Public rule coverage inventory

Which public rule sets carry a detection for which tunnelling tool.

- **Last checked:** 17 November 2026.
- **Method:** web searches and rule-browser listings. This is a first pass, not a full audit of
  each repository. "None found" means none was found in this pass. It does not prove that no rule
  exists.
- **Depth:** "reviewed" means the rule logic was read. "listed" means only the title was seen.

## By tool

| Tool | SigmaHQ | Elastic | Splunk | Seen in public incident reporting |
|---|---|---|---|---|
| Ligolo-ng | None found | None found | None found | Named in CISA advisory AA25-071a (Medusa ransomware) |
| Chisel | 1 reviewed (process creation, file name and command-line text), plus 1 listed for SharpChisel | 1 listed (Linux server), marked deprecated | None found | Not checked yet |
| frp | 1 listed (process creation) | Not checked | Not checked | Not checked yet |
| SSH port forwarding | 4 listed under the protocol-tunnelling tag, 1 of them reviewed (`ssh.exe` with a remote-forward flag) | 1 listed (reverse port forwarding, Windows) | Not checked | Not checked yet |
| Plink | 2 listed, 1 of them reviewed (file description and a remote-forward flag) | 1 listed (remote desktop tunnelling) | Not checked | ReliaQuest reports more than 200 criminal-forum mentions |
| ngrok | 4 listed | Not checked | 2 listed (Linux endpoint, network) | ReliaQuest reports more than 400 criminal-forum mentions |
| Cloudflared | 4 listed | Not checked | 2 listed (execution, network connection) | Named in CISA advisory AA25-071a |
| Microsoft dev tunnels | 2 listed | Not checked | Not checked | Not checked yet |
| VS Code remote tunnels | 1 listed | Not checked | Not checked | ReliaQuest cites one observed incident |
| LocaltoNet | 2 listed | Not checked | Not checked | Not checked yet |
| NPS, IOX, 3proxy | 1 listed each | Not checked | Not checked | Not checked yet |

## What stands out

1. **Ligolo-ng has the largest visible gap.** It appears in a government ransomware advisory, and
   this pass found no public rule for it in the three rule sets.
2. **The rules reviewed so far are host-side string matches.** None of the three rules read in
   full uses a network or behavioural signal.
3. **Coverage follows the commercial services.** ngrok and Cloudflared have the most rules.
   Self-hosted tools have the fewest.

## Sources

- [Sigma rules tagged attack.t1572](https://detection.fyi/tags/attack.t1572/)
- [SigmaHQ: PUA - Chisel Tunneling Tool Execution](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_pua_chisel/)
- [SigmaHQ: HackTool - SharpChisel Execution](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_hktl_sharp_chisel/)
- [SigmaHQ: PUA - Fast Reverse Proxy (FRP) Execution](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_pua_frp/)
- [SigmaHQ: Port Forwarding Activity Via SSH.EXE](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_ssh_port_forward)
- [SigmaHQ: Suspicious Plink Port Forwarding](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_plink_port_forwarding/)
- [Elastic: Potential SSH Reverse Port Forwarding](https://detection.fyi/elastic/detection-rules/windows/command_and_control_openssh_reverse_port_forwarding/)
- [Elastic: Potential Remote Desktop Tunneling Detected](https://detection.fyi/elastic/detection-rules/windows/command_and_control_rdp_tunnel_plink/)
- [Elastic: Potential Protocol Tunneling via Chisel Server (deprecated)](https://detection.fyi/elastic/detection-rules/_deprecated/command_and_control_linux_chisel_server_activity/)
- [Splunk: Reverse Network Proxy analytic story](https://research.splunk.com/stories/reverse_network_proxy/)
- [Splunk: Windows Potential Cloudflared Tunnel Execution](https://research.splunk.com/endpoint/2e29b58e-0f5a-42fc-b435-0fdce8862831)
- [CISA AA25-071a: #StopRansomware: Medusa Ransomware](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a)
- [ReliaQuest: Protocol tunneling tools and techniques](https://reliaquest.com/blog/protocol-tunneling-tools-and-techniques/)

## Still to do

- Audit the SigmaHQ, Elastic and Splunk repositories directly, tool by tool.
- Add Microsoft Sentinel and Chronicle community rules.
- Record for each rule what it keys on (file name, command line, network, behaviour).
