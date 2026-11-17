# Route to adoption

Reach comes from being useful to people who maintain rules and run detection teams. This plan
puts usefulness first and publicity second.

| Stage | Goal | Done when |
|---|---|---|
| 1. Credible core | First release with verified results for three tools | Every claim on three tool pages links to evidence |
| 2. Give back upstream | Findings offered to rule maintainers | Issues or pull requests opened with SigmaHQ for each documented miss, and detection notes offered to LOTTunnels |
| 3. Second lab | One outside contributor repeats a test case | A row in the results carries a second contributor |
| 4. Wider scope | Tier 2 tools added | Results exist for ngrok, Cloudflared and frp |
| 5. Share the method | Write-up and a community talk | One long-form post, and a submission to a local BSides or similar |
| 6. Keep it current | Re-test on new tool and rule versions | A dated re-test for each tier 1 tool every six months |

## What to measure

- Upstream changes that cite a result from this project.
- Number of independent contributors with at least one accepted result.
- Share of tier 1 and tier 2 tools with verified results.

Stars and followers are not goals. They follow from the three measures above.

## Risks

| Risk | Response |
|---|---|
| Results are read as a product ranking | The limits in [`principles.md`](principles.md) appear beside every summary |
| A result is wrong | Repeat tests are recorded beside the original. Corrections are welcomed and credited |
| The project becomes a how-to for intruders | No tool usage instructions and no modified tools. Variants stay within documented options |
| The maintainer runs out of time | Tier 1 is small on purpose. Later tiers depend on contributors |
