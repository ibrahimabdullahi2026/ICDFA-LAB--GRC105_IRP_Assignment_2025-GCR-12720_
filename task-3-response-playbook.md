# Task 3 — Response Playbook and Evidence Preservation

> Extracted from the complete ICDFA GRC105 assignment. Content is organised by task; tables and source terminology are retained as Markdown where possible.

## 5	Task 3 — Response Playbook and Evidence Preservation

Status: Fictional operational plan — all actions are planned, not executed.
Incident position: High — provisional at 08:45 WAT on Day 0.
Scenario basis: E01–E08 and approved Task 1/Task 2 governance artifacts.

### 5.1	Operating rules

This playbook is a proposed response sequence for the suspected ransomware incident. It does not report live containment, acquisition, eradication, restoration, or monitoring results. Action owners are functional roles from the approved Task 2 CSIRT design. The Incident Response Lead (IRL) authorises normal containment; IT Operations executes within scope. Emergency containment is limited to the approved condition where normal approval is unavailable, and delay may materially worsen harm.

All times are WAT. E01–E08 are source observations. Hypotheses, proposed actions, and unverified consequences remain labelled as such. Planned evidence is recorded in data/evidence-register.csv.

### 5.2	Ordered response actions

The structured action register is data/response-actions.csv. It contains the first 60 minutes, the remainder of the first 24 hours, and later recovery/closure stages.

#### 5.2.1	First 60 minutes — 08:45 to 09:45 WAT

Establish the incident record at 08:45, preserve the approved High — provisional classification, and record E01–E08, uncertainty and the 11:00 examination dependency.

Use verified telephone calls because the FS01 contact list is inaccessible and corporate email trust is unverified (E08).

Preserve accessible EDR, Windows, proxy, Microsoft 365 and backup-console records before disruptive changes where delay is safe.

Contain FIN-PC07 under IRL authorisation, recording scope and expected operational impact (E01, E04, E06).

Protect the finance officer account and svc_backup through a documented identity-control decision, preserving sign-in and administrator-logon records first where practicable (E02–E03).

Assess FS01 and LMS01 dependency and contain FS01 if active propagation or continued encryption is suspected; document the availability tradeoff (E06–E07).

Preserve the E04 proxy record and request provider-side metadata; do not infer the uploaded content or personal-data disclosure.

Remove BAK01 from potentially exposed administrative paths or backup jobs only within approved scope; do not restore from an unvalidated backup (E03, E05).

Convene the IRL, Security Analyst, IT Operations, BCC and Academic/Business Service Owner to decide whether the 11:00 examination can safely proceed, requires an alternative arrangement, or must remain pending.

Record the next decision point and issue a fact-bounded internal update through an approved channel.

#### 5.2.2	Remainder of first 24 hours — 09:45 Day 0 to 08:45 Day 1

Correlate FIN-PC07, FS01, LMS01, BAK01, Microsoft 365, svc_backup, proxy and EDR records to test the entry-point and lateral-movement hypotheses.

Determine whether the finance attachment was executed; preserve mail headers, attachment metadata and endpoint execution artifacts. Do not assume execution from E01.

Investigate the unfamiliar Microsoft 365 sign-in, new device, MFA state, session/token activity and finance-user involvement (E02).

Investigate svc_backup logon source, schedule deviation, command or service activity and BAK01 access (E03); do not equate unusual activity with attacker control.

Assess whether the E04 transfer is connected to the incident and what content, if any, can be established from proxy, endpoint and cloud-provider records.

Search for persistence and broader compromise across endpoints, servers, identity, scheduled tasks, services, remote administration, privileged groups, email rules, tokens and network indicators.

Define the eradication plan: preserve required evidence, remove persistence, rebuild or reimage affected systems from known-good sources, close the entry point, rotate credentials, revoke sessions and apply compensating controls.

Validate BAK01 and any candidate backup in an isolated environment. Check malware indicators, permissions, timestamps, application consistency, expected files and recovery logs before considering restoration.

Restore only approved services in dependency order after technical, security, integrity and business gates pass: controlled identity/communications dependencies, FS01 or an approved alternative, then LMS01 and other priority services. FIN-PC07 returns only after endpoint rebuild and credential controls.

Monitor restored systems and privileged activity for recurrence, record exceptions and unresolved scope questions, and obtain Business Service Owner acceptance before return to normal service.

Close only when evidence, decisions, impact, communications, residual risk, follow-up owners and management/business approvals are recorded; otherwise keep the incident open or under recovery.

### 5.3	Difficult decisions

#### 5.3.1	Containment versus evidence preservation

E06 shows active mass file changes and locked files, while E01–E04 provide possible entry, identity, privileged-access and transfer leads. The default is to preserve volatile and high-value records before disruptive changes where safe. If active encryption, propagation or privileged exposure makes delay materially dangerous, the IRL may authorise immediate, least-disruptive containment; IT Operations records the scope, expected evidence loss, business impact and retrospective review. No responder should wait for perfect attribution before stopping ongoing harm.

#### 5.3.2	Examination availability versus unverified backup safety

The 11:00 examination creates material availability pressure (E07–E08), but E05 only reports successful jobs; it does not establish a clean or restorable backup. Northbridge must not reopen LMS01 from an unvalidated backup solely to meet the deadline. The BCC and Academic/Business Service Owner should prepare an alternative examination arrangement while the IRL and Security Analyst define restrictions and IT Operations validates an isolated recovery candidate. Any material continuity risk acceptance belongs to Senior Management. The decision and its effect on learners must be recorded even if the examination status remains pending.

### 5.4	Persistence, entry point and credential protection

The likely entry point remains a hypothesis. Investigators should test the payroll attachment path, mail records, endpoint execution evidence, identity activity, remote administration, exposed services, scheduled tasks, services, registry run keys, email rules, tokens and other persistence locations. E01 does not prove malicious execution.

Credential protection should include, as authorised and evidence-aware actions: disable or reset the finance account if compromise risk warrants it; rotate svc_backup and other exposed privileged credentials; revoke active sessions and tokens; review privileged-group membership; enforce MFA and conditional access where available; and use separate recovery credentials. The action log must state whether each control is planned, authorised, executed or awaiting evidence.

### 5.5	Recovery targets and acceptance criteria

The following are proposed planning targets requiring Senior Management and service-owner approval; they are not observed service levels:

Examination decision target: reach a documented safe-service or alternative-arrangement decision by 10:30 WAT on Day 0.

LMS01 service target: seek a four-hour recovery objective after security clearance, but do not trade security validation for the target.

Data-loss planning assumption: the last disconnected backup is Day minus 3 at 17:00 WAT, so a potential gap of up to approximately 72 hours must be explicitly assessed and accepted by the Business Service Owner and Senior Management if relevant. No data-loss acceptance has occurred.

Before return to service, require:

Technical restoration completion and execution record.

Security validation showing no unresolved known persistence or unauthorised access condition within the assessed scope.

Data-integrity verification for files, permissions, application state and required assessment materials.

Monitoring enabled for recurrence and privileged-account activity.

Business Service Owner confirmation that learner and staff impact is acceptable.

Senior Management approval where High/Critical material risk or an exception remains.

A documented rollback, hold or further-investigation decision if any gate fails.

### 5.6	Sources and boundaries

ICDFA, GRC105 Incident Response Planning Assignment, Task 3 and rubric.

ICDFA, Incident Response Planning, Week 20 slides 9–13 and 16–18.

Approved Task 1 evidence analysis and Task 2 governance/authority model.

NIST, SP 800-61 Rev. 3: https://csrc.nist.gov/pubs/sp/800/61/r3/final

NIST, SP 800-86 Guide to Integrating Forensic Techniques into Incident Response: https://csrc.nist.gov/pubs/sp/800/86/final

CISA and partners, #StopRansomware Guide: https://www.cisa.gov/stopransomware/ransomware-guide

No hash, acquisition, restoration test, malware result, clean-backup determination, or business acceptance is claimed.

Canonical response actions — stage and ownership

| Action ID | Time/stage WAT | Owner | Status |
| --- | --- | --- | --- |
| T3-01 | Day 0 08:45 | Incident Response Lead | Planned |
| T3-02 | Day 0 08:48 | Communications Coordinator / Incident Response Lead | Planned |
| T3-03 | Day 0 08:50 | Security Analyst / Evidence Custodian | Planned |
| T3-04 | Day 0 08:55 | IT Operations Lead | Planned |
| T3-05 | Day 0 09:00 | IT Operations Lead / Security Analyst | Planned |
| T3-06 | Day 0 09:05 | IT Operations Lead | Planned |
| T3-07 | Day 0 09:15 | Security Analyst / Evidence Custodian | Planned |
| T3-08 | Day 0 09:25 | IT Operations Lead | Planned |
| T3-09 | Day 0 09:35 | BCC / Academic Business Service Owner | Planned |
| T3-10 | Day 0 09:45 | Communications Coordinator | Planned |
| T3-11 | Day 0 10:00 | Security Analyst | Planned |
| T3-12 | Day 0 10:15 | Security Analyst / Evidence Custodian | Planned |
| T3-13 | Day 0 10:30 | IT Operations Lead / Security Analyst | Planned |
| T3-14 | Day 0 11:00 | Academic Business Service Owner / BCC | Planned |
| T3-15 | Day 0 12:00 | Security Analyst / Evidence Custodian | Planned |
| T3-16 | Day 0 14:00 | Incident Response Lead / IT Operations Lead | Planned |
| T3-17 | Day 0 18:00 | IT Operations Lead / Security Analyst | Planned |
| T3-18 | Day 1 08:45 | IT Operations Lead | Planned |
| T3-19 | Day 1 onward | Security Analyst / IT Operations Lead | Planned |
| T3-20 | Closure stage | Incident Response Lead | Planned |

Canonical response actions — planned action

| Action ID | Action | Status |
| --- | --- | --- |
| T3-01 | Open incident record; preserve High provisional classification; capture E01-E08 and uncertainty | Planned |
| T3-02 | Use verified telephone contacts and approved out-of-band identity checks | Planned |
| T3-03 | Preserve accessible EDR Windows proxy Microsoft 365 and backup-console records before changes where safe | Planned |
| T3-04 | Contain FIN-PC07 within approved scope because of mass file activity and possible transfer | Planned |
| T3-05 | Protect finance identity and svc_backup while preserving sign-in and admin-logon records | Planned |
| T3-06 | Assess and if necessary contain FS01 while documenting LMS01 dependency | Planned |
| T3-07 | Preserve E04 proxy and request cloud-storage metadata without inferring content | Planned |
| T3-08 | Protect BAK01 from further exposure and suspend unsafe restoration activity | Planned |
| T3-09 | Assess 11:00 examination options and safe-service prerequisites | Planned |
| T3-10 | Issue fact-bounded internal update through approved channel | Planned |
| T3-11 | Correlate endpoint server identity backup proxy and application records for scope and entry hypotheses | Planned |
| T3-12 | Investigate finance attachment execution and Microsoft 365 unfamiliar sign-in | Planned |
| T3-13 | Investigate svc_backup logons and BAK01 access; preserve server and backup records | Planned |
| T3-14 | Operate approved examination arrangement or hold service pending safety decision | Planned |
| T3-15 | Search for persistence and broader compromise across endpoints servers identity and network | Planned |
| T3-16 | Define eradication and credential-protection plan | Planned |
| T3-17 | Validate candidate backup or recovery source in isolated environment | Planned |
| T3-18 | Execute approved rebuild and phased restoration with security monitoring | Planned |
| T3-19 | Monitor recurrence and review privileged access and restored services | Planned |
| T3-20 | Close or retain incident under recovery with lessons and follow-up owners | Planned |

Canonical response actions — approval and evidence

| Action ID | Required approval | Evidence to retain |
| --- | --- | --- |
| T3-01 | Incident Response Lead | Incident ID situation record initial classification next review |
| T3-02 | Incident Response Lead | Notification log channel identity verification and recipients |
| T3-03 | Incident Response Lead | Export or preservation request references source timestamps and access restrictions |
| T3-04 | Incident Response Lead | Containment scope endpoint state E01 E04 E06 and business impact |
| T3-05 | Incident Response Lead; emergency authority only if condition applies | Identity audit references session/token status credential decision E02 E03 |
| T3-06 | Incident Response Lead | FS01 status shared-folder evidence E06 LMS01 dependency E07 |
| T3-07 | Incident Response Lead and privacy consultation | Proxy record request metadata source and uncertainty |
| T3-08 | Incident Response Lead | BAK01 access/job records E03 E05 and scope |
| T3-09 | Senior Management for material continuity risk | Joint situation report learner impact options E07 E08 |
| T3-10 | Senior Management for material external communication | Approved draft channel time recipients and uncertainty |
| T3-11 | Incident Response Lead | Analysis notes evidence references hypotheses and questions |
| T3-12 | Incident Response Lead; privacy/legal consultation as needed | Mail metadata endpoint artifacts audit logs MFA/device/session records E01 E02 |
| T3-13 | Incident Response Lead | Windows logs admin activity backup-console records E03 |
| T3-14 | Senior Management for material deviation | Service-status record learner communication and approval |
| T3-15 | Incident Response Lead | Search scope indicators results and limitations |
| T3-16 | Incident Response Lead; management for material exception | Plan approvals credential scope persistence findings and evidence impact |
| T3-17 | Incident Response Lead; Senior Management for material recovery risk | Backup provenance scan results integrity checks application test and limitations |
| T3-18 | Security validation and Business Service Owner gates; management where required | Build records monitoring alerts integrity and recovery tests |
| T3-19 | Incident Response Lead | Monitoring records alerts review decisions and exceptions |
| T3-20 | Required management and business acceptance | Closure record communications evidence limitations and improvement actions |

Canonical response actions — completion

| Action ID | Completion check | Status |
| --- | --- | --- |
| T3-01 | Record exists with source references and no invented findings | Planned |
| T3-02 | Required responders reached or failed attempts recorded | Planned |
| T3-03 | Preservation scope and limitations recorded | Planned |
| T3-04 | Endpoint isolated or reason for delay recorded | Planned |
| T3-05 | Approved control state and evidence-preservation tradeoff recorded | Planned |
| T3-06 | Scope and availability impact recorded | Planned |
| T3-07 | Request logged and content limitation retained | Planned |
| T3-08 | Backup protection decision recorded without restoration claim | Planned |
| T3-09 | Decision or pending status recorded by 10:30 target | Planned |
| T3-10 | Message approval and delivery status recorded | Planned |
| T3-11 | Scope assessment updated with confidence and gaps | Planned |
| T3-12 | Execution and account involvement remain evidence-based | Planned |
| T3-13 | Reason and scope assessed without attacker attribution | Planned |
| T3-14 | Actual status and rationale recorded; no assumed resumption | Planned |
| T3-15 | Search coverage and unresolved areas recorded | Planned |
| T3-16 | Plan approved with dependencies and rollback | Planned |
| T3-17 | Validation decision recorded; no clean claim without evidence | Planned |
| T3-18 | Each gate passed or hold/rollback recorded | Planned |
| T3-19 | Defined review period and unresolved risks recorded | Planned |
| T3-20 | Closure approval exists or open status is retained | Planned |

Canonical evidence register — source and method

| Item ID | Source | Relevant evidence or purpose | Proposed collection method |
| --- | --- | --- | --- |
| T3-EV-01 | FIN-PC07 E01 E04 E06 | Endpoint state file-change artifacts attachment and transfer indicators | Approved forensic preservation or EDR export followed by controlled acquisition if authorised |
| T3-EV-02 | FS01 E03 E06 E07 E08 | Windows logs locked files ransom note shared-folder state and contact-list availability | Preserve logs and relevant file metadata; forensic collection only after scope and impact decision |
| T3-EV-03 | Microsoft 365 E02 | Finance-account sign-in device MFA session token and audit context | Export or provider-preservation request through approved identity administration process |
| T3-EV-04 | Proxy/cloud record E04 | HTTPS destination volume timing and available metadata about 1.2 GB transfer | Preserve proxy record and submit controlled provider metadata request if authorised |
| T3-EV-05 | Windows and backup console E03 E05 | svc_backup activity BAK01 access job reports and backup provenance | Preserve administrator logs job history and configuration metadata; isolate validation copy for testing |
| T3-EV-06 | LMS01 E05 E07 | Portal availability submissions materials and application state | Preserve application and access logs and record service-status observations |

Canonical evidence register — collector and status

| Item ID | Collector role | Collection status |
| --- | --- | --- |
| T3-EV-01 | Digital Forensics and Evidence Custodian with Security Analyst | Planned / Not collected |
| T3-EV-02 | Digital Forensics and Evidence Custodian with IT Operations | Planned / Not collected |
| T3-EV-03 | Security Analyst with Microsoft 365 liaison | Planned / Not collected |
| T3-EV-04 | Security Analyst / Evidence Custodian | Planned / Not collected |
| T3-EV-05 | IT Operations with Evidence Custodian | Planned / Not collected |
| T3-EV-06 | IT Operations / Security Analyst | Planned / Not collected |

Canonical evidence register — timing and integrity

| Item ID | Planned date/time WAT | Integrity check (planned) | Restricted secure storage |
| --- | --- | --- | --- |
| T3-EV-01 | Day 0 08:50 onward | Record source timestamps tool/version and acquisition metadata; hash only if collection occurs | Access-controlled evidence repository separate from FIN-PC07; least privilege |
| T3-EV-02 | Day 0 08:50 onward | Record source path timestamps permissions and method; no hash claimed before collection | Restricted repository with original records read-only where possible |
| T3-EV-03 | Day 0 09:00 onward | Record provider export reference time range and format; verify completeness when received | Restricted cloud evidence area with privacy-limited access |
| T3-EV-04 | Day 0 09:15 onward | Record proxy source query range and response status; content not inferred | Restricted repository and privacy/legal review before sharing |
| T3-EV-05 | Day 0 09:25 onward | Compare source timestamps and job identifiers; test restoration results recorded only if performed | Separate backup-validation workspace with access restricted from routine administration |
| T3-EV-06 | Day 0 09:35 onward | Record collection window and application state; validate completeness after access | Restricted service-evidence repository with business-owner consultation |

Canonical evidence register — restrictions and custody

| Item ID | Custody transfer (planned) | Collection status |
| --- | --- | --- |
| T3-EV-01 | Transfer from collector to evidence custodian recorded in custody log with date/time WAT | Planned / Not collected |
| T3-EV-02 | Collector to evidence custodian then authorised analyst; each transfer documented | Planned / Not collected |
| T3-EV-03 | Provider or administrator to evidence custodian transfer recorded; no provider response assumed | Planned / Not collected |
| T3-EV-04 | Network or provider source to custodian; request and response references retained | Planned / Not collected |
| T3-EV-05 | IT Operations to custodian and Security Analyst; no restoration transfer assumed | Planned / Not collected |
| T3-EV-06 | IT Operations to custodian and authorised service owner | Planned / Not collected |
