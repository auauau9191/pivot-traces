# Chisel

- **Tested versions:** none yet
- **Project page:** https://github.com/jpillora/chisel
- **Status:** UNVERIFIED

## Claims collected from other sources, to be tested

None of these has been confirmed in this lab.

| # | Claim | Reported by | Planned test |
|---|---|---|---|
| C1 | The HTTP upgrade request carries `Sec-WebSocket-Protocol: chisel-v3` | NHIMG guide | Read the upgrade request in the packet capture, V0 to V3 |
| C2 | Inner SSH banners read `SSH-chisel-v3-client` and `SSH-chisel-v3-server` | NHIMG guide | Check whether they are visible on the wire or only inside the tunnel |
| C3 | Default keepalive interval of 25 seconds | NHIMG guide | Measure packet timing on an idle tunnel |
| C4 | Server falls back to port 8080 | NHIMG guide | V0 run |
| C5 | SigmaHQ rule fires on image name `chisel.exe` or on client/server command-line strings | SigmaHQ | Run the rule against V0 to V4 |

## Questions the public sources do not answer

- Which of C1 to C3 remain visible when the tool's own TLS option is used?
- What does Sysmon network telemetry show for a long-lived tunnel compared with normal browsing?
- Do any traces differ between the Windows and Linux builds?
