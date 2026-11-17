# Contributing

Thank you for helping. There are three ways to contribute. None of them needs code.

## 1. Add to the coverage inventory

Open an issue with the "Inventory addition" template. Give the rule's title, its source and a
link. State what the rule keys on if you have read it.

## 2. Submit a test result

1. Read [`docs/methodology.md`](docs/methodology.md) and [`docs/principles.md`](docs/principles.md).
2. Run the test case in an isolated lab that you own.
3. Add your evidence file to `evidence/`, named as described in `evidence/README.md`.
4. Add one row per detection to `tests/matrix.csv`. The columns are explained in
   [`docs/data-format.md`](docs/data-format.md).
5. Run `python3 scripts/matrix_report.py` and commit the regenerated files.
6. Open a pull request. The automated check must pass.

If you do not use git, open an issue with the "Test result" template and attach the evidence.

## 3. Challenge a result

Repeat the test. If your outcome differs, submit it as a new row with your handle. Do not edit the
original row. Say in the pull request what differed in your lab.

## What is not accepted

- Data from client networks, employer networks or training-provider labs.
- Evidence that contains real hostnames, usernames, keys, tokens or public IP addresses.
- Instructions for using the tools, or modified versions of them.
- Results without evidence.

## Review

A maintainer checks that the evidence supports the row, that the file is sanitised, and that the
test followed the method. Reviews aim to be done within two weeks.

## Conduct

Be respectful and specific. Criticise methods and results, not people. This project follows the
[Contributor Covenant](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).
