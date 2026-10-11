The evidence in this repository is dated. This is the quarterly check that it still stands. Tick each box, note anything that changes in `CHANGELOG.md`, and close the issue when the refresh is done or consciously skipped.

## 1 Look for newer editions of what the report cites

- [ ] DORA: a 2026 flagship report, new capabilities, or an update to the ROI report
- [ ] METR: any new controlled trial or survey after the 2026 releases
- [ ] DX: the latest quarterly AI impact report
- [ ] Faros: a newer engineering report or follow-up
- [ ] LinearB: the next annual benchmarks report
- [ ] McKinsey: a newer State of AI survey
- [ ] Stack Overflow: the developer survey results and its AI section
- [ ] World Quality Report: the next edition
- [ ] PractiTest: the latest State of Testing report
- [ ] Lightrun, Undo and Prosci: newer surveys or case studies
- [ ] Academic work on agent-written code and tests (MSR, arXiv): peer-reviewed versions of the preprints cited
- [ ] ICO and other UK guidance on AI and data protection: anything newer than the 2023 summary cited

## 2 Fetch what needs a person

Some reports sit behind a sign-up form, or block automated downloads, so they have to be fetched by hand. Save each PDF in `.local/sources/` (git-ignored) and ask Claude to check the figures against it. Where a link below is a form, the report's registration page is in `references.md`.

- [ ] Faros AI Engineering Report (registration form): https://www.faros.ai/research/ai-acceleration-whiplash
- [ ] Faros follow-up report (registration form): https://www.faros.ai/research/speed-trap
- [ ] Lightrun State of AI-Powered Engineering (registration form): https://lightrun.com/ebooks/state-of-ai-powered-engineering-2026
- [ ] World Quality Report (registration form; the direct PDF link is in reference 8 and opens in a browser, but not to scripts): https://www.opentext.com/world-quality-report
- [ ] McKinsey State of AI (opens in a browser, not to scripts): https://www.mckinsey.com/featured-insights/mckinsey-global-surveys/the-state-of-ai

The DORA, DX, LinearB, Undo and earlier PractiTest reports download directly, and can be fetched by script. The PractiTest 2026 report is a web page rather than a PDF (https://www.practitest.com/state-of-testing/), so save the page text and check whether a later edition has replaced it.

## 3 Check what is already there

- [ ] Run the link check workflow and look at the warnings
- [ ] Check each archive link in `references.md` still opens
- [ ] Re-read the register caveats. Has any source been revised, retracted or superseded?
- [ ] Re-open the gated reports that were read in full and confirm the figures still match their current versions
- [ ] Look at the open questions in Section 9. Has any gap been filled?

## 4 If something changed

- [ ] Prefer the primary source. Do not edit a figure without reading the source itself
- [ ] Update `references.md` and `evidence-register.md`, and keep the grade rules in `README.md`
- [ ] Update the text, the charts and the executive brief wherever the figure appears
- [ ] Re-grade only where the evidence has changed, and say why in the register caveat
- [ ] Update the "evidence current to" date in `README.md`, `report.md`, `executive-brief.md`, `references.md` and `CLAUDE.md`

## 5 Before publishing

- [ ] Run the private-terms sweep, then the em dash and email checks
- [ ] Add a dated `CHANGELOG.md` entry and bump the edition in `README.md` and `CITATION.cff`
- [ ] Tag, push and create a release only when you have decided to

If nothing relevant has changed, add a one-line note here and close the issue.
