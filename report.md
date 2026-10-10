# AI Adoption in Software Organisations: An Evidence-Based Comparison of Established and Early-Stage Contexts

Oct 10, 2026 · Swissola

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

A staged, verification-led approach is the best-supported way to drive AI adoption in both contexts, but the two organisations need different first moves. The established company must change habits across an uneven workforce. The early-stage company must build foundations before speed outruns assurance.

**Purpose.** To compare how AI adoption, including agentic quality assurance, should be driven in (A) an established organisation and (B) a start-up about two years old.

**Method.** A structured review of primary and secondary sources current to 10 October 2026. Each source is graded for evidence strength ([Section 2](#2-method-and-evidence-grading)). Recommendations are labelled as the author's judgement wherever no study directly supports them.

**Principal findings.**

- Adoption is no longer the constraint. 88.3% of surveyed organisations use AI tools daily or weekly [[7]](references.md#ref-7), yet only 15% of organisations pursuing generative AI in quality engineering have reached enterprise-wide implementation [[8]](references.md#ref-8).
- Self-reported gains overstate measured gains. In a 2025 randomised trial, developers believed AI had made them 20% faster while tasks took 19% longer [[4]](references.md#ref-4). The authors judged their 2026 follow-up unreliable [[5]](references.md#ref-5).
- AI amplifies the system it enters. DORA identifies seven organisational capabilities that amplify the benefit [[1]](references.md#ref-1) and describes a temporary dip in productivity before returns arrive [[2]](references.md#ref-2)[[3]](references.md#ref-3).
- Preparation, not motivation, separates success from stalling. Prosci found motivation to use AI nearly identical in succeeding and stalling organisations [[9]](references.md#ref-9).
- Agent-written code is often under-tested. In one 2026 preprint of 4,882 agent-generated pull requests, agents included test changes in only 49.6% of those that changed code under test [[17]](references.md#ref-17).

**Recommendations.** Eight practices apply in both contexts ([Section 4](#4-practices-common-to-both-contexts)). Context A starts by segmenting its estate and piloting where AI performs best ([Section 5](#5-context-a-established-organisation)). Context B starts by fixing foundations and building evaluation into the product ([Section 6](#6-context-b-early-stage-start-up)). Both should baseline first, measure delivered outcomes rather than usage, and decide on thresholds agreed in advance ([Section 8](#8-baselining-and-evaluation-framework)).

**Confidence.** Moderate. Much of the evidence is survey data or vendor telemetry, and most of it is correlational ([Section 9](#9-limitations-and-evidence-gaps)). Evidence from the last six months ([Section 3.7](#37-evidence-from-the-last-six-months)) is almost all vendor-produced. It points to per-change risk stabilising while QA and operational load keep rising.

## 1 Introduction and scope

Adoption has outpaced the measurement of its value: 44.7% of surveyed organisations do not formally measure AI's impact [[7]](references.md#ref-7). The right strategy also depends on the organisation's starting condition. This report examines two starting conditions.

**Context A: established organisation.** A mature organisation with a sizeable technology function, a mix of older and newer systems, and a wide range of staff skills and attitudes to AI.

**Context B: early-stage start-up.** A start-up about two years old. Leadership wants agentic quality assurance and AI good practice built in as foundations.

**Questions addressed.**

1. How should adoption be driven in each context, and what exactly should be done?
2. What should be done identically in both?
3. What should differ, and why?
4. How should each context baseline its starting position?
5. How should initiatives and improvements be judged?

**Scope.** The review covers software engineering and quality assurance, with the UK as the primary jurisdiction. It reflects evidence available to 10 October 2026. It is not legal advice, and it does not evaluate specific commercial tools.

## 2 Method and evidence grading

Every figure in this report was taken from a retrieved source page and is attributed to it. Sources available only as an abstract, summary or excerpt are identified in [Section 9](#9-limitations-and-evidence-gaps). Where a secondary source and a primary source disagreed, the primary source was used.

**Sources.** Web searches covered adoption research (DORA, METR, Prosci), delivery telemetry (LinearB), quality engineering surveys (World Quality Report), and academic work on testing agent-written code. Primary pages were retrieved wherever they were accessible. Two sources were available only as summaries: the DORA ROI report (read through its landing page and trade-press coverage) and the World Quality Report (read through its press release).

**Conflict handling.** Secondary commentary disagrees about the direction of one headline METR figure. The primary METR page was used to settle it ([Section 3.2](#32-perceived-and-measured-gains-diverge)).

**Labels.** Findings are tagged by evidence grade. Statements of what the author would do, or why, are tagged *Judgement*.

| Grade | Meaning | Typical sources here |
| --- | --- | --- |
| A | Controlled study with disclosed method | METR randomised trials [[4]](references.md#ref-4)[[5]](references.md#ref-5) |
| B | Large survey or telemetry, often vendor or sponsor produced, correlational | DORA [[1]](references.md#ref-1)[[12]](references.md#ref-12), LinearB [[7]](references.md#ref-7), World Quality Report [[8]](references.md#ref-8), METR survey [[6]](references.md#ref-6), agentic pull request studies [[16]](references.md#ref-16)[[17]](references.md#ref-17), 2026 telemetry and surveys [[22]](references.md#ref-22) to [[31]](references.md#ref-31) |
| C | Case study, conference talk, practitioner or legal commentary | Prosci [[9]](references.md#ref-9)[[10]](references.md#ref-10), Stanford talk [[15]](references.md#ref-15), practitioner guides [[18]](references.md#ref-18)[[20]](references.md#ref-20)[[21]](references.md#ref-21), legal summary [[19]](references.md#ref-19) |

**Exclusions.** Claims that could not be traced to a primary source or a clearly attributable secondary source were left out. The principal gaps are listed in [Section 9](#9-limitations-and-evidence-gaps).

## 3 Findings: what the evidence shows

### 3.1 Adoption is widespread; organisation-wide value is not

Converting adoption into organisation-wide value is the real constraint. LinearB's 2026 benchmark reports 88.3% of surveyed organisations using AI-assisted tools daily or weekly, up from 71.6% in early 2024 [[7]](references.md#ref-7). In quality engineering, the World Quality Report 2025-26 found 89% of responding organisations piloting or deploying generative AI workflows (37% in production, 52% in pilot) but only 15% with enterprise-wide implementation. A further 43% remained experimental and 30% were limited to specific use cases [[8]](references.md#ref-8). Respondents reported an average productivity gain of 19%, although one third saw minimal gains [[8]](references.md#ref-8).

Prosci's research across more than 1,500 workers found motivation to use AI nearly identical in organisations that were succeeding and those that were stalling [[9]](references.md#ref-9). *Evidence grades: B [[7]](references.md#ref-7)[[8]](references.md#ref-8), C [[9]](references.md#ref-9).*

### 3.2 Perceived and measured gains diverge

Developers' own estimates of AI's effect on their speed are unreliable, so delivered outcomes must be measured. The METR studies show the gap most clearly.

| Measure | Result | Source |
| --- | --- | --- |
| Developers' forecast before the 2025 trial | AI would make them 24% faster | [[4]](references.md#ref-4) |
| Developers' belief after the 2025 trial | AI had made them 20% faster | [[4]](references.md#ref-4) |
| Measured, 2025 randomised trial (16 developers, 246 issues) | Tasks took 19% longer with AI (confidence interval +2% to +39%) | [[4]](references.md#ref-4)[[5]](references.md#ref-5) |
| Measured, late 2025, 10 returning developers | Change in task time of -18% (confidence interval -38% to +9%) | [[5]](references.md#ref-5) |
| Measured, late 2025, 47 new developers | Change in task time of -4% (confidence interval -15% to +9%) | [[5]](references.md#ref-5) |
| Self-reported survey, February to April 2026 (349 technical workers) | Median 1.4 to 2x change in value of work; median 3x change in speed | [[6]](references.md#ref-6) |

*Reading the table.* METR reports change in task completion time, so a negative value means less time, that is, faster. METR describes its 2026 raw results as showing some evidence of speedup [[5]](references.md#ref-5). Some secondary commentary states the opposite; the primary METR page supports the reading used here.

METR judged its 2026 data an unreliable signal. A significant share of developers declined to take part if they had to work without AI, and 30% to 50% said they withheld some tasks for the same reason. METR therefore regards its estimate as likely a lower bound and its data as only very weak evidence for the size of any increase [[5]](references.md#ref-5). METR now believes developers are likely more sped up in early 2026 than in early 2025 [[5]](references.md#ref-5).

The 2025 trial involved experienced developers working in repositories they had contributed to for years, averaging over 22,000 stars and more than 1 million lines of code [[4]](references.md#ref-4). METR states that the result is not evidence that AI fails to speed up most developers, or that it will not do so in the same setting in future [[4]](references.md#ref-4). METR notes reasons for scepticism about self-reported gains and recorded in 2025 that participants overestimated AI's effect on task time by 40 percentage points on average [[6]](references.md#ref-6).

*Implication (Judgement):* self-report is a useful sentiment signal but should never be the sole evidence of value. *Evidence grade: A, with small samples and authors' own reliability warnings [[4]](references.md#ref-4)[[5]](references.md#ref-5); B for the survey [[6]](references.md#ref-6).*

### 3.3 AI amplifies what the organisation already has

The benefit of AI depends on organisational foundations. DORA's AI Capabilities Model, built from almost 5,000 survey respondents and 78 in-depth interviews, names seven capabilities that amplify or unlock AI's benefits [[1]](references.md#ref-1):

1. a clear and communicated AI stance
2. healthy data ecosystems
3. AI-accessible internal data
4. strong version control practices
5. working in small batches
6. a user-centric focus
7. quality internal platforms

DORA reports that without a user-centric focus, AI adoption can have a negative impact on team performance. It also notes that the AI stance capability measures clarity and communication, not the content of the policy [[1]](references.md#ref-1).

DORA's 2026 ROI report adds a J-curve: most organisations should expect a temporary productivity dip before long-term gains, caused by the learning curve, the verification tax of reviewing AI-generated code, and the need to adapt downstream processes such as testing and change approval [[2]](references.md#ref-2). DORA calls this the tuition cost of the transformation and advises budgeting for it explicitly [[2]](references.md#ref-2)[[3]](references.md#ref-3). The same report notes that AI adoption is associated with higher individual effectiveness and code quality but also with more delivery instability. Its sample calculator assumes the change failure rate rises from 5% to 6%, and DORA presents this as a reason to invest in automated testing, continuous integration and small batches [[2]](references.md#ref-2).

Telemetry from 8.1 million pull requests points the same way. AI pull requests were merged within 30 days 32.7% of the time, against 84.4% for unassisted work. Agent-created pull requests waited 17.6 hours for review (75th percentile), against 3.4 hours for unassisted work [[7]](references.md#ref-7). LinearB states that these relationships are correlational [[7]](references.md#ref-7).

The amplifier claim is contested. Faros's 2026 telemetry reports that high-performing organisations experienced the same downstream deterioration as others [[22]](references.md#ref-22), whereas DORA's finding rests on survey data [[1]](references.md#ref-1). [Section 3.7](#37-evidence-from-the-last-six-months) sets out the newer evidence.

The effect also varies by context. A Stanford researcher's analysis of nearly 100,000 developers reported gains of 30% to 40% on low-complexity greenfield tasks and 0% to 10% on high-complexity brownfield tasks, with an average of 15% to 20% [[15]](references.md#ref-15). The DORA ROI report, as summarised by InfoQ, cites the same research programme: 35% to 40% on simple greenfield tasks and 10% or less on complex legacy code [[2]](references.md#ref-2). *Evidence grades: B [[1]](references.md#ref-1)[[2]](references.md#ref-2)[[7]](references.md#ref-7); C for the Stanford figures, which come from a conference talk. I did not locate a peer-reviewed publication [[15]](references.md#ref-15).*

### 3.4 People, change and policy

Clear policy, protected learning time and honest handling of job concerns are the most consistently reported adoption levers, but the strongest numbers are modelled associations rather than trial results.

- **Policy, learning time, transparency.** DORA's 2024 research estimated that clear AI acceptable-use policies were associated with a 451% increase in AI adoption, dedicated learning time with a 131% increase, and transparent communication with an 11.4% increase [[12]](references.md#ref-12). These are DORA's modelled estimates from survey data, not experimental effects.
- **Concern and trust.** Nearly 15% of DORA respondents expected AI to harm their careers, which DORA suggests may drive reactive rather than genuine adoption [[11]](references.md#ref-11). Outside Google, 39% of surveyed developers trusted the quality of AI output only a little or not at all, and developers who trust AI more use it more [[13]](references.md#ref-13).
- **A worked case.** AT&T scaled Microsoft 365 Copilot to more than 18,000 active users in six weeks, with 96.4% sustained adoption among assigned users. It first defined adoption as at least one active use in 30 days, monitored daily, and treated that as a floor rather than a ceiling. It ran more than 200 live training sessions, routed job-displacement concerns to supervisors with prepared talk tracks, and built a deliberately conservative ROI method from surveys, focus groups and usage data [[9]](references.md#ref-9). The case is published by a change-management vendor and concerns a general productivity assistant, not an engineering tool.
- **Champion networks.** Prosci reports that organisations deploying change agent networks met or exceeded their objectives more often than those that did not [[10]](references.md#ref-10). I found no verified evidence for a specific champion-to-staff ratio ([Section 9](#9-limitations-and-evidence-gaps)).
- **Usage targets.** In June 2026 DORA warned that rewarding raw AI token consumption may nudge hesitant developers to experiment, but that treating token spend as a performance indicator is a trap [[14]](references.md#ref-14).

*Evidence grades: B [[11]](references.md#ref-11)[[12]](references.md#ref-12)[[13]](references.md#ref-13); C [[9]](references.md#ref-9)[[10]](references.md#ref-10)[[14]](references.md#ref-14).*

### 3.5 Quality engineering and agentic testing

Quality engineering is where AI output most needs an independent check, and the evidence shows that checking is often thin.

- **Use cases and barriers.** AI use in quality engineering is shifting from analysing outputs, such as defect analysis, to shaping inputs, with test case design and requirements refinement now leading adoption. The most cited barriers in 2025 were data privacy risk (67%), integration complexity (64%) and hallucination and reliability concerns (60%). In 2024 they were lack of a validation strategy (50%), insufficient AI skills (42%) and an undefined quality engineering organisation (41%). Half of respondents reported lacking AI and machine learning expertise [[8]](references.md#ref-8).
- **Tests in agent-written pull requests.** A study presented at MSR 2026 of about 33,600 agent-generated pull requests found that test inclusion rose from 31% to 52% over time. Pull requests containing tests were larger and took longer, with broadly similar merge rates. The study did not evaluate test quality, adequacy or coverage [[16]](references.md#ref-16).
- **Coverage of agent-written changes.** A July 2026 preprint analysed 4,882 agent-generated pull requests from five agents. Agents included test changes in 49.6% of pull requests that changed code under test. Existing tests covered 61.5% of changed executable lines in Java but only 27.0% in Python, where 64.8% of pull requests had no changed line executed by any existing test. Agent-written tests improved coverage in a minority of pull requests: 35.9% in Java and 22.5% in Python [[17]](references.md#ref-17).
- **Practitioner guidance.** One 2026 pilot guide argues that an independent oracle should be the architectural centre of agentic testing: agents discover and draft, while deterministic checks and accountable people decide whether software passes. It advises counting accepted evidence and defects caught, not files generated [[18]](references.md#ref-18). For AI products, a 2026 conference account argues that exact-match oracles fail for non-deterministic behaviour and proposes checking a bounded behavioural envelope covering preserved intent, policy adherence and an explainable trace [[20]](references.md#ref-20).

The review located no independent controlled study of agentic QA or self-healing test frameworks ([Section 9](#9-limitations-and-evidence-gaps)). *Evidence grades: B [[8]](references.md#ref-8)[[16]](references.md#ref-16)[[17]](references.md#ref-17); C [[18]](references.md#ref-18)[[20]](references.md#ref-20).*

### 3.6 UK legal and workforce considerations

Personal data and staff consultation shape what can be adopted and how fast. The ICO's guidance on generative AI, as summarised by a law firm, states that data protection compliance is not optional where personal data is processed. It points to a data protection impact assessment, to Article 22 of the UK GDPR where AI supports automated decision-making, and to clear staff guidance on what may be shared with these tools [[19]](references.md#ref-19). The summary dates from 2023, so current requirements should be confirmed with the organisation's data protection officer or legal counsel. DORA's finding that job-displacement concern affects adoption [[11]](references.md#ref-11) supports early engagement with employee representatives where they exist (*Judgement*). *Evidence grade: C.*

### 3.7 Evidence from the last six months

The newest evidence, almost all of it produced by vendors, shows adoption near saturation, per-change risk stabilising, and the verification burden moving towards QA and operations. It was gathered after the main review and updates several findings above.

- **Adoption and agents.** DX reports industry AI adoption of 93% in its Q1 2026 report [[24]](references.md#ref-24). In Stack Overflow's 2026 survey, 17.2% of developers did not use AI tools and 26.2% used automated agent workflows [[26]](references.md#ref-26). McKinsey's September 2026 survey found 40% of respondents from large organisations scaling AI agents, up from 27% a year earlier, and about two in ten respondents scaling coding agents [[25]](references.md#ref-25). In testing, one survey series shows the trajectory: 60% of 2024 participants did not use AI for testing [[30]](references.md#ref-30), 45.65% had not integrated it by 2025 [[31]](references.md#ref-31), and 76.8% of testers reported using AI in 2026 [[21]](references.md#ref-21).
- **Policy gap.** Only 24% of Stack Overflow's 2026 respondents said their employer had published approved tools or formal AI guidance, and 29.7% said AI use was optional and left to the individual [[26]](references.md#ref-26). This supports Practice 1 in [Section 4](#4-practices-common-to-both-contexts).
- **Value at organisation level.** McKinsey found 37% of respondents attributing some EBIT impact to AI, about the same as in 2025, despite more organisations scaling [[25]](references.md#ref-25). DX's Q2 2026 report found heavy users saving over 6 hours a week (self-reported) and median throughput up 37% over four quarters, from 1.42 to 1.94 pull requests per engineer per week, while the share of time on new feature work held at roughly 57% to 58% [[24]](references.md#ref-24). Faros's April 2026 telemetry showed epics completed per developer up 66% and task throughput up 33.7% [[22]](references.md#ref-22).
- **Quality and stability.** Faros's April 2026 report found bugs per developer up 54% and the incidents-to-pull-request ratio up 242.7%, comparing each organisation's lowest and highest AI adoption periods [[22]](references.md#ref-22). Its September 2026 follow-up examines the latest 12 months as organisations deepened already-high adoption. It found incidents per pull request up only 14.5%, with deployment frequency and code churn improving, but monthly incidents up 125.4%, time in QA up 300.6% and average pull request size up 71.8% [[23]](references.md#ref-23). Faros states that its findings are correlational [[23]](references.md#ref-23).
- **Review and verification.** Faros reported pull requests merged without review up 31.3% in April [[22]](references.md#ref-22) and gives the figure as 76.3% in September [[23]](references.md#ref-23). Its article and its FAQ describe this differently (a rise versus a share of pull requests), so the figure should not be quoted without checking the full report. A survey by Coleman Parkes for Undo, which sells debugging tools, found 35% of AI-generated code reaches production before the team fully understands it [[27]](references.md#ref-27), and 79% of engineering leaders said release cycles were no faster [[28]](references.md#ref-28). A Lightrun survey of 200 SRE and DevOps leaders found 43% of AI-generated code needed manual debugging in production, including code that had passed QA or staging tests [[29]](references.md#ref-29).
- **A possible countermeasure.** Faros reports that many companies run AI review on 50% to 80% of pull requests, and that heavy users of agentic review show faster first reviews and lower change failure rates. It describes this as correlational, and unreviewed merges kept rising even where adoption was high [[23]](references.md#ref-23).
- **A contested claim.** DORA's survey-based position is that strong foundations amplify AI's benefits and protect against its downsides [[1]](references.md#ref-1). Faros's telemetry-based report states that high-performing organisations saw the same downstream deterioration as others [[22]](references.md#ref-22). Surveys and telemetry measure different things, and Faros sells measurement software. The amplifier claim is therefore supported by survey evidence and contested by telemetry.
- **What has not changed.** I found no new controlled trial since METR's February and May 2026 releases [[5]](references.md#ref-5)[[6]](references.md#ref-6), so the controlled evidence is now the oldest part of the picture. I did not locate a 2026 edition of DORA's flagship report. The ROI report was covered in May 2026 [[2]](references.md#ref-2).

*Evidence grades: B, or C where a figure is only second-hand or ambiguous. Sources here are mostly vendor or consultancy produced, none is peer reviewed, and the relationships are correlational.*

## 4 Practices common to both contexts

Eight practices should be identical in both organisations, because the evidence for them does not depend on company age or size. Each is tagged with its basis.

| # | Practice | What to do | Basis |
| --- | --- | --- | --- |
| 1 | Publish a clear, written AI stance | One page: permitted tools, data rules, what is encouraged, who owns AI-generated changes, and an explicit statement that usage volume is not a target. | DORA capability [[1]](references.md#ref-1); policy association [[12]](references.md#ref-12); usage-target warning [[14]](references.md#ref-14) |
| 2 | Treat adoption as organisational change | Sponsor, communications, supervisor briefings, reinforcement. Do not treat it as a licence rollout. | Prosci [[9]](references.md#ref-9) |
| 3 | Make verification the design centre | Name accountable owners of the independent oracle, the means of deciding whether output is correct. Gate AI output with deterministic checks. | DORA verification tax [[2]](references.md#ref-2); agentic test gaps [[17]](references.md#ref-17); practitioner guidance [[18]](references.md#ref-18) |
| 4 | Protect learning time and tie it to real work | Scheduled hours, real tasks, shared use cases, not generic demonstrations. | DORA learning-time association [[12]](references.md#ref-12) |
| 5 | Work in small batches and plan review capacity | Cap change size. Measure review wait. Staff review as the bottleneck it becomes. | DORA capability [[1]](references.md#ref-1); LinearB telemetry [[7]](references.md#ref-7) |
| 6 | Use peer champions and visible examples | Champions chosen by function, not seniority. Weekly sharing of what worked and what failed. | Prosci [[10]](references.md#ref-10); AT&T case [[9]](references.md#ref-9). Ratios are *Judgement* |
| 7 | Address people's concerns explicitly | Talk about deskilling, job security and trust early, through supervisors as well as leaders. | DORA [[11]](references.md#ref-11)[[13]](references.md#ref-13); AT&T [[9]](references.md#ref-9) |
| 8 | Baseline first, measure outcomes, budget for a dip | Capture the starting position before expansion. Judge on delivered outcomes. Fund the early dip deliberately. | LinearB [[7]](references.md#ref-7); DORA [[2]](references.md#ref-2)[[3]](references.md#ref-3); METR [[4]](references.md#ref-4)[[5]](references.md#ref-5)[[6]](references.md#ref-6) |

Two cautions apply to every row (Judgement). First, the evidence is strongest for practices 1, 4, 5 and 8 and weakest for practice 6, where I found only a vendor-reported association [[10]](references.md#ref-10). Second, no single practice substitutes for the others: DORA's capabilities are presented as a set [[1]](references.md#ref-1).

## 5 Context A: established organisation

In an established organisation with a mixed estate, the first task is to match AI to the right work and the right people, then scale through peers and pairing rather than mandates. The plan below is the author's synthesis of the evidence in [Section 3](#3-findings-what-the-evidence-shows); no single study tested it end to end.

### 5.1 Starting condition and what the evidence implies

Three working hypotheses follow from the evidence (Judgement). Each should be tested in the pilot rather than assumed.

1. **Large legacy systems are the hardest terrain for coding assistance.** METR's 2025 trial found a slowdown for experienced developers in mature, familiar repositories [[4]](references.md#ref-4), and the Stanford analysis reported the smallest gains on complex brownfield work [[15]](references.md#ref-15). Neither result proves legacy systems are a poor target with 2026 tools; both justify testing them separately from newer standalone components.
2. **Test-adjacent work is the best-supported starting point.** Test case design and requirements refinement now lead quality engineering adoption [[8]](references.md#ref-8), and these tasks do not require repository access.
3. **The workforce divides by confidence, not motivation.** Motivation to use AI was nearly identical in succeeding and stalling organisations [[9]](references.md#ref-9), so enablement should matter more than persuasion.

### 5.2 Phased plan

Timings are indicative (Judgement).

| Phase | Timing | Actions | Exit evidence |
| --- | --- | --- | --- |
| 0. Foundation and baseline | Weeks 0 to 8 | Publish the one-page AI stance. Segment the estate by work type (legacy system maintenance, newer standalone components, test-adjacent activity) and by role. Capture 8 to 12 weeks of existing delivery, review and quality data. Run a baseline survey of current use, confidence, trust and concerns. Consult employee representatives and the data protection lead. Agree a budget that expects an early dip [[2]](references.md#ref-2)[[3]](references.md#ref-3). | Stance published. Baseline dashboard exists. Pilot cells and hypotheses agreed in writing. |
| 1. Pilot | Weeks 8 to 24 | Run two to three pilot cells with staggered starts: a team working on newer standalone components; a QA-led cell using AI for test design and regression triage around legacy systems; and a cell of staff new to AI on the first two rungs of the ladder ([Section 5.3](#53-the-skills-ladder-for-staff-without-repository-experience)). One named champion per cell. Protected learning time. Weekly sharing of results. Tag AI-assisted and unassisted changes separately [[7]](references.md#ref-7). Plan review capacity in advance. | Pre-agreed thresholds on flow, quality and trust met against baseline. A written list of use cases that worked and that did not. |
| 2. Scale | Months 6 to 12 | Extend cell by cell, again staggered. Add a champion per team. Introduce pairing. Publish a use-case library from the pilots. Brief supervisors with talk tracks on job and skills concerns [[9]](references.md#ref-9). Introduce agentic QA only where a trustworthy oracle exists, for example stable regression suites and API checks. | Delivered outcomes at parity or better. No rise in escaped defects. Adoption depth growing by use case, not only by user count. |
| 3. Embed | Months 12 to 18 | Update standards: definition of done, pull request templates, test strategy, role descriptions and learning pathways. Review quarterly. Retire initiatives that miss thresholds. Refresh the stance as tools change [[9]](references.md#ref-9). | Outcomes sustained for two consecutive quarters. |

### 5.3 The skills ladder for staff without repository experience

Staff who do not work with source repositories can start at rung 1 and never need to touch one to benefit. The ladder is a design proposal (Judgement); the underlying rationale is that AI work needs judgement about when to use it and how to evaluate output [[9]](references.md#ref-9).

| Rung | Activity | Repository access needed |
| --- | --- | --- |
| 1. Use | Apply AI to documents the person already owns: requirement review, test case review, test data ideas, defect report drafting. | No |
| 2. Verify | Check AI output against domain knowledge. Log every error found. The log becomes team evidence about reliability. | No |
| 3. Direct | Build reusable prompts and context packs for recurring tasks. Share them in the use-case library. | No |
| 4. Build | Pair with a champion on test automation or agent-assisted testing, inside the organisation's approved environment. | Yes, with a pairing partner |

Experienced testers and domain specialists hold the domain knowledge that functions as the oracle. Positioning them as verifiers of AI output, rather than as people to be replaced, is consistent with DORA's finding that addressing concerns in clear terms lets staff concentrate on learning [[11]](references.md#ref-11).

### 5.4 Risks specific to this context

- **Piloting in the wrong terrain.** A disappointing result from legacy systems could be misread as evidence that AI does not work. Segment results by work type [[15]](references.md#ref-15).
- **Mistaking perception for evidence.** Enthusiastic self-report is expected and should be checked against delivered outcomes [[4]](references.md#ref-4)[[6]](references.md#ref-6).
- **Review queues.** More generated change can wait longer for review [[7]](references.md#ref-7). Plan capacity before expansion.
- **Quiet resistance.** At AT&T, concerns surfaced in pockets rather than broadly [[9]](references.md#ref-9). Use supervisors and champions to surface them early.
- **Usage targets.** Do not set them; DORA describes treating token spend as a performance indicator as a trap [[14]](references.md#ref-14).
- **Data handling.** Where the organisation processes personal or regulated data, confirm the position with data protection and compliance leads before widening access [[19]](references.md#ref-19).

## 6 Context B: early-stage start-up

In a young company the opportunity is to make verification a default before habits form, and the risk is that delivery speed outruns assurance. Because AI amplifies the system it enters [[1]](references.md#ref-1)[[2]](references.md#ref-2), a company with few foundations will amplify the gaps. The plan below is the author's synthesis of [Section 3](#3-findings-what-the-evidence-shows) (Judgement).

### 6.1 Starting condition and what the evidence implies

1. **There is no resistance to overcome, but also no baseline.** Prior delivery and quality data may be thin, so measurement must be built, not retrieved ([Section 8](#8-baselining-and-evaluation-framework)).
2. **Foundations come first.** DORA's capabilities include strong version control, small batches, quality internal platforms and AI-accessible internal data [[1]](references.md#ref-1). These are plausibly cheaper to establish in a young company than in a large one (Judgement).
3. **Quality assurance may have two jobs.** It must assure AI-assisted engineering. Where the product itself contains AI components, it must also test non-deterministic behaviour, which practitioners argue needs behavioural-envelope oracles rather than exact-match checks [[20]](references.md#ref-20) (Grade C).
4. **Agentic QA needs an independent check.** In one 2026 preprint, agents included test changes in under half of the qualifying pull requests [[17]](references.md#ref-17), and practitioner guidance places the independent oracle at the centre of agentic testing [[18]](references.md#ref-18).

### 6.2 Phased plan

Timings are indicative (Judgement).

| Phase | Timing | Actions | Exit evidence |
| --- | --- | --- | --- |
| 0. Stance and foundations | Days 0 to 30 | Publish the AI stance. Confirm data handling, including customer data and UK GDPR obligations [[19]](references.md#ref-19). Set defaults for version control, small changes, continuous integration and rollback [[1]](references.md#ref-1). Appoint a named verification lead who owns the oracle for each product behaviour. Start instrumenting delivery, review and defect data. | Stance and data rules published. Verification lead named. Instrumentation live. |
| 1. Baseline and evaluation | Days 30 to 90 | Treat this period as the baseline. Where the product contains AI components, build an evaluation set: representative cases with human-agreed expected behaviour and a defined acceptable envelope. Pilot agentic QA in a drafting and exploring role, behind deterministic gates. Inject known defects and record whether the suite catches them. | Baseline report. Evaluation set in regular use. First measured agentic QA results. |
| 2. Embed in defaults | Days 90 to 180 | Build AI practice into onboarding, pull request templates and the definition of done. Appoint a champion per squad. Hold weekly sharing of what worked and failed. Schedule protected learning time [[12]](references.md#ref-12). Require review of agent-created changes by a named owner [[7]](references.md#ref-7). | Every new starter trained in the stance and verification method. No agent-created change merged without a named owner. |
| 3. Scale by risk | After day 180 | Extend agentic QA to areas in proportion to risk and oracle quality. Review cost, defect-detection and maintenance quarterly. Retire what fails thresholds. Refresh the stance as tools change [[9]](references.md#ref-9). | Outcomes sustained for two consecutive quarters against baseline. |

### 6.3 Designing agentic QA with an independent check

The design principle is that agents may explore and draft, but accountable people and deterministic checks decide whether software has passed [[18]](references.md#ref-18). Concretely (Judgement):

- **Agents** explore the product, propose test ideas and draft tests.
- **Deterministic gates** run the accepted tests, evidence collection and release thresholds without an agent in the decision.
- **Accountable people** own the oracle for each behaviour and accept or reject agent-drafted tests.
- **Known-defect checks** inject faults and measure whether the suite detects them, which exposes false confidence.
- **Evidence trail** records what was run, by whom, against which version.

The review located no independent controlled evidence that self-healing test frameworks deliver measurable benefit at scale ([Section 9](#9-limitations-and-evidence-gaps)). Treat them as unproven, and fix brittle test design before buying repair tooling.

### 6.4 Risks specific to this context

- **Speed without verification.** More code, faster, with the same review capacity creates queues and instability [[2]](references.md#ref-2)[[7]](references.md#ref-7).
- **Key-person dependence.** A single verification lead is a single point of failure. Document oracles so that knowledge outlasts the person (Judgement).
- **Customer data in tools.** Customer or personal data may pass through AI tools. Settle data rules before wider tool access [[19]](references.md#ref-19).
- **Adoption without value.** At a small scale, enthusiasm can mask unmeasured outcomes. Baseline from the first day [[7]](references.md#ref-7).

## 7 Comparative analysis

The two contexts share a spine of eight practices and differ mainly in what comes first, what is scarce, and where the baseline comes from. The table separates what the evidence supports from what is the author's judgement.

| Dimension | Context A: established | Context B: early-stage | Basis |
| --- | --- | --- | --- |
| Starting condition | Habits, legacy code, uneven skills | Blank slate, thin history, few guardrails | Description of the two contexts |
| Primary risk | Piloting in the wrong terrain; stalled adoption | Speed outrunning verification | [[4]](references.md#ref-4)[[15]](references.md#ref-15) for A; [[2]](references.md#ref-2)[[7]](references.md#ref-7)[[17]](references.md#ref-17) for B |
| First move | Segment the estate by work type and role; baseline from history | Stance, foundations, instrumentation from day one | [[1]](references.md#ref-1)[[7]](references.md#ref-7); Judgement |
| Adoption mechanism | Champions, pairing, skills ladder, supervisor talk tracks | Defaults in onboarding, templates and definition of done | [[9]](references.md#ref-9)[[10]](references.md#ref-10); Judgement |
| Role of champions | Essential to cross a large, varied workforce | Lighter touch; one per squad | [[10]](references.md#ref-10); ratios are Judgement |
| Where AI is applied first | Newer standalone components and test-adjacent work | Everywhere, but behind deterministic gates | [[8]](references.md#ref-8)[[15]](references.md#ref-15); Judgement |
| QA focus | Protect existing quality while adding AI-assisted checks | Build evaluation sets and oracles into the product | [[18]](references.md#ref-18)[[20]](references.md#ref-20); Judgement |
| Agentic QA | Only where a trustworthy oracle already exists | Designed in with an independent check from the start | [[17]](references.md#ref-17)[[18]](references.md#ref-18); Judgement |
| Governance | Consult representatives; align with compliance and data protection | Settle customer data rules first | [[11]](references.md#ref-11)[[19]](references.md#ref-19); Judgement |
| Baseline source | 8 to 12 weeks of existing delivery and review data plus survey | First 90 days of newly instrumented data | [[7]](references.md#ref-7); Judgement |
| Pace and horizon | Staged over 12 to 18 months | Fast but gated, with review at 90 and 180 days | Judgement |
| Success signal | Outcomes at parity or better across segments, sustained | Verification embedded as default; outcomes stable as volume grows | [[2]](references.md#ref-2)[[7]](references.md#ref-7); Judgement |

The central asymmetry is that Context A has history but friction, while Context B has speed but no history. Context A should spend its early effort on enablement and segmentation. Context B should spend its early effort on verification and instrumentation. Both converge on the same discipline: decide on delivered outcomes against a baseline.

## 8 Baselining and evaluation framework

Both organisations should baseline before expanding, measure delivered outcomes across several layers, and decide against thresholds agreed in advance. Usage counts alone are not evidence of value.

### 8.1 Principles

1. **Baseline first.** LinearB advises capturing cycle time by phase, pull request size, acceptance rate and rework rate while current adoption is steady. It links the absence of a baseline to the finding that 44.7% of organisations do not formally measure AI impact while 76.1% of leaders report gains from adoption signals [[7]](references.md#ref-7).
2. **Segment by contribution type.** Keep agent-created, AI-assisted and unassisted changes separate, because blended averages describe none of them [[7]](references.md#ref-7).
3. **Judge outcomes, not activity.** Token counts and usage leaderboards are not performance measures [[14]](references.md#ref-14). Count accepted evidence and defects caught, not artefacts generated [[18]](references.md#ref-18).
4. **Do not rely on self-report alone.** Self-assessed gains overstated measured effects in METR's work [[4]](references.md#ref-4)[[6]](references.md#ref-6).
5. **Expect and budget for a dip.** Evaluate over a window long enough to pass the learning curve, and set its length in advance [[2]](references.md#ref-2)[[3]](references.md#ref-3) (Judgement on length).
6. **Use staggered rollout as the comparison.** Compelling staff to work without AI is increasingly impractical [[5]](references.md#ref-5), so later-starting cells act as the comparison group (Judgement).

### 8.2 Measures by layer

| Layer | Example measures | Data source | Caution |
| --- | --- | --- | --- |
| 1. Adoption depth | Weekly active use by role and use case; share of work items using AI, by use case; share of AI use that is verified | Tool analytics, work tracker tags, survey | Activity is not value. AT&T treated active use as a floor [[9]](references.md#ref-9). Avoid token leaderboards [[14]](references.md#ref-14) |
| 2. Flow | Lead time by phase; change size; pickup and review time; acceptance (merged within 30 days) by contribution type; deployment frequency; share of changes merged without review; time in QA | Source control, pipeline, work tracker | Correlational. Segment by contribution type [[7]](references.md#ref-7). Recent telemetry reports unreviewed merges and time in QA rising [[23]](references.md#ref-23) |
| 3. Quality and stability | Change failure rate; deployment rework rate; escaped defects; time to restore; flaky test rate; incidents per change and monthly incident volume | Incident, defect and pipeline data | DORA associates AI adoption with more instability [[2]](references.md#ref-2). DORA added deployment rework rate to its Quick Check in April 2026 [[14]](references.md#ref-14) |
| 4. Agentic QA effectiveness | Share of agent-drafted tests accepted; defects caught per accepted test; known-defect detection rate; coverage of changed lines; human review time per accepted test; maintenance effort | Test management, coverage tools, known-defect runs | Accepted evidence over generated volume [[18]](references.md#ref-18). Coverage alone does not show adequacy. Known-defect detection is Judgement |
| 5. People | Trust, confidence, workload, skills; concern about deskilling and job security | Quarterly pulse survey | Trust is associated with use [[13]](references.md#ref-13). Surveys carry self-report bias [[6]](references.md#ref-6) |
| 6. Cost and value | Licence and usage cost; review and verification time; value of time released | Finance, sampled time-use | Use conservative, auditable assumptions as AT&T did [[9]](references.md#ref-9). DORA describes its ROI calculations as high-uncertainty estimates and recommends conservative, realistic and optimistic scenarios [[2]](references.md#ref-2) |

### 8.3 Establishing the baseline in each context

- **Context A.** Use 8 to 12 weeks of existing delivery, review and defect history, held steady while the baseline is captured, and a first survey of use, trust and concerns (Judgement on duration; the principle follows [[7]](references.md#ref-7)). Define pilot segments before looking at results.
- **Context B.** Treat the first 90 days of newly instrumented data as the baseline and compare each cohort with its own earlier trajectory (Judgement). DORA's Quick Check offers an external reference point for delivery performance [[14]](references.md#ref-14).

### 8.4 Judging an initiative

1. Before the pilot, write the hypothesis, the measures, the expected direction, and a stop, continue or scale rule.
2. Define segments in advance: work type and contribution type.
3. Run for the full window and expect an early dip [[2]](references.md#ref-2).
4. Compare with the baseline and with later-starting cells.
5. Triangulate delivered data, survey results and qualitative review of sampled work.
6. Decide by the pre-agreed rule and record the decision and its rationale.

An illustrative decision rule follows. The thresholds must be set locally and in advance (Judgement).

| Observation | Decision |
| --- | --- |
| Flow improves or holds; quality and stability hold; trust stable or rising | Scale |
| Flow improves; quality or stability worsens | Pause. Fix verification and review capacity before scaling |
| Flow and quality flat after the learning window; trust falling | Stop or redesign |
| Results differ by segment | Continue only in the segments that pass |

## 9 Limitations and evidence gaps

Confidence in the conclusions is moderate, and executives should read the recommendations as informed judgement rather than proven method. The main limitations are these.

1. **Source independence.** Much of the quantitative evidence is survey or telemetry produced by vendors or sponsors: LinearB [[7]](references.md#ref-7), the OpenText-sponsored World Quality Report [[8]](references.md#ref-8), Prosci [[9]](references.md#ref-9)[[10]](references.md#ref-10), Faros [[22]](references.md#ref-22)[[23]](references.md#ref-23), DX [[24]](references.md#ref-24), Undo [[27]](references.md#ref-27)[[28]](references.md#ref-28), Lightrun [[29]](references.md#ref-29) and Google Cloud's DORA programme [[1]](references.md#ref-1)[[2]](references.md#ref-2)[[12]](references.md#ref-12). Most relationships reported are correlational, as LinearB itself states [[7]](references.md#ref-7).
2. **METR studies.** The 2025 trial had 16 developers [[4]](references.md#ref-4). The 2026 follow-up was judged unreliable by its own authors because of selection effects [[5]](references.md#ref-5). Neither setting is a corporate product team.
3. **Stanford figures.** They come from a conference talk. I did not locate a peer-reviewed publication [[15]](references.md#ref-15). The figures appear in the DORA ROI report as summarised by InfoQ, with slightly different ranges [[2]](references.md#ref-2).
4. **Case evidence.** The AT&T example is published by a change-management vendor and concerns a general productivity assistant [[9]](references.md#ref-9). Evidence for champion networks is a vendor-reported association [[10]](references.md#ref-10). I found no verified champion-to-staff ratio, so ratios in this report are judgement.
5. **Partial access to some sources.** The DORA ROI report was read through its landing page [[3]](references.md#ref-3) and InfoQ coverage [[2]](references.md#ref-2), not in full. The World Quality Report was read through its press release [[8]](references.md#ref-8). The DORA 2025 findings were read through Google Cloud's summary [[1]](references.md#ref-1). Several practitioner and preprint sources were read as abstracts or excerpts [[16]](references.md#ref-16)[[17]](references.md#ref-17)[[18]](references.md#ref-18)[[19]](references.md#ref-19)[[20]](references.md#ref-20). The Stack Overflow, Undo, Lightrun and PractiTest figures [[21]](references.md#ref-21)[[26]](references.md#ref-26)[[27]](references.md#ref-27)[[28]](references.md#ref-28)[[29]](references.md#ref-29)[[30]](references.md#ref-30)[[31]](references.md#ref-31) were read through trade-press coverage. The Faros articles were read in full but not the full reports, and the DX and McKinsey pages were read as excerpts.
6. **Agentic QA.** The review located no independent controlled study of agentic QA effectiveness or of self-healing test frameworks. Absence from this review is not proof of absence. One practitioner source asserts that independent evidence is lacking [[21]](references.md#ref-21).
7. **Test studies are descriptive.** The MSR study did not evaluate test quality, adequacy or coverage [[16]](references.md#ref-16). The coverage preprint is not yet peer-reviewed [[17]](references.md#ref-17).
8. **Legal position.** The ICO material is a 2023 law-firm summary [[19]](references.md#ref-19). It is not legal advice. Current requirements must be confirmed with the organisation's data protection officer or counsel.
9. **Currency.** The field changes quickly. METR itself marked its 2025 result out of date within a year [[4]](references.md#ref-4)[[5]](references.md#ref-5). Evidence is current to 10 October 2026.
10. **Exclusions.** Claims that could not be traced to a primary or clearly attributable secondary source were excluded. These included several widely repeated champion-programme statistics and some calculator defaults.
11. **Applicability.** Neither context is a specific named organisation. Local data, regulation and culture will change the plan.

## 10 Conclusions and recommendations

AI adoption should be run as a verification-led change programme in both contexts, and the evidence does not support mandates, usage targets, or reliance on self-reported gains.

**Conclusions.**

1. Adoption is no longer the constraint; converting it into delivered value is [[7]](references.md#ref-7)[[8]](references.md#ref-8)[[9]](references.md#ref-9).
2. Foundations and verification decide whether faster generation becomes faster delivery [[1]](references.md#ref-1)[[2]](references.md#ref-2)[[7]](references.md#ref-7).
3. The two contexts differ in their first move, not in their discipline. Context A leads with segmentation and enablement. Context B leads with foundations and instrumentation (Judgement).
4. Evidence for agentic QA effectiveness is immature, so it should be designed with an independent check and measured on accepted evidence [[17]](references.md#ref-17)[[18]](references.md#ref-18).

**Recommendations for executive decision.**

1. Endorse a written AI stance with a named executive owner [[1]](references.md#ref-1)[[12]](references.md#ref-12).
2. Approve protected learning time and an explicit budget for an early productivity dip [[2]](references.md#ref-2)[[3]](references.md#ref-3)[[12]](references.md#ref-12).
3. Approve a baseline period before wider rollout: about 8 to 12 weeks of history in Context A, the first 90 days of new instrumentation in Context B (Judgement on durations) [[7]](references.md#ref-7).
4. Adopt outcome-based measurement ([Section 8.2](#82-measures-by-layer)) and do not use usage or token counts as performance targets [[14]](references.md#ref-14).
5. Name accountable owners of verification, and require a named owner for every agent-created change [[7]](references.md#ref-7)[[18]](references.md#ref-18).
6. Fund review capacity alongside generation capacity [[7]](references.md#ref-7).
7. In Context A, pilot first on newer standalone components and test-adjacent work, with a skills ladder for staff who do not work with source code. In Context B, appoint a verification lead and build evaluation sets within 90 days (Judgement).
8. Engage employee representatives, data protection and compliance leads before widening tool access [[11]](references.md#ref-11)[[19]](references.md#ref-19).
9. Review the evidence and the plan quarterly, because the field is moving quickly [[5]](references.md#ref-5).

A suitable next step is to agree pilot hypotheses, measures and decision rules in writing before any tool is expanded.
