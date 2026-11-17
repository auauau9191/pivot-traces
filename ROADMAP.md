# Roadmap

Effort figures are estimates for a few hours per weekend.

| Step | Outcome | Effort |
|---|---|---|
| 0 | Repository skeleton, method, prior-art survey | Done |
| 1 | Lab built, versions recorded, baseline captured | 1 weekend |
| 2 | Chisel: all variants run, public rule tested, tool page and evidence published | 1 weekend |
| 3 | Ligolo-ng: same | 1 weekend |
| 4 | SSH and Plink: same | 1 weekend |
| 5 | Own detections for the strongest signals, results matrix, first release and blog post | 1 weekend |
| 6 | DNS tunnelling | Later |

## Decisions before first release

- **Licence.** Common choices: MIT for scripts and text; the Detection Rule License (DRL 1.1) is
  what SigmaHQ uses for rules. Check the licences of any public rule you copy into `rules/`.
- **Primary query language:** Splunk or Elastic.
- **Sysmon baseline configuration.**
- **Name.** `pivot-traces` is a working name.
