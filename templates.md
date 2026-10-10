# Templates

Six starting points for putting the report's recommendations to work. They are the author's judgement (*Judgement*), not findings from a study, and they are not drawn from any particular organisation. Change anything that does not fit. Text in {braces} is a placeholder, and the example wording is there to show the level of detail to aim for.

| Template | Report section it follows |
| --- | --- |
| [1 The one-page AI stance](#1-the-one-page-ai-stance) | [Practice 1, Section 4](report.md#4-practices-common-to-both-contexts) |
| [2 The pilot hypothesis card](#2-the-pilot-hypothesis-card) | [Section 5.2](report.md#52-phased-plan) and [Section 8.4](report.md#84-judging-an-initiative) |
| [3 The baseline sheet](#3-the-baseline-sheet) | [Section 8](report.md#8-baselining-and-evaluation-framework) |
| [4 The decision rule and log](#4-the-decision-rule-and-log) | [Section 8.4](report.md#84-judging-an-initiative) |
| [5 The verification lead](#5-the-verification-lead) | [Section 6.2](report.md#62-phased-plan) and [Section 6.3](report.md#63-agentic-qa-within-the-adoption-plan) |
| [6 The pull request addition](#6-the-pull-request-addition) | Practices 3 and 5, [Section 4](report.md#4-practices-common-to-both-contexts) |

## 1 The one-page AI stance

The aim is a page people will read. It says what is allowed, what is not, and who owns the result. DORA's AI stance capability is about clarity and communication, not about what the policy says, so keep it short and say it plainly [[1]](references.md#ref-1).

```text
AI at {organisation}: our stance
Owner: {named executive}      Version: {number}      Reviewed: {date}, next review {date}

What we encourage
- {Use AI on work such as drafting, reviewing and test design.}
- {Share what worked and what did not, at a regular time and place.}

Approved tools
- {Tool names, and what each is approved for.}

Data rules
- {Customer data, personal data and anything confidential: what may and may not go into which tool.}
- {Who to ask if unsure.}

Who owns the result
- Whoever merges or ships a change owns it, whether a person or an agent wrote it.
- {Output that has not been checked is not finished.}

What we do not do
- We do not set usage or token targets. How much someone uses AI is not a measure of their work.
- {Any other firm limit.}

If you have concerns
- {About your job, your skills or the tools: talk to your supervisor first, or {name or role}.}
```

## 2 The pilot hypothesis card

One card per pilot cell, completed before the pilot starts. If the hypothesis cannot be written in a sentence, the pilot is not ready.

```text
Pilot: {name}         Cell: {team, workstream}         Champion: {name}
Start: {date}   Window: {length, agreed in advance}   Later-starting comparison cell: {name}

Hypothesis
{Using AI for X will change Y in direction Z, without making Q worse.}
Example: AI-assisted test design will shorten the time from requirement to first
reviewed test set without raising escaped defects.

Work in scope: {types of ticket or task}
Work out of scope: {and why}

Measures (from the baseline sheet)
- Flow: {measure}
- Quality and stability: {measure}
- People: {measure}

Thresholds, agreed before we look at results
- Scale if: {condition}
- Pause if: {condition}
- Stop or redesign if: {condition}

Review capacity planned: {who reviews, and how much time they have}
Sign-off: {sponsor}, {date}
```

## 3 The baseline sheet

Fill this in before anyone gets wider access. In an established organisation, use 8 to 12 weeks of existing history. In a start-up, the first 90 days of newly recorded data is the baseline. Record AI-assisted, agent-created and unassisted changes separately where you can, since a blended average describes none of them [[7]](references.md#ref-7).

| Measure | Layer | Where it comes from | Baseline value | Date captured | Owner |
| --- | --- | --- | --- | --- | --- |
| Lead time by phase | Flow | Source control, work tracker | {value} | {date} | {name} |
| Pickup and review time | Flow | Source control | {value} | {date} | {name} |
| Change size | Flow | Source control | {value} | {date} | {name} |
| Share of changes merged without review | Flow | Source control | {value} | {date} | {name} |
| Time in QA | Flow | Work tracker | {value} | {date} | {name} |
| Change failure rate | Quality and stability | Pipeline, incident data | {value} | {date} | {name} |
| Escaped defects | Quality and stability | Defect data | {value} | {date} | {name} |
| Incidents per change | Quality and stability | Incident data | {value} | {date} | {name} |
| Trust and confidence in AI output | People | Pulse survey | {value} | {date} | {name} |
| Concern about skills or job security | People | Pulse survey | {value} | {date} | {name} |
| Licence and usage cost | Cost and value | Finance | {value} | {date} | {name} |

The measures follow the layers in [Section 8.2](report.md#82-measures-by-layer). Leave out any you cannot get rather than guessing, and note the gap.

## 4 The decision rule and log

Agree the rule before the pilot, then record each decision against it. The thresholds are for you to set locally.

```text
Decision rule (agreed {date} by {names})
Scale:            flow improves or holds; quality and stability hold; trust stable or rising.
Pause:            flow improves but quality or stability worsens. Fix checking and review
                  capacity before scaling.
Stop or redesign: flow and quality flat after the learning window; trust falling.
Mixed segments:   continue only in the segments that pass.
Our thresholds:   {numbers or conditions for each measure}
```

```text
Decision log
Date: {date}      Initiative: {name}      Decided by: {names}
Evidence looked at: {baseline comparison, delivered data, survey, sampled work}
Result against the rule: {scale, pause, stop or redesign, or mixed}
Decision and reason: {one or two sentences}
What would change this decision: {condition}
Next review: {date}
```

## 5 The verification lead

For a start-up, this is the first role to name. In a larger organisation, the same duties can sit with a small group. The lead owns the oracle, meaning the source of truth that says what correct looks like ([Section 3.6](report.md#36-quality-engineering-and-agentic-testing)).

```text
Verification lead: {name}      Deputy: {name}      Reports to: {name}

Owns
- For each product behaviour that matters, a written description of what correct looks like.
- The decision on which agent-drafted tests are accepted or rejected.
- The set of cases the product's own AI components are tested against, where there are any.
- The known-defect check: planting known faults to see whether the test suite catches them.

Does not do
- Accept a test because the agent says it passes.
- Hold the knowledge alone. Oracles are written down so someone else can pick them up.

Reviews, every {quarter}
- What agentic QA cost, what it caught and what it needed in maintenance.
- Whether the known-defect check still catches what it should.
```

## 6 The pull request addition

A few lines added to the pull request template make the two most useful habits routine. They give a named owner for every change, and they let you separate AI-assisted work from the rest when you measure.

```text
Created or assisted by AI:  [ ] no   [ ] assisted   [ ] created by an agent
Owner of this change (a named person): {name}
What this was checked against: {requirement, test, reviewer's reading}
Size and scope kept small enough to review properly:  [ ] yes
```
