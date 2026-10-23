# Task 5 — Tabletop Exercise and Improvement Plan

> Extracted from the complete ICDFA GRC105 assignment. Content is organised by task; tables and source terminology are retained as Markdown where possible.

## 7	Task 5 — Tabletop Exercise and Improvement Plan

Status: Fictional individual tabletop design and simulated outcome record — awaiting independent review.
Duration: 60 minutes.
Scenario point: High — provisional suspected ransomware incident, Day 0, with the 11:00 examination dependency.

### 7.1	Exercise purpose and boundaries

This tabletop tests the approved Task 1 assessment, Task 2 governance, Task 3 response playbook and Task 4 communication controls. It is an individual simulation in which the analyst takes the role of each functional participant. Every decision and result is simulated; it is not a record of live response, system restoration, evidence collection or notification.

### 7.2	Objectives

Test whether the team preserves evidence while controlling active encryption and privileged-account risk.

Test whether the Incident Response Lead, IT Operations, Security Analyst, BCC and Academic/Business Service Owner make distinct decisions under the 11:00 deadline.

Test backup uncertainty and the prohibition on unsafe restoration.

Test fact-bounded communications when a data-theft claim and media query are unverified.

Produce measurable preparation improvements for backup, communications, monitoring, training and closure discipline.

### 7.3	Participants and roles

| Participant role | Exercise responsibility |
| --- | --- |
| Incident Response Lead | Directs the simulated incident, authorises normal containment, records decisions and escalates material risk. |
| Security Analyst | Analyses evidence maintains uncertainty and validates security conditions. |
| IT Operations and Recovery Lead | Performs simulated technical assessment, backup validation and recovery decisions within authority. |
| Digital Forensics/Evidence Custodian | Preserves planned evidence and identifies custody or evidence-loss concerns. |
| Business Continuity Coordinator | Coordinates authorised continuity options and learner-service planning. |
| Academic/Business Service Owner | Decides whether an examination arrangement is acceptable within approved parameters. |
| Senior Management / Executive Sponsor | Accepts material institutional risk, approves material exceptions and communications. |
| Legal/Privacy Adviser | Advises on data claims, evidence confidence and possible reporting obligations. |
| Communications Coordinator | Drafts fact-bounded internal and external messages and records approval. |

The role set is functional; it does not imply that Northbridge has nine dedicated employees.

### 7.4	Agenda and injects

| Minute | Activity |
| --- | --- |
| 0–5 | Briefing, assumptions, role assignment and success criteria. |
| 5–10 | Review E01–E08 and establish the simulated situation record. |
| 10 | Required inject 1: management requests reopening before the 11:00 examination despite unverified backup safety. |
| 20 | Required inject 2: an attacker claims possession of all 1,800 learner records; screenshot authenticity is uncertain. |
| 35 | Required inject 3: the latest network backup fails a simulated test restoration with an unreadable snapshot error. |
| 45 | Required inject 4: social media claims cancellation and a journalist asks about learner-information exposure. |
| 50 | Additional inject: Microsoft 365 audit export is delayed and the finance officer cannot immediately confirm the unfamiliar sign-in. |
| 55–60 | Closure discipline, corrective actions, debrief and simulated handover to post-incident review. |

The editable timeline is tabletop-timeline.mmd.

### 7.5	Measurable success criteria

By minute 10, the simulated record identifies E01–E08, the High provisional classification, the examination dependency, the unverified backup position and at least three unresolved questions.

By minute 20, the participants preserve the attacker claim as unverified, assign a Legal/Privacy assessment and avoid stating that learner records were stolen.

By minute 35, the participants reject restoration from the failed or unvalidated source and record an alternative continuity path.

By minute 45, the participants produce an approved fact-bounded holding message without confirming cancellation or data exposure.

By minute 60, every simulated decision has an owner, rationale, communication, effect and follow-up record, and at least five corrective actions are assigned.

### 7.6	Individual simulated decision walkthrough

The detailed decision log is data/exercise-decision-log.csv. The six outcomes are labelled Individual simulated tabletop outcome and are not evidence from the fictional incident.

#### 7.6.1	Inject 1 — minute 10

The simulated decision is not to reopen LMS01 from an unvalidated backup. The IRL, Senior Management and Academic/Business Service Owner retain separate security, risk and service decisions while the BCC prepares an alternative. This preserves recovery safety and leaves the examination status unresolved until an authorised decision.

#### 7.6.2	Inject 2 — minute 20

The claim and screenshot are preserved for validation. The simulated team does not confirm theft, attacker identity or authenticity. Legal/Privacy receives the potential personal-data issue, while Communications prepares only a fact-bounded holding line.

#### 7.6.3	Inject 3 — minute 35

The simulated unreadable snapshot result blocks use of that candidate recovery source. It does not prove that all backups fail. IT Operations requests specialist support and records recovery uncertainty; BCC and academic operations continue contingency planning.

#### 7.6.4	Inject 4 — minute 45

The simulated team treats the social-media post as a rumour, not an examination decision. Communications prepares an approved holding statement; Legal/Privacy and Senior Management review any external message. No exposure claim is confirmed.

#### 7.6.5	Additional inject — minute 50

The delayed Microsoft 365 export and unavailable finance officer leave E02 unresolved. The simulated response preserves the provider request and uses other planned sources rather than inventing an account-compromise conclusion.

#### 7.6.6	Closure decision — minute 55

The exercise remains under simulated recovery rather than closing. Open evidence, recovery, learner-impact and approval items receive owners and next reviews. The decision tests whether closure is treated as a governance gate rather than an administrative convenience.

### 7.7	Corrective actions and post-incident review

Six proposed corrective actions are recorded in data/corrective-actions.csv. They cover backup testing, alternative communication, server monitoring, dual-hat training, privacy/communications decision support and closure gates. Target completion times are relative to simulated exercise closure and are not claims of implementation.

For this exercise, the simulated post-incident review deadline is within two weeks of simulated incident closure, consistent with the Week 20 lessons-learned teaching point. The Incident Response Lead coordinates the review; Senior Management closes corrective actions after evidence of completion is accepted by the named owner and relevant technical/business reviewer. No actual review or closure has occurred.

### 7.8	Sources and boundaries

ICDFA, GRC105 Incident Response Planning Assignment, Task 5 and rubric.

ICDFA, Incident Response Planning, Week 20 slides 12–13 and 16–18.

Approved Task 1–Task 4 planning artifacts.

NIST, SP 800-61 Rev. 3: https://csrc.nist.gov/pubs/sp/800/61/r3/final

All outcomes in this document are explicitly simulated. No live response, evidence acquisition, backup restoration or communication is represented.

Canonical simulated decision log — inject and decision

| Exercise minute | Inject | Decision | Decision owner |
| --- | --- | --- | --- |
| 10 | Management requests reopening before 11:00 despite unverified backup safety | Do not reopen from an unvalidated backup; prepare alternative examination arrangements | Incident Response Lead / Senior Management / Academic Service Owner |
| 20 | Attacker claims all 1800 learner records and provides uncertain screenshot | Preserve claim evidence and investigate; do not confirm theft or authenticity | Incident Response Lead / Legal Privacy Adviser |
| 35 | Latest network backup test fails with unreadable snapshot error | Hold that recovery source and request specialist validation; reassess alternatives | IT Operations Lead / Incident Response Lead |
| 45 | Social media cancellation rumour and journalist query about exposure | Issue approved holding statement; do not confirm cancellation or exposure | Communications Coordinator / Senior Management |
| 50 | Microsoft 365 export delayed and finance officer unavailable for immediate confirmation | Preserve provider request and keep identity question unresolved; request alternate support | Security Analyst / Incident Response Lead |
| 55 | Facilitator asks whether the exercise can close with recovery questions open | Keep incident under recovery and assign owners and next review | Incident Response Lead |

Canonical simulated decision log — rationale and communication

| Exercise minute | Rationale | Communication |
| --- | --- | --- |
| 10 | E05 does not establish backup safety and security gates cannot be waived | Verified phone briefing; learner update pending approved status |
| 20 | Evidence and authenticity are unresolved | Restricted management update and holding line |
| 35 | The source cannot currently support safe recovery; other sources remain untested | Management and BCC notified; academic owner receives uncertainty |
| 45 | The rumour is not authoritative and disclosure is unproven | Verified phone coordination and approved public statement |
| 50 | Delayed evidence cannot justify attribution or closure | Controlled provider case record and management update |
| 55 | Closure requires evidence, approvals, business acceptance and residual-risk treatment | Participant debrief and protected exercise record |

Canonical simulated decision log — effect and status

| Exercise minute | Effect on response or recovery | Simulation status |
| --- | --- | --- |
| 10 | Recovery remains controlled while continuity planning begins | Individual simulated tabletop outcome |
| 20 | Privacy workstream added without changing confirmed scope | Individual simulated tabletop outcome |
| 35 | Recovery uncertainty increases and unsafe restoration is prevented | Individual simulated tabletop outcome |
| 45 | Reduces misinformation while preserving privacy and approval controls | Individual simulated tabletop outcome |
| 50 | Maintains investigation integrity and avoids premature account-compromise finding | Individual simulated tabletop outcome |
| 55 | Tests closure discipline and creates corrective actions | Individual simulated tabletop outcome |

Canonical corrective-action register — finding and action

| Action ID | Priority | Finding | Corrective action |
| --- | --- | --- | --- |
| CA-01 | Critical | Backup recoverability was uncertain and the simulated test failed | Complete isolated FS01/LMS01 restoration tests with integrity and application checks |
| CA-02 | High | Contact list was unavailable and email trust was uncertain | Maintain independent contacts and rehearse verified phone and alternate-channel identity checks |
| CA-03 | High | Server and provider visibility may be incomplete | Assess and close FS01 LMS01 BAK01 monitoring gaps |
| CA-04 | High | Dual-hatting creates command, evidence and execution conflicts | Run role-based training and repeat tabletop with deputies and decision-log coverage |
| CA-05 | High | Claims and transfer evidence could trigger premature disclosure | Create fact-bounded privacy and communications decision checklist |
| CA-06 | Medium | Closure could occur while recovery and learner-impact questions remain open | Add closure gate for evidence, residual risk, business acceptance and follow-up |

Canonical corrective-action register — ownership

| Action ID | Owner | Target completion |
| --- | --- | --- |
| CA-01 | IT Operations and Recovery Lead with Senior Management approval | Within 30 days of exercise closure |
| CA-02 | BCC / Communications Coordinator | Within 14 days of exercise closure |
| CA-03 | Security Analyst / IT Operations Lead | Within 45 days of exercise closure |
| CA-04 | Incident Response Lead | Within 60 days of exercise closure |
| CA-05 | Legal/Privacy Adviser / Communications Coordinator | Within 30 days of exercise closure |
| CA-06 | Incident Response Lead | Within 30 days of exercise closure |

Canonical corrective-action register — evidence and status

| Action ID | Measurable evidence | Status |
| --- | --- | --- |
| CA-01 | Dated test record with provenance results limitations and decision | Proposed from simulation |
| CA-02 | Exercise retrieves contacts without FS01 and records verified notification | Proposed from simulation |
| CA-03 | Coverage register lists telemetry owners retention and test alert or exception | Proposed from simulation |
| CA-04 | Attendance record, role assignments and success-criteria results reviewed | Proposed from simulation |
| CA-05 | Approved checklist used in a scenario and linked to decision record | Proposed from simulation |
| CA-06 | Updated closure template reviewed in exercise or governance review | Proposed from simulation |
