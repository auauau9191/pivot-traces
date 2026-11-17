# Principles

Community comparison projects in security are useful and are also easy to misread. These rules
exist so that a result here is never taken for more than it is.

## What a result means

A row in the results says: this detection, at this version, evaluated against this telemetry,
fired or did not fire for this tool version, scenario and variant, in one lab, on one date.

## What a result does not mean

- It does not rank vendors or products. This project tests public rules, not commercial products.
- "Fired" does not mean the rule is good. A rule can fire in a lab and be too noisy for production.
- "Missed" does not mean the rule is bad. It may be scoped to a case the test did not cover.
- A small lab baseline cannot prove a low false-positive rate.

Every published summary must repeat these limits next to the numbers.

## How the project stays fair

1. **Open criteria.** The grading rules are in [`methodology.md`](methodology.md). Nothing is
   scored by private judgement.
2. **Evidence or it is not recorded.** Every fired or missed result links to a file that a reader
   can open.
3. **Results can be challenged.** A repeat test with a different outcome is recorded beside the
   first, not in place of it.
4. **Rule authors are told first.** When a public rule misses a variant, the finding is offered to
   the rule's maintainers as an issue or pull request before it is promoted anywhere.
5. **No paid tier.** The data, method and tooling stay free. The project sells nothing.
6. **Defensive scope.** The project does not publish tool usage instructions or modified tools.

## Lessons taken from other projects

- The EDR Telemetry project showed that a single shared data file with an evidence rule can
  attract wide contribution. Public criticism of that project centred on unclear scoring criteria,
  on readers treating the table as a product ranking, and on a commercial offering attached to it.
  Rules 1, 5 and the "does not mean" list respond to those points.
- LOLBAS and LOTTunnels showed that a catalogue with one page per tool is easy to cite. Tool pages
  here follow that shape.
