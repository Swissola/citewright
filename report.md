# AI Adoption in Software Organisations: An Evidence-Based Comparison of Established and Early-Stage Contexts

10 October 2026 · Swissola

*Short on time? Start with the [executive brief](executive-brief.md). A [ten-minute readiness check](readiness-check.md) and ready-made [templates](templates.md) follow from the plans in this report.*

## Contents

- [Abstract](#abstract)
- [1 Introduction and scope](#1-introduction-and-scope)
- [2 Method and evidence grading](#2-method-and-evidence-grading)
- [3 Findings: what the evidence shows](#3-findings-what-the-evidence-shows)
- [4 Practices common to both contexts](#4-practices-common-to-both-contexts)
- [5 Context A: established organisation](#5-context-a-established-organisation)
- [6 Context B: early-stage start-up](#6-context-b-early-stage-start-up)
- [7 Comparative analysis](#7-comparative-analysis)
- [8 Baselining and evaluation framework](#8-baselining-and-evaluation-framework)
- [9 Limitations and evidence gaps](#9-limitations-and-evidence-gaps)
- [10 Conclusions and recommendations](#10-conclusions-and-recommendations)

## Abstract

Most organisations are now using AI. Far fewer can show it is paying off, and the evidence says the gap has less to do with the tools than with what surrounds them. A staged approach that checks its own results is the best-supported way to drive adoption in both contexts, though the two organisations need different first moves. The established company has to change habits across an uneven workforce. The early-stage company has to build its foundations before speed outruns assurance.

**Purpose.** To compare how AI adoption, including agentic quality assurance, should be driven in (A) an established organisation and (B) a start-up about two years old.

**Method.** A structured review of primary and secondary sources current to 10 October 2026. Each source is graded for evidence strength ([Section 2](#2-method-and-evidence-grading)). Recommendations are labelled as the author's judgement wherever no study directly supports them.

**Principal findings.**

- Adoption is no longer the constraint. 88.3% of surveyed organisations use AI tools daily or weekly [[7]](references.md#ref-7), yet only 15% of organisations pursuing generative AI in quality engineering have reached enterprise-wide implementation [[8]](references.md#ref-8).
- Self-reported gains overstate measured gains. In a 2025 randomised trial, developers believed AI had made them 20% faster while tasks took 19% longer [[4]](references.md#ref-4). The authors judged their 2026 follow-up unreliable [[5]](references.md#ref-5).
- AI amplifies the system it enters. DORA, Google Cloud's research programme on software delivery, identifies seven organisational capabilities that amplify the benefit [[1]](references.md#ref-1) and describes a temporary dip in productivity before returns arrive [[2]](references.md#ref-2), [[3]](references.md#ref-3).
- Preparation, not motivation, separates success from stalling. Prosci found motivation to use AI nearly identical in succeeding and stalling organisations [[9]](references.md#ref-9).
- Speed arrives first and the bill lands downstream. The newest telemetry shows output rising alongside more time in QA, more incidents and more code merged without review ([Section 3.4](#34-speed-arrives-and-the-cost-lands-downstream)).
- Agent-written code is often under-tested. In one 2026 preprint of 4,882 agent-generated pull requests, agents included test changes in only 49.6% of those that changed code under test [[17]](references.md#ref-17).

**Recommendations.** Eight practices apply in both contexts ([Section 4](#4-practices-common-to-both-contexts)). Context A starts by segmenting its estate and piloting where AI performs best ([Section 5](#5-context-a-established-organisation)). Context B starts by fixing foundations and building evaluation into the product ([Section 6](#6-context-b-early-stage-start-up)). Both should baseline first, measure delivered outcomes rather than usage, and decide on thresholds agreed in advance ([Section 8](#8-baselining-and-evaluation-framework)).

**Confidence.** Moderate. Much of the evidence is survey data or vendor telemetry, and most of it is correlational ([Section 9](#9-limitations-and-evidence-gaps)). The most recent evidence is almost all vendor-produced. It points to per-change risk stabilising while QA and operational load keep rising.

## 1 Introduction and scope

Adoption has run well ahead of the measurement of its value: 44.7% of surveyed organisations do not formally measure AI's impact [[7]](references.md#ref-7). What to do about that depends on where an organisation starts, so this report looks at two starting points.

**Context A: established organisation.** A mature organisation with a sizeable technology function, organised into several workstreams that work in different ways. It runs a mix of older and newer systems, some of them recently consolidated, and its people hold a wide range of skills and attitudes to AI.

**Context B: early-stage start-up.** A company about two years old, growing quickly, where leadership wants agentic quality assurance and AI good practice built in as foundations. Its product is likely to contain AI itself, and to handle sensitive personal data.

**Questions addressed.**

1. How should adoption be driven in each context, and what exactly should be done?
2. What should be done identically in both?
3. What should differ, and why?
4. How should each context baseline its starting position?
5. How should initiatives and improvements be judged?

**Scope.** The review covers software engineering and quality assurance, with the UK as the primary jurisdiction. It reflects evidence available to 10 October 2026. Agentic quality assurance is treated as one part of AI adoption, not the whole of it. The report is not legal advice, and it does not evaluate specific commercial tools.

**Terms.** A few words recur and are used in a fixed sense.

- **Agent, agentic.** AI that takes several steps towards a goal, such as writing code, opening a pull request or running tests, with little step-by-step direction. Agentic QA means using agents in quality assurance.
- **Pull request.** A proposed code change, submitted for review before it is merged.
- **Greenfield, brownfield.** New code written from scratch, against work in an existing and often older codebase.
- **Change failure rate.** The share of deployments that cause a failure needing a fix or a rollback.
- **Oracle.** What tells a test whether the result is correct. Explained where it first matters, in [Section 3.6](#36-quality-engineering-and-agentic-testing).
- **DORA.** DevOps Research and Assessment, a research programme run by Google Cloud.

## 2 Method and evidence grading

Every figure in this report was taken from a retrieved source and is attributed to it. Where only part of a source was available, [Section 9](#9-limitations-and-evidence-gaps) says so. Where a secondary source and a primary source disagreed, the primary source was used.

**Sources.** Web searches covered adoption research (DORA, METR, Prosci), delivery telemetry (LinearB, Faros, DX), quality engineering surveys (World Quality Report, PractiTest), and academic work on testing agent-written code. Primary documents were retrieved wherever they were accessible, and for several of the main sources that meant the full report, not a summary: the DORA ROI report, the METR 2025 paper, both agentic pull request papers, the McKinsey article, the World Quality Report, the LinearB benchmarks report, both Faros reports, the Undo survey report, all three DX reports, the Lightrun report and the 2024 and 2025 PractiTest reports. A second pass in the week to 10 October 2026 added the newest vendor telemetry and surveys, and the results are folded into the findings below.

**Conflict handling.** Secondary commentary disagrees about the direction of one headline METR figure. The primary METR page was used to settle it ([Section 3.2](#32-perceived-and-measured-gains-diverge)).

**Labels.** Findings are tagged by evidence grade. Statements of what the author would do, or why, are tagged *Judgement*.

| Grade | Meaning | Typical sources here |
| --- | --- | --- |
| A | Controlled study with disclosed method | METR randomised trials [[4]](references.md#ref-4), [[5]](references.md#ref-5) |
| B | Large survey or telemetry, often vendor or sponsor produced, correlational | DORA [[1]](references.md#ref-1), [[12]](references.md#ref-12), LinearB [[7]](references.md#ref-7), World Quality Report [[8]](references.md#ref-8), METR survey [[6]](references.md#ref-6), agentic pull request studies [[16]](references.md#ref-16), [[17]](references.md#ref-17), 2026 telemetry and surveys [[22]](references.md#ref-22) to [[31]](references.md#ref-31) |
| C | Case study, conference talk, practitioner or legal commentary | Prosci [[9]](references.md#ref-9), [[10]](references.md#ref-10), Stanford talk [[15]](references.md#ref-15), practitioner guides [[18]](references.md#ref-18), [[20]](references.md#ref-20), [[21]](references.md#ref-21), legal summary [[19]](references.md#ref-19) |

**Exclusions.** Claims that could not be traced to a primary source or a clearly attributable secondary source were left out. The principal gaps are listed in [Section 9](#9-limitations-and-evidence-gaps).

## 3 Findings: what the evidence shows

The findings follow the questions a sceptical reader would ask. Is anyone using this? Do the gains show up when measured properly? What decides whether they do? What does faster output cost further down the line? What moves people? What does testing look like when an agent writes the code? And what does the law add? Figures not repeated here are in the [evidence register](evidence-register.md).

### 3.1 Adoption is widespread; organisation-wide value is not

Getting people to use AI is no longer the hard part. Turning that use into value for the organisation is.

LinearB's 2026 benchmark reports 88.3% of surveyed organisations using AI-assisted tools daily or weekly [[7]](references.md#ref-7), and DX puts industry adoption at 93% [[24]](references.md#ref-24). Only 17.2% of developers in Stack Overflow's 2026 survey did not use AI tools [[26]](references.md#ref-26). McKinsey found 40% of respondents from large organisations scaling AI agents, up from 27% a year earlier, with about two in ten scaling coding agents [[25]](references.md#ref-25). Beyond writing code, use looks thinner. In Lightrun's survey of leaders in large organisations, 90% were piloting or experimenting with AI tools for incident analysis and fixes, none used them in production workflows, and 98% of those who had tried them trusted them less than their coding assistants [[29]](references.md#ref-29).

Testing shows the same curve on a slower clock. In one survey series, 60% of 2024 participants did not use AI for testing [[30]](references.md#ref-30), 45.65% had not integrated it by 2025 [[31]](references.md#ref-31), and 76.8% of testers reported using AI in 2026 [[21]](references.md#ref-21). The World Quality Report found 89% of responding organisations piloting or deploying generative AI workflows in quality engineering, but only 15% with enterprise-wide implementation. Respondents reported an average productivity gain of 19%, although one third saw minimal gains [[8]](references.md#ref-8).

The value side is thinner. McKinsey found 37% of respondents attributing some EBIT impact to AI, about the same as in 2025, despite more organisations scaling [[25]](references.md#ref-25). DX found median throughput up 37% over four quarters, while the share of time on new feature work held at roughly 57% to 58% [[24]](references.md#ref-24). Time is being saved, but it isn't yet visibly turning into more new work.

Motivation is not what separates the organisations that turn use into value. Prosci's research across more than 1,500 workers found motivation to use AI nearly identical in organisations that were succeeding and those that were stalling [[9]](references.md#ref-9).

*Evidence grades: B, or C where a figure is only second-hand [[7]](references.md#ref-7), [[8]](references.md#ref-8), [[21]](references.md#ref-21), [[24]](references.md#ref-24), [[25]](references.md#ref-25), [[26]](references.md#ref-26), [[29]](references.md#ref-29), [[30]](references.md#ref-30), [[31]](references.md#ref-31); C for Prosci [[9]](references.md#ref-9).*

### 3.2 Perceived and measured gains diverge

Developers' own estimates of AI's effect on their speed are unreliable, so delivered outcomes have to be measured. The METR studies show the gap most clearly.

![Bar chart of change in task time with AI. Developers forecast 24% faster and believed afterwards that they were 20% faster, but measured tasks took 19% longer.](assets/metr-belief-vs-measured.svg)

| Measure | Result | Source |
| --- | --- | --- |
| Developers' forecast before the 2025 trial | AI would make them 24% faster | [[4]](references.md#ref-4) |
| Developers' belief after the 2025 trial | AI had made them 20% faster | [[4]](references.md#ref-4) |
| Measured, 2025 randomised trial (16 developers, 246 issues) | Tasks took 19% longer with AI (confidence interval +2% to +39%) | [[4]](references.md#ref-4), [[5]](references.md#ref-5) |
| Measured, late 2025, 10 returning developers | Change in task time of -18% (confidence interval -38% to +9%) | [[5]](references.md#ref-5) |
| Measured, late 2025, 47 new developers | Change in task time of -4% (confidence interval -15% to +9%) | [[5]](references.md#ref-5) |
| Self-reported survey, February to April 2026 (349 technical workers) | Median 1.4 to 2x change in value of work; median 3x change in speed | [[6]](references.md#ref-6) |

*Reading the table.* METR reports change in task completion time, so a negative value means less time, that is, faster. METR describes its 2026 raw results as showing some evidence of speedup [[5]](references.md#ref-5). Some secondary commentary states the opposite; the primary METR page supports the reading used here.

METR judged its 2026 data an unreliable signal. A significant share of developers declined to take part if they had to work without AI, and 30% to 50% said they withheld some tasks for the same reason. METR therefore regards its estimate as likely a lower bound and its data as only very weak evidence for the size of any increase. It now believes developers are likely more sped up in early 2026 than in early 2025 [[5]](references.md#ref-5).

The 2025 trial used experienced developers working in repositories they had contributed to for years. METR states that the result is not evidence that AI fails to speed up most developers, or that it will not do so in the same setting in future [[4]](references.md#ref-4). The controlled evidence is now the oldest part of the picture: the review found no new controlled trial since METR's February and May 2026 releases [[5]](references.md#ref-5), [[6]](references.md#ref-6), while the vendor telemetry in [Section 3.4](#34-speed-arrives-and-the-cost-lands-downstream) is the newest.

*Implication (Judgement):* self-report is a useful sentiment signal but should never be the sole evidence of value. *Evidence grade: A, with small samples and authors' own reliability warnings [[4]](references.md#ref-4), [[5]](references.md#ref-5); B for the survey [[6]](references.md#ref-6).*

### 3.3 AI amplifies what the organisation already has

The benefit of AI depends on what an organisation has in place before the tools arrive. DORA's AI Capabilities Model, built from almost 5,000 survey respondents and 78 in-depth interviews, names seven capabilities that amplify or unlock AI's benefits [[1]](references.md#ref-1):

1. a clear and communicated AI stance
2. healthy data ecosystems
3. AI-accessible internal data
4. strong version control practices
5. working in small batches
6. a user-centric focus
7. quality internal platforms

DORA reports that without a user-centric focus, AI adoption can have a negative impact on team performance. It also notes that the AI stance capability measures clarity and communication, not the content of the policy [[1]](references.md#ref-1).

DORA's 2026 ROI report adds a J-curve: most organisations should expect a temporary productivity dip before long-term gains, caused by the learning curve, the verification tax of reviewing AI-generated code, and the need to adapt downstream processes such as testing and change approval [[2]](references.md#ref-2). DORA calls this the tuition cost of the transformation and advises budgeting for it explicitly [[2]](references.md#ref-2), [[3]](references.md#ref-3). It also associates AI adoption with higher individual effectiveness and code quality but more delivery instability, and presents that as a reason to invest in automated testing, continuous integration and small batches [[2]](references.md#ref-2).

![Schematic line chart, not data. Productivity dips below its starting level while people learn and processes adapt, then rises above it.](assets/j-curve-schematic.svg)

Telemetry from 8.1 million pull requests points the same way. AI pull requests were merged within 30 days 32.7% of the time, against 84.4% for unassisted work, and agent-created pull requests waited 17.6 hours for review (75th percentile), against 3.4 hours for unassisted work [[7]](references.md#ref-7). LinearB states that these relationships are correlational.

The effect also varies with the kind of work. A Stanford researcher's analysis of nearly 100,000 developers reported gains of 30% to 40% on low-complexity greenfield tasks and 0% to 10% on high-complexity brownfield tasks [[15]](references.md#ref-15). The DORA ROI report cites the same research programme [[2]](references.md#ref-2).

*The amplifier claim is contested.* DORA's survey-based position is that strong foundations amplify AI's benefits and protect against its downsides [[1]](references.md#ref-1). Faros's telemetry-based report states that high-performing organisations saw the same downstream deterioration as others [[22]](references.md#ref-22). Surveys and telemetry measure different things, and Faros sells measurement software. The fair summary is that the claim is supported by survey evidence and contested by telemetry, and the next section sets out the telemetry.

*Evidence grades: B [[1]](references.md#ref-1), [[2]](references.md#ref-2), [[7]](references.md#ref-7), [[22]](references.md#ref-22); C for the Stanford figures, which come from a conference talk. The review did not locate a peer-reviewed publication [[15]](references.md#ref-15).*

### 3.4 Speed arrives, and the cost lands downstream

Output is rising. The newest evidence, almost all of it from vendors, suggests the cost is turning up in review, QA and operations, and that per-change risk is settling while the total load is not.

**Output and stability.** Faros's April 2026 telemetry showed epics completed per developer up 66%, but also an incidents-to-pull-request ratio up 242.7%, comparing each organisation's lowest and highest AI adoption periods [[22]](references.md#ref-22). Its September follow-up, covering organisations that deepened already-high adoption, is mixed. Incidents per pull request were up only 14.5%, but monthly incidents were up 125.4% and time in QA up 300.6%. Faros states that its findings are correlational [[23]](references.md#ref-23).

**Review and verification.** Faros reported pull requests merged without any review up 31.3% in April [[22]](references.md#ref-22) and up 76.3% in September, more than double the earlier rise [[23]](references.md#ref-23). Further along the pipeline, a survey for Undo, which sells debugging tools, found 35% of AI-generated code reaches production before the team fully understands it [[27]](references.md#ref-27). In a Lightrun survey of 200 SRE and DevOps leaders, respondents estimated that 43% of AI-suggested code changes needed manual debugging in production, even after passing QA or staging, and that developers spend 38% of their week on debugging, verification and troubleshooting. None of the leaders was very confident that AI-generated code would behave correctly once deployed [[29]](references.md#ref-29). Lightrun also found a gap between levels: 56% of directors said code-level issues are often behind escalations to site reliability engineers, against 38% of VPs, which it reads as the people running the day-to-day response seeing more of the problem than those further up [[29]](references.md#ref-29).

**A possible countermeasure.** Faros reports that agentic review now covers 26% of pull requests, with many companies running it on over 50%, and that heavy users see faster first reviews and fewer change failures. It describes this as correlational, and unreviewed merges kept rising even where adoption was high [[23]](references.md#ref-23).

*Evidence grade: B for the telemetry and surveys [[22]](references.md#ref-22), [[23]](references.md#ref-23), [[27]](references.md#ref-27), [[29]](references.md#ref-29). Sources are mostly vendor or consultancy produced, none is peer reviewed, and the relationships are correlational.*

### 3.5 People, change and policy

Clear policy, protected learning time and honest handling of job concerns are the most consistently reported adoption levers, but the strongest numbers are modelled associations rather than trial results.

- **Policy, learning time, transparency.** DORA's 2024 research estimated that clear AI acceptable-use policies were associated with a 451% increase in AI adoption, dedicated learning time with a 131% increase, and transparent communication with an 11.4% increase [[12]](references.md#ref-12). These are modelled estimates from survey data, not experimental effects.
- **The policy gap.** Policy is also where practice lags most. Only 24% of Stack Overflow's 2026 respondents said their employer had published approved tools or formal AI guidance, and about three in ten said AI use was optional and left to the individual [[26]](references.md#ref-26). This supports Practice 1 in [Section 4](#4-practices-common-to-both-contexts).
- **Concern and trust.** Nearly 15% of DORA respondents expected AI to harm their careers, which DORA suggests may drive reactive rather than genuine adoption [[11]](references.md#ref-11). Outside Google, 39% of surveyed developers trusted the quality of AI output only a little or not at all, and developers who trust AI more use it more [[13]](references.md#ref-13).
- **A worked case.** AT&T scaled Microsoft 365 Copilot to more than 18,000 active users in six weeks, with 96.4% sustained adoption among assigned users. It ran more than 200 live training sessions and routed job-displacement concerns to supervisors with prepared talk tracks [[9]](references.md#ref-9). The case is published by a change-management vendor and concerns a general productivity assistant, not an engineering tool.
- **Champion networks.** Prosci reports that organisations with change agent networks met or exceeded their objectives more often than those without [[10]](references.md#ref-10). The review found no verified evidence for a specific champion-to-staff ratio ([Section 9](#9-limitations-and-evidence-gaps)).
- **Usage targets.** In June 2026 DORA warned that rewarding raw AI token consumption may nudge hesitant developers to experiment, but that treating token spend as a performance indicator is a trap [[14]](references.md#ref-14).

*Evidence grades: B [[11]](references.md#ref-11), [[12]](references.md#ref-12), [[13]](references.md#ref-13), [[26]](references.md#ref-26); C [[9]](references.md#ref-9), [[10]](references.md#ref-10), [[14]](references.md#ref-14).*

### 3.6 Quality engineering and agentic testing

Testing is one place where adoption meets its limits, because someone has to decide whether AI output is right. The evidence shows that checking is often thin.

One term needs explaining before the rest makes sense. A test *oracle* is whatever tells you what the correct result should be: a requirement, an agreed example, a domain expert's judgement, a known good answer. A test can only pass or fail against an oracle. If an agent writes both the code and the test, and nothing independent says what correct looks like, a passing test shows only that the two agree with each other. "Independent oracle" below means a source of truth that does not depend on the agent's own output.

- **Use cases and barriers.** AI use in quality engineering is shifting from analysing outputs to shaping inputs, with test case design and requirements refinement now leading adoption. The most cited barriers in 2025 were data privacy risk (67%) and integration complexity (64%), and half of respondents reported lacking AI and machine learning expertise [[8]](references.md#ref-8).
- **Tests in agent-written pull requests.** A study presented at MSR 2026 of about 33,600 agent-generated pull requests found that test inclusion rose from 31% to 52% over time. It did not evaluate test quality, adequacy or coverage [[16]](references.md#ref-16).
- **Coverage of agent-written changes.** A July 2026 preprint analysed 4,882 agent-generated pull requests from five agents. Agents included test changes in 49.6% of those that changed code under test. Existing tests covered 61.5% of changed executable lines in Java but only 27.0% in Python, where 64.8% of pull requests had no changed line executed by any existing test [[17]](references.md#ref-17).
- **Practitioner guidance.** One 2026 pilot guide argues that an independent oracle should be the architectural centre of agentic testing: agents discover and draft, while deterministic checks and accountable people decide whether software passes. [[18]](references.md#ref-18) For AI products, a 2026 conference account argues that exact-match oracles fail for non-deterministic behaviour and proposes checking a bounded behavioural envelope [[20]](references.md#ref-20).

The review located no independent controlled study of agentic QA or self-healing test frameworks ([Section 9](#9-limitations-and-evidence-gaps)). *Evidence grades: B [[8]](references.md#ref-8), [[16]](references.md#ref-16), [[17]](references.md#ref-17); C [[18]](references.md#ref-18), [[20]](references.md#ref-20).*

### 3.7 UK legal and workforce considerations

Personal data and staff consultation shape what can be adopted and how fast. The ICO's guidance on generative AI, as summarised by a law firm, states that data protection compliance is not optional where personal data is processed. It points to a data protection impact assessment, to Article 22 of the UK GDPR where AI supports automated decision-making, and to clear staff guidance on what may be shared with these tools [[19]](references.md#ref-19). The summary dates from 2023, so current requirements should be confirmed with the organisation's data protection officer or legal counsel. DORA's finding that job-displacement concern affects adoption [[11]](references.md#ref-11) supports early engagement with employee representatives where they exist (*Judgement*). *Evidence grade: C.*

## 4 Practices common to both contexts

Eight practices should be the same in both organisations, because the evidence for them doesn't depend on how old or how big the company is. Each one shows what it rests on.

| # | Practice | What to do | Basis |
| --- | --- | --- | --- |
| 1 | Publish a clear, written AI stance | One page: permitted tools, data rules, what is encouraged, who owns AI-generated changes, and an explicit statement that usage volume is not a target. | DORA capability [[1]](references.md#ref-1); policy association [[12]](references.md#ref-12); usage-target warning [[14]](references.md#ref-14) |
| 2 | Treat adoption as a change in how people work | Sponsor, communications, supervisor briefings, reinforcement. Do not treat it as a licence rollout. | Prosci [[9]](references.md#ref-9) |
| 3 | Make verification the design centre | Name accountable owners of the independent oracle, the means of deciding whether output is correct ([Section 3.6](#36-quality-engineering-and-agentic-testing)). Gate AI output with deterministic checks. | DORA verification tax [[2]](references.md#ref-2); agentic test gaps [[17]](references.md#ref-17); practitioner guidance [[18]](references.md#ref-18) |
| 4 | Protect learning time and tie it to real work | Scheduled hours, real tasks, shared use cases, not generic demonstrations. | DORA learning-time association [[12]](references.md#ref-12) |
| 5 | Work in small batches and plan review capacity | Cap change size. Measure review wait. Staff review as the bottleneck it becomes. | DORA capability [[1]](references.md#ref-1); LinearB telemetry [[7]](references.md#ref-7) |
| 6 | Use peer champions and visible examples | Champions chosen by function, not seniority. Weekly sharing of what worked and what failed. | Prosci [[10]](references.md#ref-10); AT&T case [[9]](references.md#ref-9). Ratios are *Judgement* |
| 7 | Address people's concerns explicitly | Talk about deskilling, job security and trust early, through supervisors as well as leaders. | DORA [[11]](references.md#ref-11), [[13]](references.md#ref-13); AT&T [[9]](references.md#ref-9) |
| 8 | Baseline first, measure outcomes, budget for a dip | Capture the starting position before expansion. Judge on delivered outcomes. Fund the early dip deliberately. | LinearB [[7]](references.md#ref-7); DORA [[2]](references.md#ref-2), [[3]](references.md#ref-3); METR [[4]](references.md#ref-4), [[5]](references.md#ref-5), [[6]](references.md#ref-6) |

Two cautions apply to every row (Judgement). The evidence is strongest for practices 1, 4, 5 and 8 and weakest for practice 6, where all the review found was an association reported by a vendor [[10]](references.md#ref-10). And none of the eight makes up for the others being missing: DORA presents its capabilities as a set [[1]](references.md#ref-1).

### 4.1 What the practices look like in practice

The table says what to do. These are the same eight practices as they might look on an ordinary Tuesday. They are illustrations (Judgement), not findings, and they are not drawn from either organisation, so swap in whatever fits your own place. The one detail that comes from a source is marked.

1. **A written stance.** The page lists the approved tools by name. It says customer data and anything confidential stays out of unapproved ones. It says that whoever merges a change owns it, whether a person or an agent wrote it, and that nobody is judged on how much they use AI. It fits on one page because it has to be read.
2. **Adoption as change.** A licence rollout sends an email with a login link. A change programme has a named sponsor explaining why in their own words, a briefing for supervisors before their teams hear about it, and a check a month later on who stopped using the tool and why.
3. **Verification at the centre.** An agent drafts a batch of tests for an existing workflow. A named tester decides what correct behaviour looks like for it, the pipeline runs the accepted tests, and the agent's own view that its tests pass counts for nothing.
4. **Learning time tied to real work.** A protected slot in the working week, with the team's current backlog open, trying AI on tickets they would have picked up anyway and writing down where it went wrong. Not a vendor demonstration in a lecture room.
5. **Small batches and review capacity.** Agent-generated changes are turning up as large pull requests that sit in the queue. The fix is to ask for smaller ones, set a size limit, and watch review wait the way you would watch a build queue.
6. **Champions.** A tester who has been using AI to draft test cases for a few months, and will happily show the rough edges, does more good than the most senior person who approved the tools.
7. **Concerns out in the open.** A supervisor who can answer "is this about cutting my team?" honestly, with something prepared, does more than an all-hands slide. AT&T routed job-displacement concerns to supervisors with prepared talk tracks [[9]](references.md#ref-9).
8. **Baseline first.** Before anyone gets a licence, pull the last few months of lead time, review wait, change failure rate and escaped defects from the tools you already use. Then you can say whether things moved, instead of arguing about how it felt.

## 5 Context A: established organisation

In an established organisation with a mixed estate, the first job is to match AI to the right work and the right people, then scale through peers and pairing, not mandates. The plan below is the author's synthesis of the evidence in [Section 3](#3-findings-what-the-evidence-shows); no single study tested it end to end.

### 5.1 Starting condition and what the evidence implies

Three working hypotheses follow from the evidence (Judgement). Each should be tested in the pilot rather than assumed.

1. **Large legacy systems are the hardest terrain for coding assistance.** METR's 2025 trial found a slowdown for experienced developers in mature, familiar repositories [[4]](references.md#ref-4), and the Stanford analysis reported the smallest gains on complex brownfield work [[15]](references.md#ref-15). Neither result proves legacy systems are a poor target with 2026 tools; both justify testing them separately from newer standalone components. Where systems have recently been consolidated, the same logic applies: the consolidated platform and the components still waiting to move onto it are different terrain.
2. **Test-adjacent work is the best-supported starting point.** That means the work around testing, not the code itself. Test case design and requirements refinement now lead quality engineering adoption [[8]](references.md#ref-8), and these tasks do not require repository access.
3. **The workforce divides by confidence, not motivation.** Motivation to use AI was nearly identical in succeeding and stalling organisations [[9]](references.md#ref-9), so helping people matters more than persuading them. With several workstreams, expect each to start from a different place, and plan for that instead of rolling out one programme to all of them.

### 5.2 Phased plan

Timings are indicative (Judgement).

![Timeline of four phases for an established organisation: foundation and baseline in weeks 0 to 8, pilot in weeks 8 to 24, scale in months 6 to 12, embed in months 12 to 18.](assets/phases-context-a.svg)

| Phase | Timing | Actions | Exit evidence |
| --- | --- | --- | --- |
| 0. Foundation and baseline | Weeks 0 to 8 | Publish the one-page AI stance. Segment the estate by work type (legacy system maintenance, newer standalone components, test-adjacent activity) and by role. Capture 8 to 12 weeks of existing delivery, review and quality data. Run a baseline survey of current use, confidence, trust and concerns. Consult employee representatives and the data protection lead. Agree a budget that expects an early dip [[2]](references.md#ref-2), [[3]](references.md#ref-3). | Stance published. Baseline dashboard exists. Pilot cells and hypotheses agreed in writing. |
| 1. Pilot | Weeks 8 to 24 | Run two to three pilot cells with staggered starts: a team working on newer standalone components; a QA-led cell using AI for test design and regression triage around legacy systems; and a cell of staff new to AI on the first two rungs of the ladder ([Section 5.3](#53-the-skills-ladder-for-staff-without-repository-experience)). One named champion per cell. Protected learning time. Weekly sharing of results. Tag AI-assisted and unassisted changes separately [[7]](references.md#ref-7). Plan review capacity in advance. | Pre-agreed thresholds on flow, quality and trust met against baseline. A written list of use cases that worked and that did not. |
| 2. Scale | Months 6 to 12 | Extend cell by cell, again staggered. Add a champion per team. Introduce pairing. Publish a use-case library from the pilots. Brief supervisors with talk tracks on job and skills concerns [[9]](references.md#ref-9). Introduce agentic QA only where a trustworthy oracle exists, for example stable regression suites and API checks. | Delivered outcomes at parity or better. No rise in escaped defects. Adoption depth growing by use case, not only by user count. |
| 3. Embed | Months 12 to 18 | Update standards: definition of done, pull request templates, test strategy, role descriptions and learning pathways. Review quarterly. Retire initiatives that miss thresholds. Refresh the stance as tools change [[9]](references.md#ref-9). | Outcomes sustained for two consecutive quarters. |

To make the pilot concrete (Judgement): one cell is one team, one workstream, a defined set of ticket types, one champion, and a hypothesis written down before it starts. For example, "AI-assisted test design will shorten the time from requirement to first reviewed test set without raising escaped defects". If the cell hits the thresholds, it reports what the tickets looked like. If it misses, that is just as useful, because the list of what did not work is part of the exit evidence.

### 5.3 The skills ladder for staff without repository experience

Staff who do not work with source repositories can start at rung 1 and never need to touch one to benefit. The ladder is a design proposal (Judgement); the underlying rationale is that AI work needs judgement about when to use it and how to evaluate output [[9]](references.md#ref-9).

| Rung | Activity | Repository access needed |
| --- | --- | --- |
| 1. Use | Apply AI to documents the person already owns: requirement review, test case review, test data ideas, defect report drafting. | No |
| 2. Verify | Check AI output against domain knowledge. Log every error found. The log becomes team evidence about reliability. | No |
| 3. Direct | Build reusable prompts and context packs for recurring tasks. Share them in the use-case library. | No |
| 4. Build | Pair with a champion on test automation or agent-assisted testing, inside the organisation's approved environment. | Yes, with a pairing partner |

Experienced testers and domain specialists hold the domain knowledge that functions as the oracle. Casting them as the people who check AI output, not as people about to be replaced, fits DORA's finding that dealing with concerns in plain terms lets staff get on with learning [[11]](references.md#ref-11).

### 5.4 Risks specific to this context

- **Piloting in the wrong terrain.** A disappointing result from legacy systems could be misread as evidence that AI does not work. Segment results by work type [[15]](references.md#ref-15).
- **Mistaking perception for evidence.** Enthusiastic self-report is expected and should be checked against delivered outcomes [[4]](references.md#ref-4), [[6]](references.md#ref-6).
- **Review queues.** More generated change can wait longer for review [[7]](references.md#ref-7). Plan capacity before expansion.
- **Quiet resistance.** At AT&T, concerns surfaced in pockets rather than broadly [[9]](references.md#ref-9). Use supervisors and champions to surface them early.
- **Usage targets.** Do not set them; DORA describes treating token spend as a performance indicator as a trap [[14]](references.md#ref-14).
- **Data handling.** Where the organisation processes personal or regulated data, confirm the position with data protection and compliance leads before widening access [[19]](references.md#ref-19).

## 6 Context B: early-stage start-up

In a young company the opportunity is to make verification a default before habits form, and the risk is that delivery speed outruns assurance. Because AI amplifies the system it enters [[1]](references.md#ref-1), [[2]](references.md#ref-2), a company with few foundations will amplify the gaps. The plan below is the author's synthesis of [Section 3](#3-findings-what-the-evidence-shows) (Judgement).

### 6.1 Starting condition and what the evidence implies

1. **There is no resistance to overcome, but also no baseline.** Prior delivery and quality data may be thin, so measurement has to be built, not retrieved ([Section 8](#8-baselining-and-evaluation-framework)).
2. **Foundations come first.** DORA's capabilities include strong version control, small batches, quality internal platforms and AI-accessible internal data [[1]](references.md#ref-1). These are plausibly cheaper to establish in a young company than in a large one (Judgement).
3. **Growth will test the foundations.** When headcount and codebase grow together, review capacity tends to become the scarce thing, since generation is cheap [[7]](references.md#ref-7). If the product also handles sensitive personal data, the data rules in Phase 0 carry more weight than they would elsewhere (Judgement).
4. **Quality assurance may have two jobs.** It must assure AI-assisted engineering. Where the product itself contains AI components, it must also test non-deterministic behaviour, which practitioners argue needs behavioural-envelope oracles rather than exact-match checks [[20]](references.md#ref-20) (Grade C).
5. **Agentic QA needs an independent check.** Agentic QA is one part of the adoption plan, and the part most likely to look finished before it is. In one 2026 preprint, agents included test changes in under half of the qualifying pull requests [[17]](references.md#ref-17), and practitioner guidance places the independent oracle at the centre of agentic testing [[18]](references.md#ref-18).

### 6.2 Phased plan

Timings are indicative (Judgement).

![Timeline of four phases for a start-up: stance and foundations in days 0 to 30, baseline and evaluation in days 30 to 90, embed in defaults in days 90 to 180, scale by risk after day 180.](assets/phases-context-b.svg)

| Phase | Timing | Actions | Exit evidence |
| --- | --- | --- | --- |
| 0. Stance and foundations | Days 0 to 30 | Publish the AI stance. Confirm data handling, including customer data and UK GDPR obligations [[19]](references.md#ref-19). Set defaults for version control, small changes, continuous integration and rollback [[1]](references.md#ref-1). Appoint a named verification lead who owns the oracle for each product behaviour. Start instrumenting delivery, review and defect data. | Stance and data rules published. Verification lead named. Instrumentation live. |
| 1. Baseline and evaluation | Days 30 to 90 | Treat this period as the baseline. Where the product contains AI components, build an evaluation set: representative cases with human-agreed expected behaviour and a defined acceptable envelope. Pilot agentic QA in a drafting and exploring role, behind deterministic gates. Inject known defects and record whether the suite catches them. | Baseline report. Evaluation set in regular use. First measured agentic QA results. |
| 2. Embed in defaults | Days 90 to 180 | Build AI practice into onboarding, pull request templates and the definition of done. Appoint a champion per team. Hold weekly sharing of what worked and failed. Schedule protected learning time [[12]](references.md#ref-12). Require review of agent-created changes by a named owner [[7]](references.md#ref-7). | Every new starter trained in the stance and verification method. No agent-created change merged without a named owner. |
| 3. Scale by risk | After day 180 | Extend agentic QA to areas in proportion to risk and oracle quality. Review cost, defect-detection and maintenance quarterly. Retire what fails thresholds. Refresh the stance as tools change [[9]](references.md#ref-9). | Outcomes sustained for two consecutive quarters against baseline. |

### 6.3 Agentic QA within the adoption plan

Agentic QA follows the same rules as the rest of adoption: baseline it, measure it on outcomes, and scale it by risk. What is particular to it is the need for an independent check. The design principle is that agents may explore and draft, but accountable people and deterministic checks decide whether software has passed [[18]](references.md#ref-18). Concretely (Judgement):

- **Agents** explore the product, propose test ideas and draft tests.
- **Deterministic gates** run the accepted tests, evidence collection and release thresholds without an agent in the decision.
- **Accountable people** own the oracle for each behaviour and accept or reject agent-drafted tests.
- **Known-defect checks** inject faults and measure whether the suite detects them, which exposes false confidence.
- **Evidence trail** records what was run, by whom, against which version.

As an illustration (Judgement): an agent proposes tests for a new feature. The verification lead reads them against the intended behaviour, rejects the ones that only restate the code, and accepts the rest. The pipeline runs the accepted tests on every change. Once a quarter someone plants a few known faults in a copy of the code to see whether the suite notices. If it misses them, the green tick means less than everyone assumed.

The review located no independent controlled evidence that self-healing test frameworks deliver measurable benefit at scale ([Section 9](#9-limitations-and-evidence-gaps)). Treat them as unproven, and fix brittle test design before buying repair tooling.

### 6.4 Risks specific to this context

- **Speed without verification.** More code, faster, with the same review capacity creates queues and instability [[2]](references.md#ref-2), [[7]](references.md#ref-7).
- **Leaning on one person.** A single verification lead is a single point of failure. Write the oracles down, so the knowledge outlasts the person (Judgement).
- **Customer data in tools.** Customer or personal data may pass through AI tools. Settle data rules before wider tool access [[19]](references.md#ref-19).
- **Adoption without value.** In a small company, enthusiasm can easily cover for outcomes nobody has measured. Baseline from the first day [[7]](references.md#ref-7).

## 7 Comparative analysis

The two contexts share a spine of eight practices and differ mainly in what comes first, what is scarce, and where the baseline comes from. The table separates what the evidence supports from what is the author's judgement.

| Dimension | Context A: established | Context B: early-stage | Basis |
| --- | --- | --- | --- |
| Starting condition | Habits, legacy code, uneven skills | Blank slate, thin history, few guardrails | Description of the two contexts |
| Primary risk | Piloting in the wrong terrain; stalled adoption | Speed outrunning verification | [[4]](references.md#ref-4), [[15]](references.md#ref-15) for A; [[2]](references.md#ref-2), [[7]](references.md#ref-7), [[17]](references.md#ref-17) for B |
| First move | Segment the estate by work type and role; baseline from history | Stance, foundations, instrumentation from day one | [[1]](references.md#ref-1), [[7]](references.md#ref-7); Judgement |
| Adoption mechanism | Champions, pairing, skills ladder, supervisor talk tracks | Defaults in onboarding, templates and definition of done | [[9]](references.md#ref-9), [[10]](references.md#ref-10); Judgement |
| Role of champions | Essential to cross a large, varied workforce | Lighter touch; one per team | [[10]](references.md#ref-10); ratios are Judgement |
| Where AI is applied first | Newer standalone components and test-adjacent work | Everywhere, but behind deterministic gates | [[8]](references.md#ref-8), [[15]](references.md#ref-15); Judgement |
| QA focus | Protect existing quality while adding AI-assisted checks | Build evaluation sets and oracles into the product | [[18]](references.md#ref-18), [[20]](references.md#ref-20); Judgement |
| Agentic QA | Only where a trustworthy oracle already exists | Designed in with an independent check from the start | [[17]](references.md#ref-17), [[18]](references.md#ref-18); Judgement |
| Governance | Consult representatives; align with compliance and data protection | Settle customer data rules first | [[11]](references.md#ref-11), [[19]](references.md#ref-19); Judgement |
| Baseline source | 8 to 12 weeks of existing delivery and review data plus survey | First 90 days of newly instrumented data | [[7]](references.md#ref-7); Judgement |
| Pace and horizon | Staged over 12 to 18 months | Fast but gated, with review at 90 and 180 days | Judgement |
| Success signal | Outcomes at parity or better across segments, sustained | Verification embedded as default; outcomes stable as volume grows | [[2]](references.md#ref-2), [[7]](references.md#ref-7); Judgement |

The central asymmetry is that Context A has history but friction, while Context B has speed but no history. Context A should spend its early effort on enablement and segmentation. Context B should spend its early effort on verification and instrumentation. Both end up in the same place: decide on delivered outcomes against a baseline.

## 8 Baselining and evaluation framework

Both organisations should baseline before expanding, measure delivered outcomes across several layers, and decide against thresholds agreed in advance. Usage counts alone are not evidence of value.

### 8.1 Principles

1. **Baseline first.** LinearB advises capturing cycle time by phase, pull request size, acceptance rate and rework rate while current adoption is steady. It links the absence of a baseline to the finding that 44.7% of organisations do not formally measure AI impact while 76.1% of leaders report gains from adoption signals [[7]](references.md#ref-7).
2. **Segment by contribution type.** Keep agent-created, AI-assisted and unassisted changes separate, because blended averages describe none of them [[7]](references.md#ref-7).
3. **Judge outcomes, not activity.** Token counts and usage leaderboards are not performance measures [[14]](references.md#ref-14). Count accepted evidence and defects caught, not artefacts generated [[18]](references.md#ref-18).
4. **Do not rely on self-report alone.** Self-assessed gains overstated measured effects in METR's work [[4]](references.md#ref-4), [[6]](references.md#ref-6).
5. **Expect and budget for a dip.** Evaluate over a window long enough to pass the learning curve, and set its length in advance [[2]](references.md#ref-2), [[3]](references.md#ref-3) (Judgement on length).
6. **Use staggered rollout as the comparison.** Compelling staff to work without AI is increasingly impractical [[5]](references.md#ref-5), so later-starting cells act as the comparison group (Judgement).

### 8.2 Measures by layer

| Layer | Example measures | Data source | Caution |
| --- | --- | --- | --- |
| 1. Adoption depth | Weekly active use by role and use case; share of work items using AI, by use case; share of AI use that is verified | Tool analytics, work tracker tags, survey | Activity is not value. AT&T treated active use as a floor [[9]](references.md#ref-9). Avoid token leaderboards [[14]](references.md#ref-14) |
| 2. Flow | Lead time by phase; change size; pickup and review time; acceptance (merged within 30 days) by contribution type; deployment frequency; share of changes merged without review; time in QA | Source control, pipeline, work tracker | Correlational. Segment by contribution type [[7]](references.md#ref-7). Recent telemetry reports unreviewed merges and time in QA rising [[23]](references.md#ref-23) |
| 3. Quality and stability | Change failure rate; deployment rework rate; escaped defects; time to restore; flaky test rate (tests that pass and fail with no code change); incidents per change and monthly incident volume | Incident, defect and pipeline data | DORA associates AI adoption with more instability [[2]](references.md#ref-2). DORA added deployment rework rate to its Quick Check in April 2026 [[14]](references.md#ref-14) |
| 4. Agentic QA effectiveness | Share of agent-drafted tests accepted; defects caught per accepted test; known-defect detection rate; coverage of changed lines; human review time per accepted test; maintenance effort | Test management, coverage tools, known-defect runs | Accepted evidence over generated volume [[18]](references.md#ref-18). Coverage alone does not show adequacy. Known-defect detection is Judgement |
| 5. People | Trust, confidence, workload, skills; concern about deskilling and job security | Quarterly pulse survey | Trust is associated with use [[13]](references.md#ref-13). Surveys carry self-report bias [[6]](references.md#ref-6) |
| 6. Cost and value | Licence and usage cost; review and verification time; value of time released | Finance, sampled time-use | Use conservative, auditable assumptions as AT&T did [[9]](references.md#ref-9). DORA describes its ROI calculations as high-uncertainty estimates and recommends conservative, realistic and optimistic scenarios [[2]](references.md#ref-2) |

### 8.3 Establishing the baseline in each context

- **Context A.** Use 8 to 12 weeks of existing delivery, review and defect history, held steady while the baseline is captured, and a first survey of use, trust and concerns (Judgement on duration; the principle follows [[7]](references.md#ref-7)). Define pilot segments before looking at results.
- **Context B.** Treat the first 90 days of newly instrumented data as the baseline and compare each cohort with its own earlier trajectory (Judgement). DORA's Quick Check, its benchmark for delivery performance, offers an external reference point [[14]](references.md#ref-14).

### 8.4 Judging an initiative

1. Before the pilot, write the hypothesis, the measures, the expected direction, and a stop, continue or scale rule.
2. Define segments in advance: work type and contribution type.
3. Run for the full window and expect an early dip [[2]](references.md#ref-2).
4. Compare with the baseline and with later-starting cells.
5. Check delivered data, survey results and a read through a sample of the actual work against one another. Include the view of the people closest to production as well as leadership's, since in one survey they saw more of the problem [[29]](references.md#ref-29).
6. Decide by the pre-agreed rule and record the decision and its rationale.

An illustrative decision rule follows. The thresholds must be set locally and in advance (Judgement).

| Observation | Decision |
| --- | --- |
| Flow improves or holds; quality and stability hold; trust stable or rising | Scale |
| Flow improves; quality or stability worsens | Pause. Fix verification and review capacity before scaling |
| Flow and quality flat after the learning window; trust falling | Stop or redesign |
| Results differ by segment | Continue only in the segments that pass |

Two illustrative readings (Judgement). In the first, a team's AI-assisted changes are merging faster, review wait has lengthened, and the change failure rate is no worse than baseline. That points to Scale, with review capacity added first so the queue does not become the next constraint. In the second, the same team is merging faster but the change failure rate has crept up against baseline. The table says Pause: fix verification before anyone is given more tooling, and look again after the next window.

## 9 Limitations and evidence gaps

Confidence in the conclusions is moderate, and executives should read the recommendations as informed judgement, not as proven method. The table shows how firm each kind of claim is. The main limitations follow it.

| How firm | What the evidence supports | Basis |
| --- | --- | --- |
| Reasonably well supported | Self-reported gains overstate measured gains. Adoption is widespread, but organisation-wide value is harder to show, and most organisations do not formally measure it. | [[4]](references.md#ref-4), [[6]](references.md#ref-6), [[7]](references.md#ref-7), [[8]](references.md#ref-8), [[25]](references.md#ref-25) |
| Suspected, but correlational | Strong foundations amplify the benefit. There is an early dip. The cost of faster output shows up in QA and incidents. Clear policy and learning time go with higher adoption. | [[1]](references.md#ref-1), [[2]](references.md#ref-2), [[12]](references.md#ref-12), [[22]](references.md#ref-22), [[23]](references.md#ref-23) |
| Not known | Whether agentic QA improves quality. Whether any of this holds in ordinary product teams under controlled conditions. How long the dip lasts. Whether AI review reduces the downstream cost. | No controlled evidence found |

1. **Source independence.** Much of the quantitative evidence is survey or telemetry produced by vendors or sponsors: LinearB [[7]](references.md#ref-7), the OpenText-sponsored World Quality Report [[8]](references.md#ref-8), Prosci [[9]](references.md#ref-9), [[10]](references.md#ref-10), Faros [[22]](references.md#ref-22), [[23]](references.md#ref-23), DX [[24]](references.md#ref-24), Undo [[27]](references.md#ref-27), [[28]](references.md#ref-28), Lightrun [[29]](references.md#ref-29) and Google Cloud's DORA programme [[1]](references.md#ref-1), [[2]](references.md#ref-2), [[12]](references.md#ref-12). Most relationships reported are correlational, as LinearB itself states [[7]](references.md#ref-7).
2. **METR studies.** The 2025 trial had 16 developers [[4]](references.md#ref-4). The 2026 follow-up was judged unreliable by its own authors because of selection effects [[5]](references.md#ref-5). Neither setting is a corporate product team.
3. **Stanford figures.** They come from a conference talk, and the review did not locate a peer-reviewed publication [[15]](references.md#ref-15). The DORA ROI report repeats the figures with slightly different ranges and credits them to Stanford's software engineering productivity research [[2]](references.md#ref-2), [[3]](references.md#ref-3), so they are consistent across two sources, but that is not independent confirmation.
4. **Case evidence.** The AT&T example is published by a change-management vendor and concerns a general productivity assistant [[9]](references.md#ref-9). Evidence for champion networks is a vendor-reported association [[10]](references.md#ref-10). The review found no verified champion-to-staff ratio, so ratios in this report are judgement.
5. **Partial access to some sources.** Nearly all the sources that carry figures were read in full. The Lightrun sample was recruited through a business research panel and is not random. Where they were not, the figures rest on someone else's account, and the 2026 testing figure from [[21]](references.md#ref-21) is second-hand because the 2026 PractiTest report has no public copy.

   | How it was read | Sources |
   | --- | --- |
   | In full | DORA ROI report [[2]](references.md#ref-2), [[3]](references.md#ref-3), DORA AI Capabilities Model [[1]](references.md#ref-1), METR 2025 paper [[4]](references.md#ref-4), both agentic pull request papers [[16]](references.md#ref-16), [[17]](references.md#ref-17), McKinsey article [[25]](references.md#ref-25), LinearB benchmarks report [[7]](references.md#ref-7), both Faros reports [[22]](references.md#ref-22), [[23]](references.md#ref-23), all three DX reports [[24]](references.md#ref-24), Lightrun report [[29]](references.md#ref-29), World Quality Report [[8]](references.md#ref-8), PractiTest 2024 and 2025 reports [[30]](references.md#ref-30), [[31]](references.md#ref-31), Undo survey report (behind [[27]](references.md#ref-27), [[28]](references.md#ref-28)) |
   | Trade-press coverage of a survey | Stack Overflow [[26]](references.md#ref-26) |
   | Practitioner or legal article, read as published | [[18]](references.md#ref-18), [[19]](references.md#ref-19), [[20]](references.md#ref-20), [[21]](references.md#ref-21) |

6. **Agentic QA.** The review located no independent controlled study of agentic QA effectiveness or of self-healing test frameworks. Absence from this review is not proof of absence. One practitioner source asserts that independent evidence is lacking [[21]](references.md#ref-21).
7. **Test studies are descriptive.** The MSR study did not evaluate test quality, adequacy or coverage [[16]](references.md#ref-16). The coverage preprint is not yet peer-reviewed [[17]](references.md#ref-17).
8. **Legal position.** The ICO material is a 2023 law-firm summary [[19]](references.md#ref-19). It is not legal advice. Current requirements must be confirmed with the organisation's data protection officer or counsel.
9. **Currency.** The field changes quickly. METR itself marked its 2025 result out of date within a year [[4]](references.md#ref-4), [[5]](references.md#ref-5). Evidence is current to 10 October 2026.
10. **Exclusions.** Claims that could not be traced to a primary or clearly attributable secondary source were excluded. These included several widely repeated champion-programme statistics and some calculator defaults.
11. **Applicability.** Neither context is a specific named organisation. Local data, regulation and culture will change the plan.

## 10 Conclusions and recommendations

AI adoption should be run as a change programme in which checking comes first, in both contexts. The evidence does not support mandates, usage targets, or reliance on self-reported gains.

**Conclusions.**

1. Adoption is no longer the constraint; converting it into delivered value is [[7]](references.md#ref-7), [[8]](references.md#ref-8), [[9]](references.md#ref-9).
2. Foundations and verification decide whether faster generation becomes faster delivery [[1]](references.md#ref-1), [[2]](references.md#ref-2), [[7]](references.md#ref-7).
3. The two contexts differ in their first move, not in their discipline. Context A leads with segmentation and enablement. Context B leads with foundations and instrumentation (Judgement).
4. Evidence for agentic QA effectiveness is immature, so it should be designed with an independent check and measured on accepted evidence [[17]](references.md#ref-17), [[18]](references.md#ref-18).

**Recommendations for executive decision.**

1. Endorse a written AI stance with a named executive owner [[1]](references.md#ref-1), [[12]](references.md#ref-12).
2. Approve protected learning time and an explicit budget for an early productivity dip [[2]](references.md#ref-2), [[3]](references.md#ref-3), [[12]](references.md#ref-12).
3. Approve a baseline period before wider rollout: about 8 to 12 weeks of history in Context A, the first 90 days of new instrumentation in Context B (Judgement on durations) [[7]](references.md#ref-7).
4. Adopt outcome-based measurement ([Section 8.2](#82-measures-by-layer)) and do not use usage or token counts as performance targets [[14]](references.md#ref-14).
5. Name accountable owners of verification, and require a named owner for every agent-created change [[7]](references.md#ref-7), [[18]](references.md#ref-18).
6. Fund review capacity alongside generation capacity [[7]](references.md#ref-7).
7. In Context A, pilot first on newer standalone components and test-adjacent work, with a skills ladder for staff who do not work with source code. In Context B, appoint a verification lead and build evaluation sets within 90 days (Judgement).
8. Engage employee representatives, data protection and compliance leads before widening tool access [[11]](references.md#ref-11), [[19]](references.md#ref-19).
9. Review the evidence and the plan quarterly, because the field is moving quickly [[5]](references.md#ref-5).

A suitable next step is to agree pilot hypotheses, measures and decision rules in writing before any tool is expanded. The [templates](templates.md) give a starting point for each.
