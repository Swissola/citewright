# Readiness check

Thirteen questions to answer before choosing a first move. It takes about ten minutes with two or three people in the room, ideally from engineering, quality and whoever looks after people and policy. It is the author's judgement (*Judgement*), built around the report's findings, and it is not a validated survey instrument. Answer for what is true today, not for what is planned.

For each question, answer **yes**, **partly** or **no**. If people disagree, take the less comfortable answer and write down why.

## The questions

**Stance and data**

1. Is there a short written statement of what AI use is allowed, with data rules and a named owner? (DORA's first capability is a clear and communicated AI stance [[1]](references.md#ref-1).)
2. Can the people who would use AI reach the internal data and documents they need, in an approved way? [[1]](references.md#ref-1)
3. Is that data in reasonable shape: findable, current, with someone responsible for it? [[1]](references.md#ref-1)

**Engineering foundations**

4. Is code, test code and configuration all kept under version control, with changes tracked and reversible? [[1]](references.md#ref-1)
5. Do changes usually go out small, and can you say how big a typical one is? [[1]](references.md#ref-1)
6. Can teams say who their work is for, and how they would know it had helped them? [[1]](references.md#ref-1)
7. Do the internal platforms and pipelines teams rely on work reliably and quickly? [[1]](references.md#ref-1)

**Checking and capacity**

8. Is there a named person who decides what correct looks like for the behaviours that matter most? ([Section 3.6](report.md#36-quality-engineering-and-agentic-testing) calls this owning the oracle.)
9. Do code reviews usually happen within a normal working day, and do you know the actual wait? [[7]](references.md#ref-7)

**Baseline and measurement**

10. Could you pull the last few months of lead time, review wait, change failure rate and escaped defects without a special project? [[7]](references.md#ref-7)
11. Do you judge AI use by delivered outcomes, not by how much people use it? [[14]](references.md#ref-14)

**People**

12. Have people been told plainly what AI means for their jobs and skills, and do supervisors have honest answers ready? [[9]](references.md#ref-9), [[11]](references.md#ref-11)
13. Is there protected time to learn, on real work? [[12]](references.md#ref-12)

## Reading the answers

Count the answers in each group. Do not add them up into one number, because a single score hides where the gap is. The patterns below are a guide to which plan to start from, and they are judgement.

| Pattern | What it suggests | Start from |
| --- | --- | --- |
| Mostly **no** or **partly** on questions 4 to 7 and 10 | The foundations are thin and there is little history to measure from. Speed will arrive before assurance does. | [Section 6](report.md#6-context-b-early-stage-start-up): stance, foundations and instrumentation first, whatever the age of the company |
| Foundations mostly **yes**, but **no** or **partly** on questions 12 and 13 | The tools could work but the people are not yet ready. Enthusiasm may be masking uneven confidence. | [Section 5](report.md#5-context-a-established-organisation): segment by work and role, then build through champions and protected time |
| **No** on questions 8 and 9 | Nobody owns checking, and review is already a queue. More generated change will make both worse. | Fix these before any agentic QA ([Section 6.3](report.md#63-agentic-qa-within-the-adoption-plan)) |
| **No** on questions 1 and 11 | There is no stance and no way to tell whether any of it is working. | Practices 1 and 8 in [Section 4](report.md#4-practices-common-to-both-contexts) are the whole plan for now |
| Mostly **yes** throughout | You are better placed than most. | Pilot against a baseline, set thresholds first, and review quarterly |

Most organisations will not look like either context in the report. A large company can have the foundations of a start-up in one corner and the habits of an established organisation in another, so run the check for each part that would act on its own.

## What to do with it

Write the answers down with the date, put the three weakest questions at the top of the plan, and run the check again after the first pilot. The [templates](templates.md) cover the stance, the baseline and the decision rule, which between them answer questions 1, 10 and 11.
