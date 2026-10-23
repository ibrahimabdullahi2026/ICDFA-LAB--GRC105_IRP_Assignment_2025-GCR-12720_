# Incident Response Planning and Ransomware Response Simulation
**Northbridge Skills Institute — Evidence-Based Assessment Report**

---

## Document & Student Metadata

| Property | Value |
| :--- | :--- |
| **Student Name** | Ibrahim Abdullahi |
| **Registration Number** | 2025/GCR/12720 |
| **Official Email** | gcr2512720@students.icdfa.edu.ng |
| **Program** | GRC Engineering (CGRCE) |
| **School** | School of Cyber Risk, Governance and Compliance |
| **Cohort** | Batch B2025 |
| **Academic Session** | 2026 |
| **Level / Year** | Level 1 / Year 1 |
| **Course** | GRC105 — Incident Management and Business Continuity |
| **Assignment** | Incident Response Planning and Ransomware Response Simulation |

---

## Executive Summary & Baseline Parameters

* **Organization:** Northbridge Skills Institute (fictional scenario)
* **Assessment Point:** 08:45 WAT on Day 0
* **Current Initial Severity:** High — provisional

---

## Table of Contents
1. [Task 1 — Incident Classification and Initial Assessment](#1-task-1--incident-classification-and-initial-assessment)
   * [1.1 Initial Classification & Impact Assessment](#11-initial-classification--impact-assessment)
   * [1.2 Evidence Analysis Register](#12-evidence-analysis-register)
   * [1.3 Assets and Scope](#13-assets-and-scope)
   * [1.4 CIA Triad Assessment](#14-cia-triad-assessment)
   * [1.5 Response Priorities](#15-response-priorities)
   * [1.6 Investigation Priorities & Responsibilities](#16-investigation-priorities--responsibilities)
2. [Task 2 — Incident Response Governance and CSIRT Responsibilities](#2-task-2--incident-response-governance-and-csirt-responsibilities)
   * [2.1 Policy Purpose, Governance & Decision Authority](#21-policy-purpose-governance--decision-authority)
   * [2.2 Incident Declaration & Escalation Model](#22-incident-declaration--escalation-model)
   * [2.3 CSIRT Organizational Structure & Staffing Allocation](#23-csirt-organizational-structure--staffing-allocation)
   * [2.4 RACI Accountability Matrix](#24-raci-accountability-matrix)
   * [2.5 CSIRT Role Register](#25-csirt-role-register)
3. [Task 3 — Response Playbook and Evidence Preservation](#3-task-3--response-playbook-and-evidence-preservation)
   * [3.1 Operating Rules & Chronological Action Register](#31-operating-rules--chronological-action-register)
   * [3.2 Difficult Decision Handling](#32-difficult-decision-handling)
   * [3.3 Canonical Evidence Register](#33-canonical-evidence-register)
4. [Task 4 — Communication and Escalation Framework](#4-task-4--communication-and-escalation-framework)
   * [4.1 Stakeholder Communication Matrix](#41-stakeholder-communication-matrix)
   * [4.2 Key Briefings & Notices](#42-key-briefings--notices)
   * [4.3 Operational vs. Breach Notifications](#43-operational-vs-breach-notifications)
5. [Task 5 — Tabletop Exercise and Improvement Plan](#5-task-5--tabletop-exercise-and-improvement-plan)
   * [5.1 Simulation Parameters & Injects](#51-simulation-parameters--injects)
   * [5.2 Canonical Decision Log](#52-canonical-decision-log)
   * [5.3 Corrective Action Register](#53-corrective-action-register)
6. [Task 6 — Case Study Analysis and Critical Reflection](#6-task-6--case-study-analysis-and-critical-reflection)
7. [References & Acknowledgements](#7-references--acknowledgements)

---

## 1. Task 1 — Incident Classification and Initial Assessment

### 1.1 Initial Classification & Impact Assessment
The evidence is consistent with a suspected ransomware or destructive file-impact event involving possible identity misuse, unauthorized transfer, and backup compromise. Classification is based on the combination of observed file and learner-service impact, unusual privileged activity, uncertain data transfer, time-critical examination impact, and uncertain recovery capability.

* **Initial Severity:** **High — Provisional** at 08:45 WAT (Day 0).
* **Justification for High:**
  * **E06:** Mass file changes on `FIN-PC07` and `.locked` files + ransom note in `FS01` shared folders.
  * **E07:** Learner portal materials/submissions unavailable; directly impacts learner availability.
  * **E08:** Incident contact list on `FS01` is inaccessible; corporate email trust is unverified.
  * **E03:** Account `svc_backup` made unusual remote administrator logons to `FS01` and `BAK01`.
  * **E04:** `FIN-PC07` uploaded 1.2 GB over HTTPS to an unfamiliar cloud storage destination.
  * **Time Pressure:** Imminent 11:00 WAT examination for 100 learners, limited staffing, sensitive data holdings.
* **Why Not Critical (at 08:45):** Evidence does not yet confirm institution-wide total loss, broad data disclosure, full path recovery destruction, or permanent persistent attacker control. The portal login loads, phones are operational, and scope is unverified.

#### Observed, Suspected, and Unconfirmed Impact Summary

| Category | Current Assessment |
| :--- | :--- |
| **Observed Impact** | E06 file changes on FIN-PC07/FS01; E07 learner portal service loss; E08 contact list inaccessible; E03 unusual privileged logons; E04 cloud upload. |
| **Suspected Impact** | Ransomware/destructive activity; privileged lateral movement; LMS01 dependency disruption; identity misuse; backup compromise. |
| **Unconfirmed Consequences** | Malicious execution from E01; account theft from E02; personal data transfer in E04; BAK01 tampering; malware family; total network spread. |
| **Additional Evidence Needed** | Endpoint process/file telemetry; M365/MFA logs; Windows security logs; proxy metadata; application logs; isolated backup verification. |

---

### 1.2 Evidence Analysis Register

#### Evidence Core
| Evidence ID | Timestamp (WAT) | Original Source | Confirmed Observation |
| :--- | :--- | :--- | :--- |
| **E01** | Day -1 16:40 | Assignment brief (Mail record) | Finance officer opened an unexpected payroll attachment on `FIN-PC07`. Code execution unverified. |
| **E02** | Day 0 01:15 | M365 Audit log | Finance officer account signed in from unfamiliar IP/new device. MFA status & user involvement unknown. |
| **E03** | Day 0 01:35 | Windows Logs | `svc_backup` made remote admin logons to `FS01` and `BAK01` outside schedule. |
| **E04** | Day 0 01:50 | Proxy Record | `FIN-PC07` uploaded 1.2 GB over HTTPS to unfamiliar cloud destination. Transferred content unknown. |
| **E05** | Day 0 02:00 | Backup Console | Console reported successful backup jobs for `FS01` and `LMS01`. Recoverability/integrity unverified. |
| **E06** | Day 0 08:30 | EDR & Helpdesk | Mass file changes on `FIN-PC07`. `FS01` shares contain `.locked` files and ransom note. |
| **E07** | Day 0 08:40 | Helpdesk Report | LMS01 login loads, but learners cannot open materials or submit assessments. |
| **E08** | Day 0 08:45 | Operations Report | Contact list on `FS01` inaccessible. Phones available; email trust unverified. |

#### Analytical Uncertainty & Hypotheses
| Evidence ID | Reasonable Working Hypothesis | Alternative Explanation | Unresolved Questions |
| :--- | :--- | :--- | :--- |
| **E01** | Initial access vector; execution of malicious document. | Benign document; opened only in preview without code execution. | Message ID & hash? Process tree created? Persistence or outbound calls? |
| **E02** | Stolen credentials or session token from E01 attachment. | Legitimate user travel, new VPN/proxy, or dynamic IP assignment. | MFA result? User location/device owner? Token/rule/password changes made? |
| **E03** | Unauthorized lateral movement using service account. | Schedule drift, automated script, legitimate admin maintenance. | Source hosts? Session type? Post-logon commands? Account authorization? |
| **E04** | Data exfiltration staging prior to encryption. | Approved backup/sync, large business file upload, software update. | Destination account/owner? Generating process? Did transfer complete? |
| **E05** | Backup completed, but restore points contain encrypted/corrupted state. | True clean success, but application consistency remains unverified. | Restore point timestamp? Snapshot integrity? Isolated restore possible? |
| **E06** | Active ransomware deployment across file infrastructure. | Localized file corruption, rogue bulk process, planted ransom note. | Process ID/hash? Exact encryption time? Other shares/hosts affected? |
| **E07** | Dependency failure due to locked assets on `FS01`. | Independent application/database fault on LMS01 platform. | Can staff access files? DB/web engine status? Specific failed calls? |
| **E08** | Availability issue caused by ransomware encryption/lock. | Permission issue, document-specific lock, network share glitch. | Can other shares be read? Email compromise status? Offline contact copy? |

#### Impact Assessment & Verification Guidance
| Evidence ID | Affected Assets | CIA Triad Implications | Recommended Verification Activity |
| :--- | :--- | :--- | :--- |
| **E01** | FIN-PC07, M365 Mail | **C:** Potential credential exposure. **I:** Potential workstation alter. **A:** None direct. | Preserve email/attachment; review M365 message trace & endpoint EDR telemetry. |
| **E02** | M365 Identity, Mailbox | **C:** Mailbox exposure. **I:** Potential forwarding rules. **A:** None direct. | Correlate IP/MFA/device logons; interview user regarding travel. |
| **E03** | `svc_backup`, FS01, BAK01 | **C:** Privileged data exposure. **I:** File/backup alteration. **A:** Backup trust impaired. | Collect Windows Security logs, Sysmon, PowerShell history, backup console logs. |
| **E04** | FIN-PC07, Cloud Dest. | **C:** Data exfiltration. **I:** Unauthorized copying. **A:** None direct. | Inspect network/proxy logs, endpoint process activity, cloud destination details. |
| **E05** | FS01, LMS01, BAK01 | **C:** Backups contain data. **I:** Backup trustworthiness unverified. **A:** Potential recovery loss. | Export job logs; perform isolated sandboxed restoration test. |
| **E06** | FIN-PC07, FS01, LMS01 | **C:** Data access. **I:** Encryption/metadata alteration. **A:** Shared files unavailable. | Preserve EDR alerts; isolate/image system; analyze ransom note metadata. |
| **E07** | LMS01, Exam Workflow | **C:** Records exposed if breached. **I:** Content altered. **A:** Portal workflows blocked. | Capture LMS01 logs; perform controlled application test; check FS01 paths. |
| **E08** | Response Team, Email | **C:** Disclosure if mail read. **I:** Contacts altered. **A:** Out-of-band communication required. | Test permissions; establish verified phone communications; obtain offline contact list. |

---

### 1.3 Assets and Scope

#### Asset Impact Register
| Asset ID | Asset / Service | Business Function | Observed Status | Potential Security Implications | Affected Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **FIN-PC07** | Finance Workstation | Finance processing | Unexpected attachment opened; 1.2 GB HTTPS upload; mass file changes. | Endpoint compromise, credential theft, exfiltration of finance records. | Affected (Investigation required) |
| **FS01** | File Server | Shared storage & LMS dependency | `.locked` files; ransom note; contact list down; unusual `svc_backup` logons. | Mass encryption, lateral movement, LMS service degradation. | Affected (Confirmed service impact) |
| **LMS01** | Learning Portal | Course delivery & assessments | Login loads; materials and assessment submissions fail. | Dependency failure, assessment delay for 100 learners, material corruption. | Affected (Confirmed service impact) |
| **BAK01** | Backup Repository | System restoration | Unusual `svc_backup` logon; non-immutable backups. | Recovery image tampering, backup deletion, malicious restore points. | Requires Investigation |
| **M365-ID** | M365 / Corporate Email | Identity & communication | Finance user sign-in from unfamiliar IP; email trust unverified. | Account takeover, mail forwarding, compromised out-of-band communications. | Requires Investigation |
| **SVC-BACKUP** | Service Account | Admin access to FS01/BAK01 | Remote admin logons outside regular schedule. | Lateral movement, elevated privileges used for destructive deployment. | Requires Investigation |
| **FIN-USER** | Finance User Account | Financial management | Opened unexpected email attachment; anomalous logon location. | Identity theft, mailbox misuse, access to financial databases. | Requires Investigation |
| **SUP-01** | Security Telemetry | EDR, proxy, logs, support | Log records available; missing server EDR agents. | Log tampering, blind spots in server activity monitoring. | Requires Protection |

---

### 1.4 CIA Triad Assessment

* **Confidentiality:** **Potential Material Impact (Unestablished).** E02, E03, and E04 present exposure vectors, but do not yet confirm data theft, mailbox extraction, or the specific contents of the 1.2 GB upload.
* **Integrity:** **Observed Material Anomaly.** E06 confirms mass file changes and `.locked` files/ransom notes. E03 shows potential privileged access misuse. E05 does not guarantee data or application consistency.
* **Availability:** **High Observed Impact (Time-Critical).** Primary disruption to `FS01` and `LMS01` directly threatens the scheduled 11:00 WAT examination for 100 learners.

---

### 1.5 Response Priorities

1. **Life Safety & Safeguarding:** Check immediately (none identified in this scenario).
2. **Safe Coordination:** Establish phone-based out-of-band communications while corporate email trust is verified.
3. **Active Containment:** Contain active spread while preserving volatile memory and evidence.
4. **Evidence Preservation:** Secure endpoint, identity, proxy, server, and backup logs with full chain of custody.
5. **Identity Safeguarding:** Implement identity controls for `FIN-USER`, M365, and `svc_backup`.
6. **Scope Hunt:** Search environment for broader compromised endpoints or persistent hooks.
7. **Backup Protection:** Isolate and test `BAK01` snapshots prior to any recovery attempt.
8. **Exam Continuity:** Make an evidence-based exam decision; do **not** blindly reopen portal before 11:00 WAT.
9. **Recovery Criteria:** Formulate secure restoration criteria for post-containment phases.

---

### 1.6 Investigation Priorities & Responsibilities

| Inv ID | Related Evidence | Priority | Core Investigation Question | Responsible Role | Required Records / Artifacts | Current Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **IP-01** | E01, E02 | High | Did the payroll attachment trigger execution or identity compromise? | Security Analyst / Forensics | Attachment hash, M365 audit logs, EDR process trees, user interview. | Not Investigated |
| **IP-02** | E02, E03 | High | Were the M365 and `svc_backup` logons authorized or malicious? | Incident Response Lead | M365 sign-in logs, Windows Event Logs (4624/4672), PowerShell logs, admin interviews. | Not Investigated |
| **IP-03** | E04 | High | What content was uploaded in the 1.2 GB HTTPS transfer from `FIN-PC07`? | Forensic Specialist | Proxy logs, DNS history, PCAP, endpoint network connection telemetry, browser history. | Not Investigated |
| **IP-04** | E03, E05, E06 | High | Was `BAK01` or `FS01` modified/tampered with before backup completion? | Forensic Specialist | Backup job logs, repository access audit, snapshot metadata, server EDR records. | Not Investigated |
| **IP-05** | E05, E06, E07 | High | Can backups be safely restored in an isolated sandbox? | IT Operations Lead | Isolated hypervisor restore, application health checks, IOC malware scan. | Not Investigated |
| **IP-06** | E06, E07 | High | What is the scope and mechanism of the ransomware/locked files? | Security Analyst | Sample encrypted files, ransom note analysis, file system modify timestamps, process lineage. | Not Investigated |
| **IP-07** | E04, E06-E08 | Medium | Was sensitive learner/staff PII accessed or exfiltrated? | Legal / Privacy Adviser | Correlated network, proxy, file-access logs; data classification register analysis. | Not Investigated |

---

## 2. Task 2 — Incident Response Governance and CSIRT Responsibilities

### 2.1 Policy Purpose, Governance & Decision Authority

Northbridge’s proposed Incident Response policy establishes command authority, evidence-preservation rules, and business continuity integration to limit operational damage while maintaining academic services.

#### Decision Authority Matrix
| Decision Scope | Proposed Owner | Control & Governance Constraints |
| :--- | :--- | :--- |
| **Declare & Direct Incident** | Incident Response Lead | Document evidence, severity, uncertainty, and re-evaluation timeline. |
| **Authorize Normal Containment** | Incident Response Lead | Consult IT Ops & Business Owners; define boundary & operational impact. |
| **Execute Technical Actions** | IT Operations Lead | Execute strictly within authorized scope; record execution state. |
| **Analyze Evidence & Security** | Security Analyst | Provide evidence-based recommendations; no independent containment authority. |
| **Material Exceptions / Critical Severity**| Senior Management | Authorize institutional risk, external resources, public statements. |
| **Accept Service Return** | Business Service Owner | Validate business readiness after technical and security sign-offs. |
| **Business Continuity Coordination** | Business Continuity Coord. | Coordinate academic workarounds; cannot bypass security controls. |

---

### 2.2 Incident Declaration & Escalation Model

```
   [Triage & Detection]
            │
            ▼
 [Credential / Severity Event]
            │
            ▼
┌──────────────────────────────┐
│ Incident Response Lead (IRL) │ ◄── Declares & Activates Incident
└──────────────┬───────────────┘
               │
      ┌────────┴────────┐
      ▼                 ▼
[High Provisional]   [Escalation Tier]
(08:45 WAT Baseline)        │
                            ├─► Low: Standard documented workflow
                            ├─► Medium: IRL + IT + Service Owner coordination
                            ├─► High: Management notification + Protective isolation
                            └─► Critical: Exec Sponsor + Continuity activation + External support
```

* **Emergency Isolation Authority:** If the IRL is unreachable and delay will cause catastrophic harm, the **IT Operations Lead** (or delegated senior IT/Security staff) may execute minimal emergency containment, followed immediately by retrospective management review.

---

### 2.3 CSIRT Organizational Structure & Staffing Allocation

```
                        ┌──────────────────────────────┐
                        │ Senior Management / Sponsor  │
                        │          (MGT-01)            │
                        └──────────────┬───────────────┘
                                       │
                        ┌──────────────┴───────────────┐
                        │    Incident Response Lead    │
                        │           (IRL-01)           │
                        └──────────────┬───────────────┘
                                       │
        ┌──────────────────────────────┼──────────────────────────────┐
        ▼                              ▼                              ▼
┌──────────────┐              ┌──────────────┐              ┌──────────────┐
│ Security     │              │ IT Operations│              │ Business     │
│ Analyst      │              │ & Recovery   │              │ Continuity   │
│ (SEC-01)     │              │ (OPS-01)     │              │ (BCC-01)     │
└───────┬──────┘              └───────┬──────┘              └───────┬──────┘
        │                             │                             │
        ▼                             ▼                             ▼
┌──────────────┐              ┌──────────────┐              ┌──────────────┐
│ Digital      │              │ External /   │              │ Academic /   │
│ Forensics    │              │ Vendor       │              │ Service      │
│ (FOR-01)     │              │ Support      │              │ Owner        │
└──────────────┘              └──────────────┘              └──────────────┘
```

#### Capacity & Internal Staffing Allocations
* **IT Staff 1:** Assigned as **Incident Response Lead (IRL-01)**. Excluded from hands-on command-time technical execution.
* **IT Staff 2:** Assigned as **IT Operations Lead (OPS-01)**. Technical execution and service recovery lead.
* **IT Staff 3:** Assigned as **Technical Operator / Forensics Dual-Hat (FOR-01)**. System handling under supervision.
* **Security Analyst 1:** Assigned as **Security Analyst (SEC-01)**. Triage, investigation, and security validation lead.

---

### 2.4 RACI Accountability Matrix

* **R** = Responsible | **A** = Accountable (Strictly **1** per activity) | **C** = Consulted | **I** = Informed

| ID | Activity | R | A | C | I |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **R01** | Detection & Triage | SEC-01 | SEC-01 | OPS-01 | IRL-01, MGT-01 |
| **R02** | Technical Analysis | SEC-01 | SEC-01 | FOR-01, OPS-01, M365-01 | IRL-01, BSO-01 |
| **R03** | Incident Declaration | IRL-01 | IRL-01 | SEC-01, OPS-01 | MGT-01 |
| **R04** | Response Activation | IRL-01 | IRL-01 | SEC-01, OPS-01, BCC-01 | MGT-01, LP-01, COM-01 |
| **R05** | Severity Escalation | IRL-01 | IRL-01 | SEC-01, OPS-01, BSO-01 | MGT-01 |
| **R06** | Normal Containment | OPS-01 | IRL-01 | SEC-01, FOR-01, BSO-01 | MGT-01, COM-01 |
| **R07** | Emergency Containment | OPS-01 | OPS-01 | IRL-01, SEC-01, BSO-01 | MGT-01, BCC-01 |
| **R08** | Evidence Handling | FOR-01 | FOR-01 | SEC-01, OPS-01, IRL-01 | LP-01, MGT-01 |
| **R09** | Stakeholder Communications | COM-01, BCC-01 | COM-01 | IRL-01, LP-01 | MGT-01, SEC-01 |
| **R10** | Legal/Breach Assessment | LP-01 | LP-01 | SEC-01, IRL-01, MGT-01 | BSO-01, COM-01 |
| **R11** | Backup Integrity Check | OPS-01, FOR-01| SEC-01 | BKP-01, IRL-01, BSO-01 | MGT-01, BCC-01 |
| **R12** | Continuity Activation | BCC-01 | MGT-01 | IRL-01, BSO-01, OPS-01 | SEC-01, LP-01 |
| **R13** | Exam Continuity Approval | BCC-01, BSO-01| BSO-01 | IRL-01, SEC-01, OPS-01 | COM-01 |
| **R14** | Technical Restoration | OPS-01 | OPS-01 | SEC-01, BSO-01, IRL-01 | MGT-01, BCC-01 |
| **R15** | Recovery Security Check | SEC-01 | SEC-01 | FOR-01, OPS-01, IRL-01 | BSO-01, MGT-01 |
| **R16** | Data Integrity Verification| OPS-01, FOR-01| OPS-01 | SEC-01, BSO-01 | IRL-01, MGT-01 |
| **R17** | Business Return Acceptance | BSO-01 | BSO-01 | IRL-01, SEC-01, OPS-01 | COM-01 |
| **R18** | Incident Closure & PIR | IRL-01 | IRL-01 | All Roles | MGT-01 |
| **R19** | Routine Operational Deviation| IRL-01 | IRL-01 | SEC-01, OPS-01 | MGT-01 |
| **R20** | Policy Exception Approval | IRL-01 | MGT-01 | SEC-01, OPS-01, LP-01 | COM-01 |
| **R21** | Decision Delegation | IRL-01 | IRL-01 | OPS-01, SEC-01 | MGT-01 |
| **R22** | Deputy Appointment | MGT-01 | MGT-01 | IRL-01, OPS-01, BCC-01 | SEC-01, COM-01 |

---

### 2.5 CSIRT Role Register

| Role ID | Functional Role | Primary Staff Assignment | Primary Decision Authority |
| :--- | :--- | :--- | :--- |
| **IRL-01** | Incident Response Lead | IT Staff 1 | Overall response direction, activation, normal containment. |
| **SEC-01** | Security Analyst | Security Analyst 1 | Security triage, investigation, and recovery clearance. |
| **FOR-01** | Forensics & Evidence Custodian | IT Staff 3 (Dual-Hat) | Forensic collection, chain of custody maintenance. |
| **OPS-01** | IT Operations & Recovery Lead | IT Staff 2 | Infrastructure management, execution of containment, restoration. |
| **LP-01** | Legal / Privacy Adviser | Internal Counsel / External | Regulatory assessment, breach reporting advice. |
| **COM-01** | Communications Coordinator | Assigned Non-IT Staff | Fact-bounded notification drafting & distribution. |
| **BCC-01** | Business Continuity Coordinator | Functional Appointee | Workaround arrangements, academic impact planning. |
| **BSO-01** | Academic Service Owner | Academic Ops Lead | Exam continuity parameters, final business service return sign-off. |
| **MGT-01** | Executive Sponsor / Senior Mgmt | Senior Management | Critical risk acceptance, budget, public release authorization. |

---

## 3. Task 3 — Response Playbook and Evidence Preservation

### 3.1 Operating Rules & Chronological Action Register

#### First 60 Minutes (08:45 – 09:45 WAT)
```
08:45 WAT ────► Open Incident Record; Set High Provisional Baseline (T3-01)
08:48 WAT ────► Establish Out-of-Band Phone Tree (T3-02)
08:50 WAT ────► Secure Volatile EDR/Server Logs Before Changes (T3-03)
08:55 WAT ────► Isolate Host FIN-PC07 (T3-04)
09:00 WAT ────► Disable FIN-USER & svc_backup Credentials (T3-05)
09:05 WAT ────► Assess FS01 Isolation vs LMS01 Impact (T3-06)
09:15 WAT ────► Preserve E04 Proxy Metadata (T3-07)
09:25 WAT ────► Disconnect & Isolate BAK01 Repository (T3-08)
09:35 WAT ────► Convene Exam Continuity Board re: 11:00 Exam (T3-09)
09:45 WAT ────► Issue Internal Holding Briefing (T3-10)
```

#### Remainder of First 24 Hours (09:45 Day 0 – 08:45 Day 1)
* **T3-11 (10:00):** Cross-correlate endpoint, cloud, proxy, and identity telemetry.
* **T3-12 (10:15):** Investigate attachment execution (`E01`) and M365 IP logon (`E02`).
* **T3-13 (10:30):** Investigate `svc_backup` event history and snapshot modification logs.
* **T3-14 (11:00):** Execute approved exam workaround or officially postpone exam.
* **T3-15 (12:00):** Conduct scope sweep across environment for secondary webshells/persistence.
* **T3-16 (14:00):** Construct Eradication and Credential Rotation Plan.
* **T3-17 (18:00):** Conduct isolated sandbox restoration test of candidate backup snapshot.
* **T3-18 (Day 1 08:45):** Phased rebuild, system restoration, and monitoring enablement.
* **T3-19 (Day 1+):** Post-restoration monitoring for persistent indicators.
* **T3-20 (Closure):** PIR execution, corrective actions handoff, formal incident closure.

---

### 3.2 Difficult Decision Handling

#### Containment vs. Evidence Preservation
If mass file encryption is actively spreading (`E06`), immediately isolating hosts takes precedence over full memory imaging. The IRL authorizes immediate containment; IT Operations notes the evidence trade-off and captures volatile state where possible.

#### Exam Availability vs. Unverified Backup Safety
The 11:00 WAT exam creates high business pressure, but restoring from an unvalidated backup (`E05`) risks re-introducing malware or deploying corrupted data. **Rule:** **Never reopen LMS01 on unvalidated backups to meet a deadline.** The Academic Owner must execute contingency plans while isolated testing proceeds.

---

### 3.3 Canonical Evidence Register

| Item ID | Target Source | Purpose / Observation Link | Proposed Collection Method | Collector Role | Integrity / Chain Control |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **T3-EV-01**| FIN-PC07 | Process tree, E01, E04, E06 | Live memory dump, EDR log export, disk image | FOR-01 / SEC-01 | SHA-256 hash log; write-blocker image storage. |
| **T3-EV-02**| FS01 | Locked files, ransom note, E08 | Event logs, filesystem snapshot metadata | FOR-01 / OPS-01 | Read-only image copy; restricted evidence repo. |
| **T3-EV-03**| M365 Tenant | E02 logon anomaly, token activity | Unified Audit Log (UAL) export via PowerShell | SEC-01 | Export reference ID; secure cloud bucket. |
| **T3-EV-04**| Edge Proxy | E04 1.2 GB HTTPS transfer | Firewall & proxy access log export | SEC-01 | System-generated log export; hash verification. |
| **T3-EV-05**| BAK01 / Console| E03, E05 backup state & logons | VSS logs, backup console database dump | OPS-01 / FOR-01 | Isolated snapshot copy; restricted permissions. |
| **T3-EV-06**| LMS01 Host | E07 portal degradation details | Web server access/error logs, DB audit logs | OPS-01 / SEC-01 | Time-synchronized log dump; secure storage. |

---

## 4. Task 4 — Communication and Escalation Framework

### 4.1 Stakeholder Communication Matrix

| Stakeholder Group | Trigger Event | Primary Channel | Approver | Frequency |
| :--- | :--- | :--- | :--- | :--- |
| **Senior Management** | High provisional declaration; Exam decision | Out-of-band call + Briefing | IRL-01 | Declaration + 2-hour updates (Next: 10:30 WAT) |
| **IT & Security Team** | Response activation; containment action | Secure Voice Tree / Offline Log | IRL-01 | Ongoing continuous operational coordination |
| **Learner Cohort** | Portal outage / Exam status update | Verified SMS / Portal Banner | BSO-01 / MGT-01 | Initial notice prior to 11:00; ongoing changes |
| **Teaching Staff** | Course material unavailability | Staff Voice Tree / Direct Call | BCC-01 | Hourly updates during business hours |
| **Service Vendors** | Technical support / Provider escalation | Provider Support Portal | OPS-01 / MGT-01 | As required by investigation findings |
| **Legal & Privacy** | Potential PII data loss check | Encrypted Out-of-Band Call | IRL-01 | Immediate upon data impact discovery |
| **Staff & Users** | General IT advisory | Approved Staff Voice Tree | COM-01 | Initial safety guidance; material updates |
| **Media / Public** | External queries / Speculation | Formal Press Statement | MGT-01 | Ad-hoc (Strict holding statement policy) |

---

### 4.2 Key Briefings & Notices

#### Executive Briefing (08:45 WAT Baseline)
> "At 08:45 WAT, Northbridge activated incident response for a High-provisional ransomware incident impacting FIN-PC07 and FS01 file shares, degrading LMS01 portal functions. The 11:00 WAT examination for 100 learners is affected. File encryption and unusual administrative logons are confirmed. Exfiltration and attachment code execution are unconfirmed. Out-of-band communications are active due to unverified corporate email trust. Next update at 10:30 WAT."

#### Learner Status Notice
> "Northbridge Skills Institute is addressing a technical issue currently affecting LMS01 portal materials and assessment submissions. We are determining continuity plans for the 11:00 WAT examination. Please keep mobile devices available for official status updates. Do **not** send assessment submissions or credentials via unverified email or social media channels."

---

### 4.3 Operational vs. Breach Notifications

```
             [Incident Event]
                    │
       ┌────────────┴────────────┐
       ▼                         ▼
[Operational Status Notice]   [Formal Breach Assessment]
 ├─ Focus: Service status     ├─ Focus: Legal obligations
 ├─ Content: Workarounds      ├─ Content: Proven PII impact
 ├─ Audience: Users/Learners  ├─ Audience: Regulators/Data Subjects
 └─ Channel: Status page      └─ Channel: Formal legal notice
```

---

## 5. Task 5 — Tabletop Exercise and Improvement Plan

### 5.1 Simulation Parameters & Injects

* **Exercise Duration:** 60 Minutes (Simulated)
* **Scenario Baseline:** High-Provisional Ransomware Incident at 08:45 WAT on Day 0.

```
00:05 ──► Briefing & Baseline Setup
00:10 ──► Inject 1: Management pressure to reopen LMS01 for 11:00 Exam despite unverified backup.
00:20 ──► Inject 2: Threat actor claims exfiltration of 1,800 learner records (Unverified screenshot).
00:35 ──► Inject 3: Test restoration of latest network backup fails with unreadable snapshot error.
00:45 ──► Inject 4: Social media rumors claim exam cancellation; media query received.
00:50 ──► Inject 5 (Add.): M365 audit log export delayed; Finance Officer unavailable.
00:55 ──► Debrief & Handover to PIR
```

---

### 5.2 Canonical Decision Log

| Min | Inject | Decision Taken | Decision Owner | Rationale & Outcome |
| :--- | :--- | :--- | :--- | :--- |
| **10** | Pressure to reopen LMS01 | **Reject premature reopening.** Execute alternative exam workaround. | IRL / MGT-01 / BSO-01 | Restoring unvalidated backups risks system corruption or re-infection. |
| **20** | Exfiltration claim (1.8k records) | **Preserve claim as unconfirmed.** Refer to Privacy Adviser. | IRL-01 / LP-01 | Unverified screenshots are not proof of breach; avoid false public statements. |
| **35** | Backup test failure | **Halt restore route.** Request specialist isolated recovery. | OPS-01 / IRL-01 | Primary restore image corrupted; prevents unsafe deployment to production. |
| **45** | Social media rumor & media query | **Issue approved holding statement.** Deny unconfirmed claims. | COM-01 / MGT-01 | Prevents panic; maintains official factual messaging channel. |
| **50** | M365 log delay / User away | **Maintain open identity investigation.** Proceed with alternative logs.| SEC-01 / IRL-01 | Avoids drawing false conclusions on identity compromise without artifacts. |
| **55** | Exercise closure attempt | **Keep incident status open.** Transition to recovery phase. | IRL-01 | Governance gate: cannot close incident while recovery & PII checks remain open. |

---

### 5.3 Corrective Action Register

| Action ID | Priority | Gap / Finding Identified | Corrective Action Required | Assigned Owner | Target Completion | Measurable Success Evidence |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **CA-01** | Critical | Backup recoverability failure during test. | Implement isolated, automated sandbox restoration tests. | OPS-01 | 30 Days | Successful automated test logs for 3 consecutive restoration cycles. |
| **CA-02** | High | Inaccessible contact list on FS01. | Deploy encrypted, out-of-band cloud contact repository. | BCC-01 / COM-01 | 14 Days | Successful out-of-band contact retrieval during unannounced test. |
| **CA-03** | High | Incomplete server EDR coverage. | Install EDR agents across all infrastructure servers (FS01/BAK01). | SEC-01 / OPS-01 | 45 Days | 100% agent coverage confirmed in EDR central dashboard. |
| **CA-04** | High | Dual-hatting role conflicts during crisis. | Train designated deputies for key CSIRT command roles. | IRL-01 | 60 Days | Tabletop simulation completed successfully using secondary deputies. |
| **CA-05** | High | Risk of premature breach disclosure. | Formulate PII assessment decision tree and communications checklist. | LP-01 / COM-01 | 30 Days | Signed-off legal checklist integrated into incident response toolkit. |
| **CA-06** | Medium | Premature closure risk during incidents. | Establish mandatory multi-gate closure sign-off template. | IRL-01 | 30 Days | Closure template added to incident policy and verified by management. |

---

## 6. Task 6 — Case Study Analysis and Critical Reflection

### Comparative Analysis: Week 20 Healthcare Incident vs. Northbridge

```
┌──────────────────────────────────────┐     ┌──────────────────────────────────────┐
│       Healthcare Case Study          │     │    Northbridge Skills Institute      │
├──────────────────────────────────────┤     ├──────────────────────────────────────┤
│ • Fast EDR detection & isolation     │     │ • Partial EDR server coverage        │
│ • Validated immutable offline backups│ VS  │ • Non-immutable, untested backups    │
│ • 72h critical system recovery       │     │ • Imminent exam pressure (11:00 WAT) │
│ • 7-day total downtime               │     │ • Out-of-band phone tree needed      │
└──────────────────────────────────────┘     └──────────────────────────────────────┘
```

#### Key Strengths Identified in Case Study
1. **Rapid Network Isolation:** Network segmentation successfully restricted ransomware to initial zones.
2. **Offline Backup Preservation:** Air-gapped backups allowed full system reconstruction without paying ransom.
3. **Structured Lessons Learned:** Post-incident review led to direct security baseline enhancements.

#### Limitations & Transferable Lessons for Northbridge
* **"Not Confirmed" $\neq$ "Not Exfiltrated":** The healthcare case noted no data theft was confirmed, but lacked exhaustive log coverage proof. Northbridge must avoid assuming data is safe simply because proxy logs are unclear (`E04`).
* **72-Hour Restoration vs. Full Recovery:** Critical system restoration (72h) is only the first step; business processes required 7 days. Northbridge must separate technical system restoration from academic return-to-service sign-off.
* **Direct Applied Improvements:**
  1. Northbridge must immediately move to **immutable offline backups** (current last offline copy is 3 days old).
  2. Complete **EDR deployment across core servers** (`FS01`, `LMS01`, `BAK01`) to eliminate visibility gaps.
  3. Formally decouple deadline pressure (e.g., 11:00 WAT exam) from technical recovery clearance.

---

## 7. References & Acknowledgements

### References
1. **ICDFA** (2026). *GRC105 Incident Response Planning Assignment Brief & Scenario Data*. Northbridge Skills Institute.
2. **ICDFA** (2026). *Incident Response Planning*. GRC105 Week 20 Presentation Slides 1–18.
3. **Nelson, A., Rekhi, S., Souppaya, M., & Scarfone, K.** (2025). *NIST SP 800-61 Revision 3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management: A CSF 2.0 Community Profile*. National Institute of Standards and Technology. [https://csrc.nist.gov/pubs/sp/800/61/r3/final](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
4. **Cichonski, P., Millar, T., Grance, T., & Scarfone, K.** (2012). *NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response*. National Institute of Standards and Technology. [https://csrc.nist.gov/pubs/sp/800/86/final](https://csrc.nist.gov/pubs/sp/800/86/final)
5. **CISA & Partners** (2023). *#StopRansomware Guide*. Cybersecurity and Infrastructure Security Agency. [https://www.cisa.gov/stopransomware/ransomware-guide](https://www.cisa.gov/stopransomware/ransomware-guide)

### AI Assistance Acknowledgement
AI assistance was utilized in accordance with academic guidelines for formatting, markdown structuring, table alignment, and consistency verification across artifacts. The author retains full responsibility for all evidence interpretations, analytical conclusions, and strategic recommendations presented in this report.
