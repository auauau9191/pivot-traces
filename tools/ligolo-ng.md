# Ligolo-ng

- **Tested versions:** none yet
- **Project page:** https://github.com/nicocha30/ligolo-ng
- **Status:** UNVERIFIED

## Claims collected from other sources, to be tested

None of these has been confirmed in this lab.

| # | Claim | Reported by | Planned test |
|---|---|---|---|
| L1 | Agent connects over TLS to port 11601 by default | NHIMG guide | V0 run |
| L2 | A self-signed certificate may use the domain name "ligolo" | NHIMG guide | Read certificate fields in Zeek ssl and x509 logs |
| L3 | In WebSocket mode the agent sends a Windows Chrome 103 user agent unless overridden | NHIMG guide | V3 run, read the HTTP upgrade request |
| L4 | Agent is usually a single binary with no configuration file | NHIMG guide | File-creation events on the pivot host |

## Questions the public sources do not answer

- TLS client fingerprint (JA3 or JA4) of the agent per version, and whether it is stable.
- What the proxy side creates on the operator host (interface, routes), for responders who seize one.
- Sysmon view of the agent: one long connection, or many?
