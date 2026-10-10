# Executive brief

*Evidence current to 10 October 2026. A two-page summary of the [full report](report.md). Citation numbers link to the [references](references.md), and every figure is in the [evidence register](evidence-register.md).*

## The short answer

Most organisations are using AI. Far fewer can show it is paying off. The evidence says the difference has more to do with what surrounds the tools than with the tools themselves: a clear policy, protected time to learn, small changes, enough capacity to review them, and a way of checking that the output is right. Treat adoption as a change programme in which checking comes first, and judge it on delivered outcomes, not on how much people use it.

## What the evidence says

- **Using it is not the problem.** 88.3% of surveyed organisations use AI tools daily or weekly [[7]](references.md#ref-7), yet 44.7% do not formally measure the impact [[7]](references.md#ref-7). In quality engineering, only 15% of organisations pursuing generative AI have reached enterprise-wide implementation [[8]](references.md#ref-8).
- **Do not trust how it feels.** In a 2025 randomised trial, developers believed AI had made them 20% faster while their tasks took 19% longer [[4]](references.md#ref-4). The trial was small, and its authors say the result may now be out of date, but the gap between belief and measurement is the point.

  ![Bar chart of change in task time with AI. Developers forecast 24% faster and believed afterwards that they were 20% faster, but measured tasks took 19% longer.](assets/metr-belief-vs-measured.svg)
- **Expect a dip before the gain.** DORA, Google Cloud's research programme, describes a temporary fall in productivity while people learn and the surrounding processes catch up, and advises budgeting for it [[2]](references.md#ref-2), [[3]](references.md#ref-3).
- **Foundations decide the result.** DORA names seven organisational capabilities that amplify the benefit [[1]](references.md#ref-1). Prosci found motivation to use AI nearly identical in organisations that were succeeding and those that were stalling, so preparation matters more than enthusiasm [[9]](references.md#ref-9).
- **The cost lands further down the line.** Vendor telemetry reports that, among organisations deepening already high adoption, time in QA rose 300.6% and monthly incidents rose 125.4% [[23]](references.md#ref-23). These are correlations from one vendor, not proof of cause, but they point to review and testing as the place to spend. One survey of leaders in large organisations found that none was very confident AI-generated code would behave correctly once deployed [[29]](references.md#ref-29).

## What you are being asked to decide

1. Endorse a written AI stance with a named executive owner.
2. Approve protected learning time, and an explicit budget for an early dip.
3. Approve a baseline period before any wider rollout.
4. Measure delivered outcomes, and do not set usage or token targets.
5. Name the people accountable for checking AI output, and fund review capacity alongside generation.

The [report's Section 10](report.md#10-conclusions-and-recommendations) gives these with their sources.

## The first steps

The two starting points differ in what comes first, not in the discipline. The timings are indicative and are the author's judgement.

| | An established organisation | A start-up about two years old |
| --- | --- | --- |
| **First move** | Match AI to the right work and people. Split the estate by type of work and by role. | Build the foundations before speed outruns assurance. |
| **Early weeks** | Publish the stance. Capture 8 to 12 weeks of existing delivery and quality data. Survey current use, confidence and concerns. Consult employee representatives and the data protection lead. | Publish the stance and the data rules. Set defaults for small changes and rollback. Name a verification lead. Start recording delivery, review and defect data. |
| **By about month 3 to 6** | Run two to three pilot cells with staggered starts, one champion each, and thresholds agreed in advance. | Treat the first 90 days as the baseline. Pilot agentic QA in a drafting role, behind deterministic checks. |
| **The trap to avoid** | Piloting only on the hardest terrain, then deciding AI does not work. | Letting generation outrun review. |

[Section 5](report.md#5-context-a-established-organisation) and [Section 6](report.md#6-context-b-early-stage-start-up) set out the full plans. Ready-made starting points for the stance, the pilot, the baseline and the decision rule are in the [templates](templates.md), and a [ten-minute readiness check](readiness-check.md) helps choose where to start.

## How sure we are

Moderately. Reasonably well supported: self-report overstates gains, and value is harder to show than use. Suspected but correlational: the early dip, the amplifying effect of foundations, and the downstream cost. Not known: whether agentic QA improves quality. Much of the quantitative evidence is survey data or vendor telemetry, and most of it is correlational. The one controlled trial is small. The agentic QA evidence is the thinnest of all, and the review found no independent controlled study of it. Read the recommendations as informed judgement, not as proven method.

The advice would change if a controlled study in ordinary product teams showed a different pattern, or if the full vendor reports turned out to say something other than their summaries. Those are the things to watch, and the report recommends reviewing the evidence quarterly.
