# Changelog

## v1.1.5 (14 October 2026)

- Reviewed Faros's field guide to measuring token efficiency. It carries no new
  evidence: every figure in it is drawn from the AI Engineering Report 2026,
  already cited as reference 22 and read in full. Its own contribution is a
  measurement framework, so that is what has been folded in.
- New reference 33 links the field guide, with its companion article and the
  gated guide page, both with existing archive captures. A register row records
  it as vendor guidance, grade C, noting its figures restate reference 22.
- Section 8.2 now notes the field guide's four-category lens (adoption,
  productivity, quality, outcomes) as external corroboration of the report's six
  measurement layers and of Principle 3, that token spend is an input to trace to
  delivered work, not an outcome in itself.
- Section 3.4 surfaces three figures from reference 22 that the v1.1.2 trim had
  left to the register: bugs per developer up 54%, up from a 9% rise in the prior
  dataset; median time in pull request review up 441.5%; and lead time from
  commit to production up 480.4%, with the caveat that only about one
  organisation in ten instruments lead time and the figure varies widely. The
  register row for reference 22 gains the same figures.
- No source or grade changed for any existing figure. Evidence remains current
  to 10 October 2026, since the field guide and reference 22 both predate it.

## v1.1.4 (11 October 2026)

- PractiTest 2026 figure now checked against the primary source. The 2026
  State of Testing report turned out to be public, as a web page rather than a
  PDF, and it gives 76.8% for "Do you currently use AI in your organization?".
  New reference 32 links it, with an existing Wayback capture. The figure no
  longer cites reference 21 (TestDino), which stays for the self-healing test
  point.
- Wording in Section 3.1 changed from "76.8% of testers reported using AI" to
  76.8% of respondents saying they used AI in their organisation, which is what
  the question asked. The register notes that the three years of figures are
  worded differently and that the page gives no respondent count or survey
  dates.
- The two starting points are now named the same way throughout: the Company A
  Context and the Company B Context, replacing "Context A" and "Context B".
  The abstract introduces them where it first uses them, rather than leaving
  the definitions to the next paragraph. Section headings, their links in the
  executive brief and readiness check, the table headers and the two timeline
  charts are updated to match. No figure or source changed.
- Section 7 gains a table of DORA's seven capabilities with a reading for each
  context, all marked Judgement because DORA does not split them by type of
  organisation. Section 3.3 points to it, and its list of the seven now starts
  each item with a capital.
- Section 3.6 splits its practitioner guidance into two bullets and explains
  deterministic checks and the bounded behavioural envelope, with an example
  of each taken from the two sources. Both stay grade C.
- Section 9 trimmed from eleven limitations to seven. The three single-source
  caveats (METR, Stanford, the case evidence) are grouped under one heading;
  the "partial access" item, which contradicted its own table, is reworked as
  "how each source was read"; the agentic-QA and test-study items are merged;
  and the duplicate "exclusions" item is dropped, its detail folded into
  Section 2. Section 9 no longer says the 2026 testing figure is second-hand.
- Repetition trimmed elsewhere: the two agentic-QA hypotheses in Section 6.1
  are folded into one that points to Section 6.3, and the Section 3.4 evidence
  note points to Section 9 rather than restating the vendor-and-correlational
  caveat in full.
- Byline date moved to 11 October 2026 to match this edition. The "evidence
  current to 10 October 2026" line is unchanged.
- Copywriting pass over the other documents. The executive brief's confidence
  paragraph no longer calls the agentic-QA evidence weak twice. The decision
  rule in template 4 now says "verification" to match the report's decision
  table. The readiness check and README needed no change.
- Added a markdownlint config (`.markdownlint-cli2.jsonc`) so the formatting
  check runs clean. It turns off the rules that fight the report's deliberate
  style (long prose lines, the citation anchors in references.md, bold
  sub-labels, the survey's 1-to-20 numbering) and ignores the issue-body
  checklist and private notes. README.md and CLAUDE.md gained a trailing
  newline. The
  refresh checklist moves the PractiTest page from the hand-fetch list to the
  scripted one.

## v1.1.3 (10 October 2026)

- Measurement readiness added. Section 8.3 now says that comparing assisted with
  unassisted work needs the work to be labelled, sets out four levels of how
  firm the comparison is, and suggests starting at a pull request label in one
  team and checking a sample by hand. The levels and the start are marked
  Judgement. No figure or source changed.
- Readiness check is now fourteen questions. New question 11 asks whether you
  can say which changes AI helped write; the later questions move up by one and
  the reading table has a new row for it.
- Template 8 added to templates.md: a brief to give an AI assistant that builds
  or improves an AI-adoption dashboard, with definitions, segmentation,
  independent validation and privacy rules. Template 3 and template 6 gain a
  line each on recording and checking the label.

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
