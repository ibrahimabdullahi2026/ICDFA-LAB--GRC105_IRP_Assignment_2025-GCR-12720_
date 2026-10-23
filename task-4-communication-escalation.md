# Task 4 — Communication and Escalation

> Extracted from the complete ICDFA GRC105 assignment. Content is organised by task; tables and source terminology are retained as Markdown where possible.

## 6	Task 4 — Communication and Escalation

Status: Draft complete — fictional planning artifact awaiting independent review.
Incident position: High — provisional at 08:45 WAT on Day 0.
Communication constraint: Staff phones are available; the FS01 contact list is inaccessible, and corporate email trustworthiness is unverified (E08).

### 6.1	Communication principles

Communications must be fact-bounded, approved, traceable and proportionate to confirmed impact. E01–E08 support the current availability and integrity concerns but do not establish attacker identity, malicious attachment execution, account compromise, backup safety or personal-data theft. Sensitive forensic material must not be sent through an unverified channel.

The principal stakeholder matrix is stakeholder-matrix.csv. It defines eight groups, triggers, owners, channels, approvers, update frequency and alternatives. Verified telephone calls and an independently maintained contact record are the immediate fallback; no secure alternate collaboration platform is assumed to exist.

### 6.2	Executive briefing

At 08:45 WAT on Day 0, Northbridge assumed control of a High—provisional suspected ransomware incident. Confirmed observations include mass file changes on FIN-PC07, .locked files and a ransom note on FS01, inability for learners to open materials or submit assessments through LMS01, and an inaccessible incident contact list (E06–E08). The 11:00 examination for 100 learners is therefore subject to a time-critical continuity decision.

The evidence does not yet prove malicious execution of the payroll attachment, compromise of the finance officer or svc_backup, attacker control, the content of the 1.2 GB HTTPS transfer, theft of learner information, or a clean and restorable backup (E01–E05). Corporate email trust is unverified, so verified telephone calls and controlled records are being proposed for coordination.

Approval is required for any material continuity risk acceptance, external specialist engagement, emergency exception, examination alternative, and return to service. The Incident Response Lead will coordinate containment and evidence preservation; technical restoration, security validation, data integrity and business acceptance remain separate gates. The next management update is targeted for 10:30 WAT, before the examination decision point. This is a proposed briefing, not a record that any action has occurred.

### 6.3	Learner notice

Northbridge is investigating a serious technology incident affecting access to some learning materials and assessment of submission services. We are assessing the impact on the 11:00 WAT examination for the affected learner group. The examination has not been confirmed as cancelled or resumed at the time of this notice.

Please keep your phone available, monitor the next verified Northbridge update, and do not send examination answers or personal information through an unverified email or social media account. If an alternative assessment arrangement is approved, the Academic/Business Service Owner will provide the instructions and any revised submission method through a verified channel. Learners who cannot access materials should record the time and contact the designated support channel when it is published. The next status update is targeted before the examination decision point. This notice reports service uncertainty; it does not confirm that learner information was accessed or stolen.

### 6.4	Operational notifications versus formal breach notifications

Operational notifications explain service status, safety instructions, continuity arrangements and next decision points. They should contain only the minimum information needed by the audience and should not state that personal data was exposed unless supported by evidence.

Any formal personal-data breach assessment is a separate Legal/Privacy workstream. The adviser should assess the facts, affected data categories, jurisdiction, contractual duties, evidence confidence, recipients and any applicable deadlines before management authorises a notification. No jurisdiction-specific deadline is asserted here. The communication log must distinguish a fact-bounded operational message from a formal notification decision and retain approval references.

### 6.5	Escalation rules

The Incident Response Lead escalates to Senior Management when impact, uncertainty, examination disruption, privileged-access concern, backup risk or external support need becomes material.

Legal/Privacy advice is requested when learner or staff information may be involved, when E04 cannot be characterised, or when disclosure obligations are uncertain.

The Academic/Business Service Owner and BCC escalate examination alternatives or material learner impact to Senior Management.

The Communications Coordinator escalates public or media queries; no unapproved external statement is released.

If corporate email cannot be trusted, verified telephone calls and controlled offline records remain the communication baseline until an approved alternative is confirmed.

### 6.6	Sources and boundaries

ICDFA, GRC105 Incident Response Planning Assignment, Task 4 and rubric.

ICDFA, Incident Response Planning, Week 20 slides 8, 10, 13–15 and 18.

Approved Task 1 evidence analysis and Task 2 governance documents.

NIST, SP 800-61 Rev. 3: https://csrc.nist.gov/pubs/sp/800/61/r3/final

No legal deadline, provider response, communication delivery or personal-data finding is claimed.

Stakeholder communication matrix — trigger and channel

| Stakeholder | Trigger | Message owner | Channel |
| --- | --- | --- | --- |
| Senior Management / Executive Sponsor | Initial High provisional assessment; material risk; continuity or exception decision | Incident Response Lead | Verified phone call followed by controlled written record |
| IT Operations and Security Staff | Containment decision; new evidence; credential or backup control; restoration gate | Incident Response Lead | Verified phone or approved out-of-band channel |
| Learners and examination cohort | Confirmed access disruption or approved examination arrangement | Academic/Business Service Owner with Communications Coordinator | Approved learner notice through verified institutional channel |
| Teaching staff and academic operations | Assessment availability or submission changes; learner support requirement | Business Continuity Coordinator / Academic Service Owner | Verified phone briefing and approved staff notice |
| Microsoft 365 / backup / relevant service provider | Need for provider records, identity support, backup validation or recovery assistance | IT Operations Lead with Security Analyst | Approved provider portal or verified support contact |
| Legal / Privacy Adviser | Potential personal-data implication or reporting-obligation question | Incident Response Lead | Verified phone and restricted fact pack |
| Staff and finance officer | Account or endpoint protection; operational instructions; fact-bounded safety notice | Communications Coordinator with Incident Response Lead | Verified telephone call and approved staff notice |
| Media / public-facing stakeholders | External query or public rumour requiring approved response | Communications Coordinator | Approved statement through authorised public channel |

Stakeholder communication matrix — approval and cadence

| Stakeholder | Alternative channel | Approver | Update frequency |
| --- | --- | --- | --- |
| Senior Management / Executive Sponsor | In-person briefing or independently verified phone tree | Senior Management / Executive Sponsor | At declaration and each material decision; next update by 10:30 WAT Day 0 |
| IT Operations and Security Staff | Direct voice call and controlled offline decision log | Incident Response Lead | At each decision point and when scope changes |
| Learners and examination cohort | Verified telephone or approved physical/alternative learning channel | Academic/Business Service Owner; management for material change | Initial status and before the 11:00 examination decision; update when status changes |
| Teaching staff and academic operations | Direct phone calls or controlled staff briefing | Academic/Business Service Owner | At initial decision, before examination start and at material change |
| Microsoft 365 / backup / relevant service provider | Verified telephone contact and controlled case record | Senior Management for engagement and information sharing | At request, provider response and material finding |
| Legal / Privacy Adviser | Direct verified call; no sensitive forensic detail over unverified email | Senior Management for formal advice or notification decision | At initial uncertainty and whenever facts change materially |
| Staff and finance officer | Direct phone call or controlled briefing | Incident Response Lead; Privacy Adviser if personal information is included | Initial instruction and when user action changes |
| Media / public-facing stakeholders | Verified telephone response or holding statement | Senior Management with Legal/Privacy advice | Only when approved; reassess when public information changes |
