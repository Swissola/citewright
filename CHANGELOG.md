# Changelog

## Unreleased

- Template 7 added to templates.md: a pulse survey of twenty questions on use,
  perceived effect, trust, learning, concern and workload, with notes on running
  it and reading the results.
- Quarterly reminder added: a scheduled workflow opens an issue on the first of
  January, April, July and October, assigned to the repository owner, with the
  refresh checklist in .github/refresh-checklist.md. It can also be run by hand
  as a dry run.
  The checklist now lists the reports that must be fetched by hand and where to
  save them.

## v1.1.2 (10 October 2026)

Evidence:

- Read in full and linked, with archive captures where the archive would take
  them: the LinearB, DX Q2, Undo, Faros (both), Lightrun, World Quality Report
  and PractiTest 2024 and 2025 reports. Section 2, the Section 9 source-access
  table and the register caveats now say how each source was read.
- The Faros reports settle the earlier ambiguity: pull requests merged without
  any review are up 31.3% (April) and up 76.3% (September), both rises. That
  register row moves from grade C to B.
- Two Faros statements corrected to the full reports: the rise in code churn is
  smaller (71.6% against 861% before), not "improving", and agentic review
  covers 26% of pull requests, over 50% at many companies, not 50% to 80%.
- Caveats added, with no other figure changed: LinearB's 71.6% and 88.3%
  adoption figures measure different things; the DX summary and body disagree on
  average time saved; the World Quality Report's 37% and 52% describe AI
  assistants and copilots for QA tasks; the Undo survey covered 300 engineering
  directors and managers; the Lightrun figures are averages of respondents'
  estimates.
- New Lightrun findings: no leader very confident in AI-generated code once
  deployed, 38% of developer time on debugging and verification, a gap between
  directors and VPs, and AI incident tools stuck at pilot (Sections 3.1, 3.4 and
  8.4, the executive brief and three register rows).

Reading and use:

- New readiness-check.md: thirteen questions and a guide to reading the pattern
  of answers.
- New "how firm" table at the start of Section 9, repeated in short in the
  executive brief.
- Section 3 trimmed by about 15% (2,860 to about 2,460 words), mostly secondary
  figures. Detail left out of the text stays in the evidence register.
- Three charts and two phase timelines added as SVGs in assets/: the METR
  belief and measurement gap, a schematic J-curve, and the phases for each
  context. They appear in Sections 3.2, 3.3, 5.2 and 6.2 and the executive
  brief.

Housekeeping: .gitignore now excludes .playwright-mcp/. No source or grade
changed apart from the Faros row above.

## v1.1.1 (10 October 2026)

- New [executive-brief.md](executive-brief.md): a two-page summary for decision
  makers, using only figures already in the report and register.
- New [templates.md](templates.md): six starting points (AI stance, pilot
  hypothesis card, baseline sheet, decision rule and log, verification lead,
  pull request addition), all labelled as the author's judgement.
- README and the top of the report point to both.
- Reference 3 now also links the full DORA ROI report PDF, with an archive
  capture. Reference 28 now has an archive capture, so every source URL has one.
- Section 3.5 and the evidence register give the Stack Overflow figure on
  optional AI use as "about three in ten", which is what the available source
  says. The decimal could not be traced.
- Adjacent citations are now separated by a comma, which also clears a
  markdownlint warning. No citation was added or removed.
- Both workflows now use actions/checkout v7.
- The Faros unreviewed-merge ambiguity stands. The full Faros reports are gated
  and could not be read.

## v1.1.0 (10 October 2026)

- Wayback Machine capture links added beside 33 of the 34 source URLs in
  references.md.
- Report restructured and rewritten for readability. The old Section 3.7
  ("Evidence from the last six months") is dissolved into Sections 3.1, 3.3,
  3.4 and 3.5, with a new Section 3.4 on the downstream cost of faster output.
  Sections 3.5 to 3.7 are renumbered. No figure, source or grade changed.
- Section 3.1 dated the McKinsey survey to September 2026. The article is dated
  25 August 2026, so the date is removed.
- Sections 2 and 9 and one evidence register caveat updated to say which
  sources were read in full (DORA ROI report, METR 2025 paper, both agentic
  pull request papers, McKinsey, DX Q1 and Q4) and which were not.
- Illustrative examples added: new Section 4.1 (the eight practices in
  practice), a pilot cell in Section 5, an agentic QA walk-through in
  Section 6.3 and two worked readings of the decision rule in Section 8.4.
  All are labelled as the author's judgement.
- Test oracle defined in plain terms at first use (Section 3.6). Agentic QA
  reframed as one part of adoption: scope note in Section 1, new intro to
  Section 3.6, Section 6.1 reordered so foundations and growth lead, and
  Section 6.3 retitled "Agentic QA within the adoption plan".
- Comprehension pass: terms list added to Section 1 (agent, pull request,
  greenfield and brownfield, change failure rate, oracle, DORA), byline date put
  in British format, the METR "what has not changed" paragraph moved from 3.4
  to 3.2, and "squad" and a few other terms made plainer.
- Section 9 item 5 (source access) turned into a table, and a voice pass over
  Sections 4 to 10 for plainer wording. No figure, source or grade changed.

## v1.0.0 (10 October 2026)

- First edition. Evidence current to 10 October 2026.
- Report split into report.md, references.md and evidence-register.md.
- References 1 to 31 form one numbered list, and every in-text citation links
  to its entry.
- The October 2026 additions to the evidence register are merged into the
  main table.
- Contents list and linked section cross-references added to the report.
