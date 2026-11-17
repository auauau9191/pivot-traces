# SSH port forwarding (OpenSSH and Plink)

- **Tested versions:** none yet
- **Status:** UNVERIFIED

SSH is a legitimate administration tool, so traces here are mostly grade B or C. The value of this
page is in showing which combinations separate forwarding from ordinary use.

## Public detections to test

| # | Detection | Source | Planned test |
|---|---|---|---|
| S1 | Port Forwarding Activity Via SSH.EXE | SigmaHQ | Local, remote and dynamic forwarding, V0 to V4 |
| S2 | Suspicious Plink Port Forwarding | SigmaHQ | Remote forwarding with Plink, V0 to V4 |
| S3 | Potential SSH Reverse Port Forwarding | Elastic | OpenSSH for Windows, remote forwarding |

## Questions the public sources do not answer

- Forwarding configured in a config file instead of on the command line: what is left to detect?
- Server-side evidence in sshd logs at default and raised log levels.
- Listening-socket and loopback-connection events as a behavioural signal on Windows and Linux.
