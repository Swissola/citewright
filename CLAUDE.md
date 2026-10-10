# citewright

Evidence-graded, fully cited review of AI adoption in software organisations.
Evidence current to 10 October 2026.

## Hard rules

- British English. No em dashes.
- Anonymity: the two contexts stay generic ("an established organisation",
  "a start-up about two years old"). Never add names, sectors, products, team
  sizes, tools, regulators or people that could identify a real organisation.
- Never invent a source or figure. Every figure needs a numbered citation that
  resolves to references.md and a row in evidence-register.md. If a source
  cannot be opened and read, say so instead of citing it.
- Prefer primary sources. Where primary and secondary disagree, the primary
  wins and the conflict is noted.
- The author's synthesis carries the tag (Judgement). Evidence grades A, B, C
  are defined in README.md.
- Never edit LICENSE. Never push, tag or change visibility unless asked.
- Before the first commit, check git config user.email is a noreply address.
- Private notes go in .local/ (git-ignored), never in tracked files.

## Conventions

- Keep sections numbered as in report.md. Add a dated CHANGELOG.md entry for
  every substantive change. Run link and formatting checks before committing.
- Expected files: README.md, report.md, evidence-register.md, references.md,
  CHANGELOG.md, CITATION.cff, LICENSE.