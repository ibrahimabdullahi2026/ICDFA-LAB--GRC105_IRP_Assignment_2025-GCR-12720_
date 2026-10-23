# Task 2 — Incident Response Plan and Team Responsibilities

> Extracted from the complete ICDFA GRC105 assignment. Content is organised by task; tables and source terminology are retained as Markdown where possible.

## 4	Task 2 — Incident Response Plan and Team Responsibilities

Status: Stage 1 draft — awaiting independent review and organisational approval Scope: Incident response policy, governance, activation, escalation, isolation authority, recordkeeping, and business continuity integration Incident planning point: 08:45 WAT on Day 0 Approved Task 1 position: High — provisional

This consolidated draft is intended for later report incorporation. Supporting procedures and editable diagrams remain authoritative for detail. No response action, forensic acquisition, restoration test, or notification is claimed.

### 4.1	Policy purpose, objectives and scope

Northbridge's proposed incident response mission is to protect educational services and learner/staff information, limit security and operational damage, preserve evidence, make accountable decisions, coordinate continuity, and enable safe recovery. The policy covers employees, contractors, relevant service providers, managed endpoints and servers, Microsoft 365 identities, privileged accounts, shared storage, backups, learning services, and institutional information.

The policy is a draft awaiting approval. Its objectives are to establish consistent reporting and validation, clear authority, evidence-preserving decisions, proportionate response, continuity coordination, safe return to service, and post-incident improvement.

See incident-response-policy.md for document control, governance principles, exceptions, review, and source references.

### 4.2	Governance and decision authority

The proposed authority model separates governance ownership from technical execution:

| Decision | Proposed owner | Required control |
| --- | --- | --- |
| Declare and direct the incident | Incident Response Lead | Record evidence basis, severity, uncertainty, and next review. |
| Authorise normal containment | Incident Response Lead | Consult IT Operations, Security Analysis, and the Business Service Owner where material effects exist; specify scope and review point. |
| Execute approved technical action | IT Operations Lead and assigned authorised operator | Stay within approved scope and record execution status. |
| Analyse evidence and validate security | Security Analyst | Make evidence-linked recommendations; do not assume authority from analysis alone. |
| Approve material exceptions or Critical action | Senior management / Executive Sponsor | Record risk acceptance, resources, continuity, and communications decisions. |
| Accept business service return | Business Service Owner with management as required | Confirm business readiness after technical and security validation. |
| Coordinate business continuity | Business Continuity Coordinator within written delegation; Senior Management retains material activation authority | Assign a deputy/alternate and record scope; do not bypass security controls. |

Emergency containment applies only when the Incident Response Lead cannot be reached promptly and delay may materially worsen harm. The IT Operations Lead or formally delegated senior IT/security authority may approve the minimum necessary action, with notification and retrospective review. This Stage 1 draft records the historical boundary; the detailed CSIRT membership and RACI matrix are now maintained in the Stage 2 CSIRT/RACI draft and its supporting artifacts.

### 4.3	Incident declaration and activation

Reports may arrive through the service desk, Incident Response Lead, Security Analyst, IT Operations Lead, line manager, service provider, or approved phone channel. If the FS01 contact list or corporate email is unavailable or untrusted, staff phones are used for verified calls to known contacts. A controlled independent contact list and a pre-authorised secondary channel remain proposed readiness controls unless separately approved and verified.

The Incident Response Lead or delegated triage role records the report, WAT timestamp, source, immediate impact, evidence references, affected or potentially affected assets, continuing-threat concern, and protective options. The status model in the incident-response-governance-plan.md distinguishes security event, suspected incident, validated incident, declaration, activation, escalation, recovery, and closure. A credible security or policy event is declared as an incident; activation then brings the appropriate resources and governance into the response. Validation, declaration, and urgent protective action may overlap.

At 08:45 WAT on Day 0, the approved Task 1 position is High — provisional. If applied, this would justify urgent coordinated activation because E03, E04, E06, E07, and E08 indicate privileged-access, transfer, file-integrity, learner-service, and coordination concerns, while E05 leaves recovery trust uncertain. This is a proposed planning treatment, not a completed action.

The flow is shown in incident-declaration-activation.mmd.

### 4.4	Severity-based escalation

| Level | Governance treatment |
| --- | --- |
| Low | Standard documented workflow, bounded owner, validation, and monitoring or closure. |
| Medium | Prompt Incident Response Lead, IT, and service-owner coordination with proportionate management notification. |
| High | Rapid management notification, coordinated security/IT/continuity involvement, protection of identities and recovery assets, and reassessment before major service return. Northbridge is High — provisional. |
| Critical | Senior management or Executive Sponsor leads risk decisions, full available mobilisation is used, continuity is activated, and external support may be authorised. |

Escalation is driven by observed and potential operational impact, scope, data sensitivity, urgency, recoverability, and resources. It is not based solely on a ransom note. The decision flow is in severity-escalation-workflow.mmd.

### 4.5	Emergency isolation authority

Immediate containment may be considered where activity may continue, propagation or further damage is possible, privileged or recovery assets may remain exposed, or delay is likely to worsen harm. Before action, the Incident Response Lead records the security benefit, operational effect, examination dependency, evidence-preservation tradeoff, action boundary, authority, technical executor, and review time.

Normal containment authority is the Incident Response Lead, with IT Operations, Security Analysis, and the Business Service Owner consulted where relevant. If the Incident Response Lead cannot be reached promptly and delay may materially worsen harm, the IT Operations Lead or formally delegated senior IT/security role may authorise the minimum necessary emergency action, notify the Incident Response Lead or deputy and management as soon as practicable, and arrange retrospective review. Emergency authority does not permit unrelated isolation, unsafe restoration, or bypassing business acceptance.

FIN-PC07, FS01, LMS01, BAK01, Microsoft 365, and svc_backup are governance decision contexts from Task 1, not proof of compromise. Restoration from an unverified backup is not authorised by this procedure. See isolation-authority-and-emergency-decisions.md and its diagram.

### 4.6	Documentation and recordkeeping

Every material incident decision must record its ID, WAT time, reporter/source, description, evidence IDs, classification, assets, decision, owner, approval, action owner, execution status, supporting evidence, business impact, communications, next review time, and closure authorisation.

Records are access-restricted, version-controlled, confidential, and linked to evidence references. Corrections are additive or controlled revisions; original observations are not silently overwritten. If central systems are unavailable or untrusted, an approved alternate record is used and reconciled later. Retention follows the approved records schedule; no statutory period is invented.

See incident-documentation-procedure.md and the headers-only incident-decision-log-template.csv.

### 4.7	Business continuity integration

Incident response investigates, contains, preserves evidence, and validates security. The Business Continuity Coordinator coordinates authorised continuity arrangements; business continuity maintains acceptable educational services, coordinates learner and examination contingencies, and allocates operational resources. Senior Management retains authority for material continuity activation and institutional risk acceptance. Disaster recovery plans and validates controlled restoration.

The 11:00 examination requires joint security, technical, academic, continuity, and management decision-making. The relevant Academic or Business Service Owner approves the examination delivery arrangement within approved parameters; material deviations require management approval. E07 confirms learner-facing impact; E05 does not confirm a safe restore point. No postponement, restoration, or reopening decision is assumed. A continuity option must document its security assumptions, business owner, approval, learner communications, and review condition.

Return to service requires separate confirmation of technical availability, security validation, data integrity, and business acceptance. See business-continuity-integration.md and ir-business-continuity-coordination.mmd.

### 4.8	Operational limitations and residual risks

Northbridge has three IT personnel and one security analyst; role allocation, external support, and sequencing require management attention.

The incident contact list is inaccessible and corporate email trust is unverified. Staff phones are available for verified calls; a controlled independent contact list and secondary channel remain proposed readiness controls requiring approval.

The FS01 dependency may affect LMS01, but it does not prove the cause of E07.

svc_backup activity and the E04 transfer are observations requiring validation, not confirmed attacker actions or data theft.

E05 reports successful jobs but does not establish backup integrity, recoverability, or cleanliness.

Server EDR coverage is incomplete, so absence of an alert cannot establish absence of activity.

No legal deadline, contractual right, external support engagement, or response SLA is assumed.

### 4.9	Sources and assumptions

[A1] ICDFA, GRC105 Incident Response Planning Assignment, pp. 1–6, Task 2 and marking criteria.

[S1] ICDFA, Incident Response Planning, Week 20 slides 6–10 and 14–18. The four course stages are used for organisation only.

[N1] NIST, SP 800-61 Revision 3, 2025: https://csrc.nist.gov/pubs/sp/800/61/r3/final

[N2] NIST, SP 800-86, 2006: https://csrc.nist.gov/pubs/sp/800/86/final

[C1] CISA and partners, #StopRansomware Guide: https://www.cisa.gov/stopransomware/ransomware-guide

Scenario facts and E01–E08 observations are drawn from the approved Task 1 materials. Proposed roles, authorities, channels, identifiers, and review controls are assumptions requiring organisational approval.

### 4.10	Outstanding Task 2 requirements

The following are intentionally deferred and must not be read as complete Task 2 requirements:

Define the complete CSIRT with at least six roles and detailed responsibilities.

Produce the final RACI for at least eight activities, with exactly one accountable role and at least one responsible role per activity.

Produce at least four preparation/readiness improvements with owner, resources, target completion, and measurable evidence.

Complete independent review, organisational approval, and the Task 2 review gate.

These items are tracked in governance-requirements-matrix.csv. Task 3 technical containment, evidence custody execution, eradication, and recovery criteria are outside this stage.

Status: Task 2 Stage 2 draft — ready for independent review after validation
Scope: CSIRT structure, staffing capacity, RACI accountability, authority crosswalk, and duty-conflict controls
Approved governance baseline: Stage 1 authority model; High — provisional at 08:45 WAT on Day 0

No response action, forensic acquisition, external engagement, appointment, restoration, or investigation result is claimed.

### 4.11	Purpose and governance context

This Stage 2 package converts the accepted Stage 1 policy and 14-activity authority matrix into an operationally credible CSIRT and RACI. It preserves the Incident Response Lead's command and normal-containment authority, constrained emergency authority, Senior Management risk acceptance, BCC coordination role, and separate recovery gates.

The structure is functional rather than enterprise-scale. Northbridge has three IT personnel and one security analyst. Legal/privacy, communications, continuity, service-owner, and external specialist functions are proposed assignments or contingent support arrangements, not confirmed dedicated staff.

### 4.12	CSIRT organisational structure

The core CSIRT functions are:

Incident Response Lead / Incident Commander (IRL-01).

Security Analyst / Investigation Coordinator (SEC-01).

Digital Forensics and Evidence Custodian (FOR-01).

IT Operations and Recovery Lead (OPS-01).

Legal / Privacy Adviser (LP-01).

Stakeholder Communications Coordinator (COM-01).

Supporting governance and continuity interfaces are Senior Management / Executive Sponsor (MGT-01), Business Continuity Coordinator (BCC-01), Academic/Business Service Owner (BSO-01), and contingent Microsoft 365 and backup-provider interfaces.

See csirt-organisation-and-command.md and csirt-organisational-structure.mmd.

### 4.13	Roles and responsibilities

The Incident Response Lead directs, declares, activates, escalates, authorises normal containment, and coordinates closure. The Security Analyst analyses evidence and performs security validation. The Digital Forensics function preserves evidence and provenance. IT Operations executes approved technical work. Legal/Privacy advises on data and reporting obligations. Communications prepares fact-bounded messages but does not approve its own external release.

Senior Management retains material risk acceptance, formal appointment, material exception, Critical, and continuity activation authority. The BCC coordinates authorised continuity arrangements. The Academic/Business Service Owner approves examination arrangements within parameters and accepts business service return after the technical and security gates are satisfied.

### 4.14	Internal capacity and staffing allocation

The proposed initial allocation is:

| Resource | Primary assignment | Main restriction |
| --- | --- | --- |
| IT Staff 1 | IRL-01 | Does not perform simultaneous hands-on containment during command-critical decisions. |
| IT Staff 2 | OPS-01 | Does not expand scope or approve its own business return. |
| IT Staff 3 | Technical operator and proposed FOR-01 dual-hat | Evidence preservation and disruptive work must be sequenced or separately supervised. |
| Security Analyst 1 | SEC-01 | Analysis does not independently authorise disruptive action. |

The 11:00 examination, E08 communication constraint, E03 privileged activity, E04 transfer uncertainty, E05 backup uncertainty, and E06/E07 availability and integrity effects require deliberate sequencing. If capacity is exhausted, active-threat containment, evidence preservation, privileged-access protection, examination decision-making, and recovery safety take precedence over low-value review or improvement work.

See staffing-capacity-and-support-model.md.

### 4.15	External support and escalation

The Incident Response Lead recommends external support when internal capacity, specialist skill, independence, or recovery confidence is insufficient. Senior Management authorises engagement, information sharing, extraordinary resources, and confidentiality arrangements. Potential support includes specialist forensics, malware analysis, Microsoft 365 identity assistance, backup recovery engineering, legal/privacy advice, and communications support.

No supplier, retainer, response time, or completed engagement is assumed. Evidence of engagement would be an approved work order, provider ticket, engagement letter, or equivalent controlled record.

### 4.16	RACI methodology

The RACI separates execution from decision ownership:

R performs or coordinates the activity.

A owns the outcome or decision; exactly one A is assigned per row.

C provides required input.

I receives status or outcome information.

Normal containment is R06 with IRL-01 accountable. Emergency containment is separate in R07 with OPS-01 accountable only under the constrained emergency authority. Technical restoration, security validation, data integrity, business acceptance, and management risk acceptance are separate rows.

The complete matrix is in raci.csv. Explanatory rules are in raci-methodology-and-accountability.md.

### 4.17	RACI matrix summary

The matrix contains 22 activities, including all eight instructor-mandated activities:

Detection and analysis.

Containment and emergency containment.

Evidence handling.

Stakeholder communication.

Assessment of reporting obligations.

Restoration approval and its separate security, integrity, and business gates.

Closure and review.

Additional rows cover declaration, activation, escalation, backup integrity, continuity activation, examination continuity, exceptions, delegation, and appointment of leadership or continuity deputies.

### 4.18	Authority consistency

The authority-raci-crosswalk.csv maps all 14 Stage 1 authority activities to the RACI. The technical restoration authority is intentionally mapped to separate R14, R15, and R16 gates, with R17 for business acceptance and R20 for material institutional risk acceptance. No Stage 1 authority assignment is changed.

The crosswalk identifies the emergency containment substitution, delegation boundary, BCC limitation, and Senior Management appointment authority. The authority-consistency matrix remains the controlling source for governance authority.

### 4.19	Separation-of-duties risks

The duty-conflict register records conflicts involving command versus technical execution, evidence versus destructive containment, backup administration versus integrity validation, identity administration versus investigation, communications drafting versus approval, and recovery implementation versus business acceptance.

Mitigations rely on sequencing, explicit approval scope, independent consultation where available, deputies, controlled records, and external support requests. These are planning controls, not evidence that any conflict has occurred.

### 4.20	Visual exhibits

csirt-organisational-structure.mmd — command, consultation, and contingent support relationships.

csirt-staffing-and-escalation.mmd — capacity, sequencing, and external escalation.

raci-accountability-workflow.mmd — RACI decision path and emergency distinction.

recovery-approval-gates.mmd — technical, security, integrity, business, and management gates.

Rendered SVG and PNG exports are in visuals/ after validation.

### 4.21	Sources and assumptions

ICDFA GRC105 Incident Response Planning Assignment, Task 2 and 20-mark rubric.

Week 20 teaching slides 8–11 and 14–15.

Approved Task 1 integrated assessment and High — provisional severity classification.

Approved Stage 1 policy, governance plan, isolation procedure, documentation procedure, business-continuity plan, and 14-activity authority matrix.

NIST SP 800-61 Revision 3 as CSF 2.0-aligned guidance; course four-stage teaching model remains a course-facing organisation aid.

All staffing, deputy, external support, and role assignments are proposed unless identified as scenario-established. No personal names, investigation outcomes, or completed engagements are invented.

### 4.22	Preparation improvements

The readiness register is in preparation-improvements.md. It covers four distinct improvements:

Backup isolation, tested recoverability and integrity evidence.

Independently accessible incident contacts and secure communication fallback.

Server and endpoint monitoring coverage with alert ownership.

Role-based training and tabletop exercise readiness.

Each improvement identifies the weakness, proposed control, accountable owner, required resources, priority and measurable readiness check. These are proposed improvements; implementation evidence is not claimed.

### 4.23	Remaining task boundaries

Task 3's technical response playbook, evidence register, eradication procedures and recovery acceptance workflow remain outside this Stage 2 governance package. No live action, forensic acquisition, restoration test or external engagement is claimed.

Figure 1 — Initial severity decision logic.

Figure 2 — Proposed CSIRT organisational structure.

RACI accountability matrix — activity and accountability

| Activity ID | Activity | Responsible role IDs | Accountable role ID |
| --- | --- | --- | --- |
| R01 | Detection | SEC-01 | SEC-01 |
| R02 | Analysis | SEC-01 | SEC-01 |
| R03 | Incident declaration | IRL-01 | IRL-01 |
| R04 | Response activation | IRL-01 | IRL-01 |
| R05 | Severity escalation | IRL-01 | IRL-01 |
| R06 | Normal containment | OPS-01 | IRL-01 |
| R07 | Emergency containment authorisation | OPS-01 | OPS-01 |
| R08 | Evidence handling | FOR-01 | FOR-01 |
| R09 | Stakeholder communication preparation and coordination | COM-01;BCC-01;BSO-01 | COM-01 |
| R10 | Assessment of reporting obligations | LP-01 | LP-01 |
| R11 | Backup integrity validation | OPS-01;FOR-01 | SEC-01 |
| R12 | Business continuity activation | BCC-01 | MGT-01 |
| R13 | Examination continuity approval | BCC-01;BSO-01 | BSO-01 |
| R14 | Technical restoration authorisation | OPS-01 | OPS-01 |
| R15 | Security validation for recovery | SEC-01 | SEC-01 |
| R16 | Data integrity verification | OPS-01;FOR-01 | OPS-01 |
| R17 | Business return-to-service acceptance | BSO-01 | BSO-01 |
| R18 | Closure and post-incident review | IRL-01 | IRL-01 |
| R19 | Routine operational deviation | IRL-01 | IRL-01 |
| R20 | Material or policy-level exception | IRL-01 | MGT-01 |
| R21 | Incident response decision delegation | IRL-01 | IRL-01 |
| R22 | Appointment of incident leadership or continuity deputy | MGT-01 | MGT-01 |

RACI accountability matrix — consultation and notification

| Activity ID | Consulted role IDs | Informed role IDs |
| --- | --- | --- |
| R01 | OPS-01 | IRL-01;MGT-01 |
| R02 | FOR-01;OPS-01;M365-01 | IRL-01;BSO-01 |
| R03 | SEC-01;OPS-01 | MGT-01 |
| R04 | SEC-01;OPS-01;BCC-01;BSO-01 | MGT-01;LP-01;COM-01 |
| R05 | SEC-01;OPS-01;BSO-01;BCC-01 | MGT-01 |
| R06 | SEC-01;FOR-01;BSO-01;BCC-01 | MGT-01;COM-01 |
| R07 | IRL-01;SEC-01;BSO-01 | MGT-01;BCC-01 |
| R08 | SEC-01;OPS-01;IRL-01 | LP-01;MGT-01 |
| R09 | IRL-01;LP-01 | MGT-01;SEC-01;OPS-01 |
| R10 | SEC-01;IRL-01;MGT-01 | BSO-01;COM-01 |
| R11 | BKP-01;IRL-01;BSO-01 | MGT-01;BCC-01 |
| R12 | IRL-01;BSO-01;OPS-01;COM-01 | SEC-01;LP-01 |
| R13 | IRL-01;SEC-01;OPS-01;MGT-01 | COM-01 |
| R14 | SEC-01;BSO-01;IRL-01 | MGT-01;BCC-01 |
| R15 | FOR-01;OPS-01;IRL-01 | BSO-01;MGT-01 |
| R16 | SEC-01;BSO-01 | IRL-01;MGT-01 |
| R17 | IRL-01;SEC-01;OPS-01;BCC-01;MGT-01 | COM-01 |
| R18 | SEC-01;FOR-01;OPS-01;LP-01;COM-01;BCC-01;BSO-01 | MGT-01 |
| R19 | SEC-01;OPS-01;BSO-01;LP-01 | MGT-01 |
| R20 | SEC-01;OPS-01;BSO-01;LP-01;BCC-01 | COM-01 |
| R21 | OPS-01;SEC-01;BSO-01;MGT-01 | MGT-01 |
| R22 | IRL-01;OPS-01;BCC-01;BSO-01 | SEC-01;COM-01 |

RACI accountability matrix — authority record

| Activity ID | Normal authority basis | Emergency or exception note | Required record |
| --- | --- | --- | --- |
| R01 | Security Analyst coordinates detection and initial triage | Escalate immediately if active harm or material impact is suspected | Source time initial facts evidence references and triage status |
| R02 | Security Analyst owns analysis and uncertainty reporting | Request external analysis if internal capability or independence is insufficient | Hypotheses evidence references scope assessment and unresolved questions |
| R03 | Incident Response Lead declares under Stage 1 authority | Delegated senior IT/security decision-maker may declare if IRL is unavailable and delegation is recorded | Incident ID evidence basis initial severity owner delegation and next review |
| R04 | Incident Response Lead activates required response functions | Deputy or management-appointed incident director acts only within recorded authority | Activation scope resources communication route and review point |
| R05 | Incident Response Lead escalates with management notification | Senior Management may direct a higher tier; reassess on material evidence or impact change | Evidence impact urgency uncertainty authority notification and reassessment basis |
| R06 | Incident Response Lead authorises normal containment and IT Operations executes | Emergency path is separate in R07; technical operator cannot expand scope | Approved target scope expected effect evidence plan business impact and review time |
| R07 | IT Operations Lead is accountable only for the constrained emergency authority when IRL cannot be reached promptly and delay may materially worsen harm | Formal delegated senior IT/security authority may substitute and must be recorded; retrospective management review required | Why delay was unsafe minimum action authority delegation notification evidence effect business impact and review deadline |
| R08 | Digital Forensics and Evidence Custodian coordinates evidence preservation within approved scope | If disruptive containment is urgent record unavoidable evidence loss and seek specialist support | Provenance collection status custody references secure storage and limitations |
| R09 | Communications Coordinator owns preparation and coordination; Senior Management retains release approval | Use verified phone fallback when email trust is unverified; do not release unapproved external messages | Draft message audience channel approval reference facts and notification time WAT |
| R10 | Privacy or Legal Adviser owns the advisory assessment | No jurisdiction or deadline is assumed; formal notification approval remains with authorised management | Advice basis jurisdiction or contract question factual uncertainty approval recommendation and deadline source if verified |
| R11 | Security Analyst owns the security validation while IT and forensics perform checks | No restoration from an unvalidated backup; obtain specialist support where required | Validation method evidence references integrity and recoverability limitations and decision recommendation |
| R12 | Senior Management retains material activation and institutional risk acceptance; BCC coordinates authorised arrangements | Predefined low-risk preparations may proceed within written delegation; material deviation requires management approval | Trigger authority delegation continuity option security restrictions approval and review condition |
| R13 | Business Service Owner approves examination delivery within approved parameters | Senior Management approves material deviation or institutional risk acceptance; BCC cannot override security restrictions | Learner impact technical prerequisites security assumptions approval communications and review condition |
| R14 | IT Operations Lead authorises technical restoration work subject to security and business gates | High/Critical management approval is represented through R20 where material risk or exception exists; no unsafe emergency restoration | Restoration scope prerequisites approvals execution status and technical test result |
| R15 | Security Analyst owns security validation and does not certify cleanliness without evidence | Further investigation or external specialist support is required if validation is incomplete | Security validation evidence persistence or access findings restrictions and decision |
| R16 | IT Operations owns technical data-integrity verification with evidence and forensic support | Unvalidated backup or inconsistent application state blocks safe return | Files application state permissions recovery data checks evidence and limitations |
| R17 | Business Service Owner accepts service return after technical security and integrity gates | Senior Management accepts material continuity risk or deviation; technical execution alone is insufficient | Business readiness learner impact conditions approval and review point |
| R18 | Incident Response Lead owns closure recommendation and review coordination | Management or appointed closure authority must approve where required; unresolved risks remain open | Closure authority records communications follow-up owners unresolved risks and review outcome |
| R19 | Incident Response Lead approves limited deviation within delegated authority | Material impact or weakened controls escalate to R20; document rationale and review condition | Deviation scope rationale compensating control authority duration and review |
| R20 | Senior Management or Executive Sponsor owns institutional risk acceptance | Emergency protective action may proceed only to reduce immediate harm and must receive retrospective management review | Exception scope consultation risk acceptance compensating controls approval and review deadline |
| R21 | Incident Response Lead delegates defined response decisions within policy authority | No onward delegation unless expressly permitted; emergency authority remains constrained | Recipient scope start time WAT expiry or review restrictions approval reference and revocation |
| R22 | Senior Management or Executive Sponsor appoints replacement incident leadership or BCC deputy | Incident Response Lead or BCC cannot self-appoint the management-designated deputy | Appointment authority role scope effective time WAT expiry or review and communication to affected teams |

CSIRT role register — purpose and responsibility

| Role ID | Functional role | CSIRT classification | Key responsibility |
| --- | --- | --- | --- |
| IRL-01 | Incident Response Lead / Incident Commander | Core CSIRT | Direct incident response; declare, activate, escalate, authorise normal containment, coordinate decisions, and close or recommend closure |
| SEC-01 | Security Analyst / Investigation Coordinator | Core CSIRT | Triage, correlate, analyse, assess severity and scope, and provide security validation |
| FOR-01 | Digital Forensics and Evidence Custodian | Core CSIRT | Preserve evidence references, coordinate collection planning, and maintain provenance and custody records |
| OPS-01 | IT Operations and Recovery Lead | Core CSIRT | Assess dependencies and execute approved endpoint, server, identity, backup, and restoration work |
| LP-01 | Legal / Privacy Adviser | Core CSIRT advisory function | Assess information classification, privacy, contractual, legal, safeguarding, and reporting-obligation questions |
| COM-01 | Stakeholder Communications Coordinator | Core CSIRT communications function | Prepare and coordinate fact-bounded internal, learner, staff, and external communications |
| BCC-01 | Business Continuity Coordinator | Supporting governance and continuity stakeholder | Coordinate authorised continuity arrangements and predefined low-risk preparations within delegation |
| BSO-01 | Academic / Business Service Owner | Supporting business stakeholder | Define service impact and approve examination or business service arrangements within approved parameters |
| MGT-01 | Senior Management / Executive Sponsor | Supporting governance authority | Approve material risk, Critical decisions, material exceptions, extraordinary resources, continuity activation, and formal appointments |
| M365-01 | Microsoft 365 / Identity Provider Liaison | External or service-provider interface | Obtain provider-side identity, mailbox, MFA, token, device, and audit-log assistance when authorised |
| BKP-01 | Backup / Recovery Specialist or Provider Liaison | External or service-provider interface | Support isolated backup validation and recovery engineering when internal capacity is insufficient |

CSIRT role register — authority and status

| Role ID | Normal decision authority | Status |
| --- | --- | --- |
| IRL-01 | Incident Response Lead under Stage 1 authority | Proposed internal assignment |
| SEC-01 | Analysis and security recommendations; no independent disruptive authority | Scenario-established resource; role assignment proposed |
| FOR-01 | Evidence-handling coordination within approved scope; no containment or restoration authority | Proposed functional assignment |
| OPS-01 | Technical execution within approved scope; constrained emergency containment authority under Stage 1 conditions | Proposed internal assignment |
| LP-01 | Advisory authority only; formal risk acceptance and external release remain with authorised management | Proposed support function |
| COM-01 | Communication preparation and coordination; Senior Management approves external release | Proposed support function |
| BCC-01 | Coordination only; Senior Management retains material activation and risk acceptance | Proposed functional assignment |
| BSO-01 | Business acceptance and examination arrangement approval within delegated parameters | Proposed functional assignment |
| MGT-01 | Institutional risk acceptance, material exception, continuity activation, and appointment authority | Proposed governance role |
| M365-01 | No independent Northbridge decision authority | Contingent support interface |
| BKP-01 | No independent Northbridge decision authority | Contingent support interface |

CSIRT role register — staffing and competence

| Role ID | Primary staffing assignment | Alternate staffing assignment | Required competence |
| --- | --- | --- | --- |
| IRL-01 | IT Staff 1 — proposed assignment | Management-appointed deputy from IT Staff 2 or IT Staff 3; external incident director if authorised | Incident coordination, risk-based decisions, evidence-aware leadership, service impact assessment |
| SEC-01 | Security Analyst 1 — scenario-established | Authorised external specialist or trained IT support subject to approval | Security monitoring, identity and cloud investigation, log analysis, uncertainty reporting |
| FOR-01 | IT Staff 3 — proposed dual-hat assignment or authorised external specialist | External forensic provider or trained IT Staff 2 subject to approval | Evidence preservation, secure storage, time-zone-aware records, custody principles |
| OPS-01 | IT Staff 2 — proposed assignment | IT Staff 3; authorised provider support | Windows/server, endpoint, identity, backup, network, and service dependencies |
| LP-01 | Proposed internal adviser if available or authorised external counsel | External legal/privacy adviser | Privacy, legal, records, contractual, and regulatory analysis |
| COM-01 | Management-assigned non-IT staff member — proposed | BCC, Academic/Business Service Owner, or authorised external communications support | Clear writing, privacy-aware handling, audience coordination, alternate-channel use |
| BCC-01 | Management-assigned functional role — proposed | Management-appointed deputy or alternate BCC | Continuity coordination, service prioritisation, resource coordination, examination planning |
| BSO-01 | Academic Operations or affected Business Service Owner — proposed role assignment | Management-designated alternate service owner | Service dependency, learner impact, business acceptance, and continuity decisions |
| MGT-01 | Senior Management / Executive Sponsor — scenario governance role, not a named person | Delegated senior management authority | Risk acceptance, resource authorisation, governance oversight, and decision review |
| M365-01 | Authorised IT Operations or provider support — contingent | Microsoft 365 provider support or approved specialist | Identity administration, provider processes, audit-log interpretation |
| BKP-01 | Authorised external specialist or provider — contingent | IT Operations and approved recovery support | Backup architecture, isolated validation, application consistency, recovery engineering |

CSIRT role register — dependencies and provenance

| Role ID | Support dependency | Potential conflict | Source or governance reference |
| --- | --- | --- | --- |
| IRL-01 | Senior Management, BCC, service owners, and external support when capacity is insufficient | Command competes with hands-on technical work and recordkeeping | Stage 1 policy Section 5; governance plan Section 6 |
| SEC-01 | External forensics, malware analysis, cloud provider, and IT Operations | Analysis may conflict with urgent containment or recovery validation | Task 1 integrated assessment; Stage 1 policy Sections 5–6 |
| FOR-01 | Specialist forensics and secure storage support may be required | Evidence preservation may conflict with disruptive containment | Task 2 requirement; Stage 1 documentation procedure |
| OPS-01 | Backup, cloud identity, and recovery specialists may be required | Technical execution may conflict with backup validation or business acceptance | Stage 1 policy Sections 5 and 7; isolation procedure |
| LP-01 | External advice may require management authorisation and confidentiality arrangements | Advice and communications approval must remain distinct | Task 2 requirement; Stage 1 policy Section 7 |
| COM-01 | Management approval, Privacy/Legal advice, and approved channels | Drafting may conflict with message approval or unverified email use | Task 2 requirement; Stage 1 policy Section 5 |
| BCC-01 | Academic/Business Service Owner, Incident Response Lead, and management | Continuity pressure may conflict with security restrictions and recovery gates | Stage 1 policy Section 5; business-continuity plan |
| BSO-01 | Incident Response Lead, IT Operations, Security Analyst, and management | Business acceptance may conflict with security validation or technical recovery status | Stage 1 policy Sections 5 and 7 |
| MGT-01 | Incident Response Lead, advisers, service owners, and external providers | Management decisions may be delayed by incomplete evidence or competing continuity pressure | Stage 1 policy Sections 1 and 5 |
| M365-01 | Provider availability and contractual access are unverified | Identity administration may conflict with compromise investigation and evidence preservation | Stage 1 governance plan Section 8 |
| BKP-01 | Management approval, availability, confidentiality, and validated scope | Backup administration may conflict with independent backup-integrity validation | Stage 1 governance plan Section 8; business-continuity plan |

The four proposed preparation improvements are documented in the Task 2 readiness register and integrated draft.
