# Task 1 — Incident Classification and Initial Assessment

> Extracted from the complete ICDFA GRC105 assignment. Content is organised by task; tables and source terminology are retained as Markdown where possible.

## Task 1 — Incident Classification and Initial Assessment

Organization: Northbridge Skills Institute (fictional) Assessment point: 08:45 WAT on Day 0 Current initial severity: High — provisional Scope: Task 1 only. No Task 2–6 content is included.

### 3.1	Incident classification and initial assessment

The evidence is consistent with a suspected ransomware or destructive file-impact event involving possible identity misuse, possible unauthorized transfer, and possible backup compromise. The classification is not based solely on the ransom note. It is based on the combination of observed file and learner-service impact, unusual, privileged activity, uncertain data transfer, time-critical examination impact, and uncertain recovery capability.

#### 3.1.1	Initial classification: High — provisional

High is justified by:

E06: mass file changes on FIN-PC07 and. locked files plus a ransom note in FS01 shared folders;

E07: learners cannot open materials or submit assessments, creating confirmed learner-facing availability impact;

E08: the FS01 incident contact list is inaccessible, and corporate email trust is unverified;

E03: svc_backup made unusual remote administrator logons to FS01 and BAK01;

E04: FIN-PC07 uploaded 1.2 GB over HTTPS to an unfamiliar cloud-storage destination;

the 11:00 examination for 100 learners, the institute’s sensitive information holdings, limited staffing, and uncertain backup recoverability.

The assessment is not Critical at 08:45 because the evidence does not confirm institution-wide loss, broad data disclosure, compromise of every recovery path, or persistent attacker control. The portal login still loads; staff phones are available, and the event scope and causal chain remain unverified. These limitations do not remove the urgency; they explain the provisional High decision.

#### 3.1.2	Observed, suspected, and unconfirmed impact

| Category | Current assessment |
| --- | --- |
| Observed impact | E06 file-change indicators on FIN-PC07/FS01; E07 learner-facing portal functions unavailable; E08 contact-list access problem; E03 unusual, privileged logons; E04 upload event. |
| Suspected impact | Ransomware or destructive file activity; privileged misuse or lateral movement; dependency-driven LMS01 disruption; possible identity misuse; possible backup-risk activity. |
| Unconfirmed consequences | Malicious execution from E01; account compromise from E02; personal data transfer in E04; BAK01 tampering; malware family; institution-wide spread; attacker identity. |
| Additional evidence needed | Endpoint process/file telemetry; Microsoft 365/MFA/device data; Windows and backup logs; proxy/cloud metadata; application and dependency checks; isolated backup validation; broader scope hunt. |

Full four-tier criteria are in analysis/severity-classification.md and data/severity-criteria.csv.

### 3.2	Evidence-linked timeline and uncertainty

The complete E01–E08 chronology, Day minus 1/Day 0 distinction, 08:45 WAT control point, possible relationships, and unverified-link statements remain in:

analysis/incident-chronology.md

data/evidence-analysis-register.csv

diagrams/incident-timeline.mmd

The observations/hypotheses/questions separation and alternative explanations remain in analysis/observations-hypotheses-questions.md. No Stage 2 conclusion changes the Stage 1 evidence record.

### 3.3	Assets and scope

The asset-impact register distinguishes assets with observed impact from assets that require investigation. At 08:45:

Affected or service-impacted for assessment: FIN-PC07, FS01, and LMS01.

Requires urgent investigation but not confirmed affected: BAK01, Microsoft 365 identity/email, svc_backup, the finance officer account, and supporting telemetry/coordination services.

Potentially affected data: learner contact, admission, assessment, finance, credential, mailbox, shared-file, backup, and response-contact information. No data category is confirmed exfiltrated.

See data/asset-impact-register.csv for business functions, evidence, confirmed impact, potential impact, priority, and verification requirements.

### 3.4	CIA assessment

#### 3.4.1	Confidentiality

Potential material impact — not established. E02, E03, and E04 create possible access or transfer paths, but none proves account compromise, unauthorized reads, or the content of the 1.2 GB upload. The institution’s information holdings make the questions important, not resolved.

#### 3.4.2	Integrity

Observed material anomaly; scope and cause unconfirmed. E06 shows mass file changes and .locked files/ransom note indicators. E03 creates a privileged-access integrity concern. E05 does not establish backup integrity, application consistency, or cleanliness.

#### 3.4.3	Availability

High observed impact to important services, with examination risk. E06 and E08 show FS01 access/file problems. E07 shows learners cannot access materials or submit assessments. The stated LMS01 dependency on FS01 and the 11:00 examination make this time-critical. Availability impact is not evidence of data disclosure.

See analysis/cia-impact-assessment.md and data/cia-impact-matrix.csv for the separate property assessments.

### 3.5	Response priorities

The response priority order is:

Check life-safety or safeguarding consequences; none are stated in the supplied scenario.

Establish safe coordination using staff phones or another approved channel while email trust is checked.

Contain suspected active compromise while preserving high-value evidence.

Preserve endpoint, identity, network, server, backup, application, EDR, and helpdesk records with provenance.

Protect the finance officer account, Microsoft 365 identity, and svc_backup through an approved decision.

Hunt for broader scope and protect potentially sensitive institutional information.

Protect and validate backup options in isolation.

Make an evidence-informed examination-continuity decision; do not reopen the portal solely because of the deadline.

Prepare validated restoration and monitoring criteria for later recovery work.

The detailed matrix is in analysis/response-prioritisation.md and data/response-priority-matrix.csv. Detailed ordered actions, custody fields, restoration acceptance criteria, and communications remain in later Task 3/4 work and are not completed here.

### 3.6	Severity and scope reassessment

Severity should increase to Critical if evidence confirms severe examination or institution-wide disruption, broad compromise, material data disclosure, persistent privileged control, or loss of all viable recovery options. High should be maintained while material service impact, unresolved privileged activity, uncertain data impact, or unvalidated recovery persists.

Severity may reduce only after evidence supports bounded scope, authorized identity/privileged activity, a legitimate unrelated transfer, no active destructive activity, safe service continuity, and validated recovery. An asset may be excluded from confirmed affected scope only when records show no related unauthorized access, change, persistence, or service impact and the asset is not needed to explain another observation.

The complete trigger and validation register is in analysis/severity-reassessment-triggers.md.

### 3.7	Evidence gaps and limitations

The assessment does not have the original attachment, complete identity/mailbox logs, endpoint process/file telemetry, source hosts and commands for svc_backup, full server/application/backup logs, cloud-destination ownership/object data, forensic images, hashes, custody records, or restoration results. Server EDR coverage is incomplete. No forensic acquisition, hash verification, restoration test, account reset, containment action, notification, or service restoration is claimed.

The High classification is therefore a defensible initial decision under uncertainty, not a final finding about attacker identity, data theft, malware family, or total scope.

### 3.8	References

ICDFA GRC105 Incident Response Assignment, Northbridge Skills Institute scenario, initial evidence pack E01–E08, Task 1 instructions, and marking rubric.

ICDFA, Incident-Response-Planning.pptx, Week 20 slides 4, 6, 9, 10, and 11.

Nelson, A., Rekhi, S., Souppaya, M., and Scarfone, K. (2025). NIST SP 800-61r3, Incident Response Recommendations and Considerations for Cybersecurity Risk Management: A CSF 2.0 Community Profile. Official NIST publication.

Figure 1 — Initial severity decision logic.

Evidence analysis register — evidence core

| Evidence ID | Timestamp (WAT) | Original source | Confirmed observation |
| --- | --- | --- | --- |
| E01 | Day minus 1 16:40 WAT | Assignment brief, Initial evidence pack: user report and mail record | A finance officer opened an unexpected payroll attachment on FIN-PC07. The supplied record does not verify execution of malicious code. |
| E02 | Day 0 01:15 WAT | Assignment brief, Initial evidence pack: Microsoft 365 audit | The finance officer account signed in from an unfamiliar IP address and a new device. MFA status and the user's involvement are unknown. |
| E03 | Day 0 01:35 WAT | Assignment brief, Initial evidence pack: Windows logs | The svc_backup account made remote administrator logons to FS01 and BAK01 outside its usual schedule. The reason is unknown. |
| E04 | Day 0 01:50 WAT | Assignment brief, Initial evidence pack: proxy record | FIN-PC07 uploaded 1.2 GB over HTTPS to an unfamiliar cloud storage destination. The record does not reveal the transferred content. |
| E05 | Day 0 02:00 WAT | Assignment brief, Initial evidence pack: backup console | The backup console reported successful jobs for FS01 and LMS01. Recoverability and freedom from compromise have not been established. |
| E06 | Day 0 08:30 WAT | Assignment brief, Initial evidence pack: EDR and helpdesk | EDR and helpdesk records show mass file changes on FIN-PC07. FS01 shared folders contain files with a .locked extension and a ransom note. The malware family is unconfirmed. |
| E07 | Day 0 08:40 WAT | Assignment brief, Initial evidence pack: helpdesk report | The LMS01 portal login page loads, but learners cannot open materials or submit assessments. The scope of damage to LMS01 remains unknown. |
| E08 | Day 0 08:45 WAT | Assignment brief, Initial evidence pack: operations report | The incident contact list on FS01 is inaccessible. Staff phones are available, and the trustworthiness of corporate email is unverified. |

Evidence analysis register — analytical uncertainty

| Evidence ID | Reasonable working hypothesis | Alternative explanation | Unresolved questions |
| --- | --- | --- | --- |
| E01 | The attachment may have been the initial access vector or may have exposed the user to a malicious document; both remain unverified. | The attachment may have been benign, a legitimate document sent unexpectedly, or opened only in a preview without code execution. | What was the message ID and attachment hash? Was the file opened, previewed, or executed? Did FIN-PC07 create child processes, persistence, or outbound connections at this time? |
| E02 | The sign-in may reflect use of stolen credentials, a stolen session, or unauthorized access associated with the earlier attachment. | The sign-in may be legitimate activity from a new device, VPN, proxy, mobile network, or shared egress address; user involvement is not established. | Was MFA satisfied, bypassed, or challenged? Who controlled the device and IP? Were there token, mailbox, forwarding-rule, password, or consent changes? What resources were accessed? |
| E03 | The account may have been misused for unauthorized administrative access or lateral movement toward file and backup systems. | The activity may be scheduled maintenance, an automated job with schedule drift, an administrator action, or a time-synchronization/logging anomaly. | Which source hosts initiated the logons? Were logons interactive or service-based? What commands and changes followed? Was the account owner or job operator authorized? |
| E04 | The transfer may represent staging or exfiltration from FIN-PC07, potentially involving finance or learner information. | The transfer may be a legitimate backup, synchronization, software update, or large business file transfer; HTTPS prevents content identification from the proxy record alone. | What destination, account, and object identifiers were involved? Which process and files generated the transfer? Was the destination approved? Did the transfer complete or recur? |
| E05 | The jobs may have completed as recorded, but their restore points may be incomplete, corrupted, inaccessible, or contain the same compromise. | The console may report job completion despite unverified application consistency, inaccessible snapshots, or a control-plane-only success state. | Which backup set and timestamp are implicated? Can an isolated restore be completed? Are backup credentials, policies, and snapshots intact? Were FS01/LMS01 data or encryption indicators present before backup? |
| E06 | The combined indicators are consistent with a ransomware event affecting FIN-PC07 and FS01, but the execution path, scope, and malware identity remain unverified. | A legitimate bulk file operation, software fault, or test activity could explain some file changes; the ransom note and .locked files could be planted, generated by another process, or unrelated to the mass changes. | Which process performed the changes? When did FS01 changes begin? Are files encrypted, renamed, deleted, or merely inaccessible? Are other hosts or shares affected? |
| E07 | The portal's dependence on FS01 may be causing service degradation because shared materials or related files are unavailable or altered. | The issue may be an LMS01 application, database, authentication, network, or capacity fault independent of the FS01 file changes. | Can staff access the same materials? Are LMS01 application, database, authentication, and network health checks normal? Which files or functions are unavailable? |
| E08 | FS01 availability or access-control impact may be obstructing normal response coordination, requiring phone-based coordination while email trust is checked. | The contact list may be unavailable because of a permissions, share, network, or document-specific problem rather than the same event affecting other FS01 content. | Can other FS01 shares be opened? Is corporate email safe for incident details? Is there an offline or printed contact list? Which staff and providers can be reached by phone? |

Evidence analysis register — impact assessment

| Evidence ID | Potentially affected assets | Confidentiality integrity availability implications |
| --- | --- | --- |
| E01 | FIN-PC07; finance officer identity; Microsoft 365 mail | C: possible exposure of credentials or finance data if malicious; I: possible workstation or document alteration; A: no direct outage shown by this item. |
| E02 | Microsoft 365 identity and mailbox; finance officer account; potentially FIN-PC07 | C: possible exposure of mailbox or identity data; I: possible account or mail-rule changes; A: no direct service outage shown. |
| E03 | svc_backup account; FS01; BAK01; source host(s); backup-management functions | C: privileged access could expose stored data; I: administrative activity could alter files, shares, or backup configurations; A: backup availability or trust could be affected. |
| E04 | FIN-PC07; unfamiliar cloud-storage destination; potentially finance or learner data | C: possible disclosure of data; I: possible unauthorized copying or alteration of data; A: no direct outage shown by this item. |
| E05 | FS01; LMS01; BAK01; backup console and credentials | C: backups may contain copied sensitive data; I: backup integrity and trustworthiness are unverified; A: recovery capability may be unavailable despite the success report. |
| E06 | FIN-PC07; FS01; shared folders; potentially LMS01 through its FS01 dependency | C: possible access to files and subsequent disclosure; I: file contents or metadata may be altered; A: shared-file access is disrupted and dependent services may be impaired. |
| E07 | LMS01; FS01; learner assessment workflow; 11:00 Day 0 online examination | C: learner records may be exposed only if access was unauthorized; I: course or assessment content may be altered; A: portal functions are unavailable to learners and examination readiness is at risk. |
| E08 | FS01; incident contact list; corporate email; staff phones; response team | C: incident details could be disclosed if email is compromised; I: contact data or response records could be altered; A: coordination is impaired by loss of the normal contact list. |

Evidence analysis register — verification and traceability

| Evidence ID | Recommended verification activity | Evidence limitations | Traceability |
| --- | --- | --- | --- |
| E01 | Preserve the email and attachment with headers; review Microsoft 365 message trace and audit data; examine FIN-PC07 process, browser, EDR, and file-system telemetry for the relevant interval. | User report and mail record do not establish code execution, maliciousness, or attacker identity; no forensic collection has yet occurred. | Assignment brief Table 2; Task 1 evidence analysis requirement |
| E02 | Correlate sign-in, MFA, device, conditional-access, token, mailbox-rule, consent, and password-reset records with the user's interview and known travel/device history. | An unfamiliar IP/device is an anomaly, not proof of compromise; audit context, MFA result, and user attribution are incomplete. | Assignment brief Table 2; Task 1 evidence analysis requirement |
| E03 | Collect correlated Windows security, Sysmon/EDR where available, PowerShell, task-scheduler, backup-console, firewall, VPN, and identity records; interview the account owner/operator. | The record shows logon events but not source, commands, authorization, persistence, or successful changes; server EDR coverage is incomplete. | Assignment brief Table 2; scenario fact that svc_backup administers FS01 and BAK01 |
| E04 | Retain proxy/DNS/firewall records; inspect FIN-PC07 process and browser/cloud-sync telemetry; identify destination ownership and account; compare file access and archive activity before the transfer. | Volume and destination are recorded, but content, ownership, completion state, and personal-data involvement are unknown; no exfiltration conclusion is permitted. | Assignment brief Table 2; Task 1 evidence analysis requirement |
| E05 | Export job details and logs; identify restore points; perform a controlled, isolated restoration and integrity/indicator check before any production use. | A successful job report is not a restoration test, clean-backup finding, or proof of application consistency; the scenario states no restoration test in the last 90 days. | Assignment brief Table 2; scenario facts on non-immutable backups and untested restore routes |
| E06 | Preserve EDR alerts and file-event telemetry; isolate or image according to approved forensic procedure; compare affected file samples and ransom note metadata; hunt across servers, endpoints, identities, and backups. | Indicators support a ransomware working hypothesis but do not prove malicious code execution from E01, malware family, attacker identity, encryption scope, or root cause; no acquisition has occurred. | Assignment brief Table 2; scenario fact that LMS01 depends on FS01 |
| E07 | Capture LMS01 application/web/database logs and health metrics; test with a controlled account; map file dependencies and permissions; preserve examination records and helpdesk reports. | The report demonstrates user-facing impact but does not prove LMS01 encryption, data loss, or the cause of the failed functions. | Assignment brief Table 2; scenario fact that LMS01 depends on FS01 |
| E08 | Verify access from a controlled account; use staff phones and an approved alternate channel; check email identity/audit controls; recover an offline contact list without altering the affected share. | The report does not establish the cause of inaccessibility, email compromise, or loss of the contact data; the 08:45 response takeover is a scenario decision, not a forensic finding. | Assignment brief Table 2; scenario statement that control was assumed at 08:45 WAT |

Asset impact register — asset and observed status

| Asset ID | Asset or service | Business function | Relevant evidence IDs | Observed status |
| --- | --- | --- | --- | --- |
| FIN-PC07 | Finance workstation | Finance processing and user endpoint | E01; E04; E06 | Unexpected payroll attachment opened; 1.2 GB HTTPS upload; mass file changes reported. |
| FS01 | Shared file server | Shared institutional files and dependencies for LMS01 | E03; E05; E06; E07; E08 | Unusual svc_backup logons; FS01 backup job reported successful; .locked files/ransom note; contact list inaccessible; LMS01 dependency stated. |
| LMS01 | Learning portal | Learning materials and assessment submission | E05; E07 | Login page loads; learners cannot open materials or submit assessments; backup job reported successful. |
| BAK01 | Network backup repository | Backup storage and recovery capability | E03; E05 | Unusual svc_backup remote administrator logon; backup recoverability not established; network backups are not immutable. |
| M365-ID | Microsoft 365 identity and email | Identity, authentication, and corporate email | E02; E08 | Finance officer account signed in from unfamiliar IP/new device; corporate email trust is unverified; staff phones available. |
| SVC-BACKUP | svc_backup privileged account | Administrative access to FS01 and BAK01 | E03 | Remote administrator logons occurred outside usual schedule. |
| FIN-USER | Finance officer user account | Finance user identity and mailbox access | E01; E02 | User opened unexpected attachment; account later signed in from unfamiliar IP/new device; user involvement/MFA unknown. |
| SUP-01 | Supporting telemetry and coordination services | Proxy/DNS/firewall, EDR, backup console, helpdesk, and incident coordination | E04; E05; E06; E07; E08 | Relevant telemetry and reports exist; normal contact list is inaccessible; corporate email trust is unverified. |

Asset impact register — confirmed and potential impact

| Asset ID | Confirmed impact | Potential security implications |
| --- | --- | --- |
| FIN-PC07 | Endpoint activity and file-change anomaly are confirmed; no confirmed malware execution or data disclosure. | Possible endpoint compromise, credential exposure, file alteration, or transfer of sensitive finance data. |
| FS01 | Shared-file and contact-list access disruption is observed; file-change indicators are observed; cause and full scope are unconfirmed. | Possible server compromise, file integrity loss, lateral movement, exposure of institutional information, and LMS01 dependency impact. |
| LMS01 | Learner-facing functions are unavailable; LMS01 encryption or data loss is not confirmed. | Possible dependency failure, altered materials, application compromise, or examination disruption. |
| BAK01 | No BAK01 outage, deletion, tampering, or compromise is confirmed. | Recovery points or configuration may be exposed, altered, deleted, or unsafe; last disconnected backup is from Day minus 3 17:00. |
| M365-ID | Anomalous sign-in and communications-trust concern are confirmed; account compromise is not. | Possible mailbox, token, MFA, forwarding-rule, consent, or credential compromise; unsafe coordination channel. |
| SVC-BACKUP | The unusual logons are confirmed; unauthorized use or account compromise is not. | Possible privileged lateral movement, file changes, backup tampering, or exposure of recovery data. |
| FIN-USER | User action and sign-in anomaly are observed; compromise is not confirmed. | Possible credential theft, mailbox access, endpoint compromise, or finance-data exposure. |
| SUP-01 | Coordination constraint is observed; telemetry or record tampering is not confirmed. | Loss or alteration of evidence, unsafe incident communications, or incomplete scope assessment. |

Asset impact register — status and verification

| Asset ID | Affected-asset status | Investigation priority | Verification requirements |
| --- | --- | --- | --- |
| FIN-PC07 | Affected for investigation; compromise not confirmed | Immediate | Preserve EDR/process/file/network telemetry; identify modifying process and uploaded content; confirm current usability. |
| FS01 | Affected asset based on observed service/file impact; root cause not confirmed | Immediate | Correlate administrator, share, file, PowerShell, EDR, and application records; inventory affected shares and dependencies. |
| LMS01 | Affected service based on observed availability impact; underlying cause not confirmed | Immediate | Run controlled functional tests; review application/database/authentication/network logs; map FS01 dependencies; validate continuity option. |
| BAK01 | Requires investigation; not confirmed affected | Immediate | Review repository access and configuration audit; preserve snapshots; identify restore points; perform isolated validation before production use. |
| M365-ID | Requires investigation; not confirmed affected | High | Review sign-in/MFA/device/token/mailbox/conditional-access audit; validate email trust; establish alternate channel. |
| SVC-BACKUP | Requires investigation; not confirmed compromised | Immediate | Identify source hosts, session type, commands, authorization, subsequent changes, and account owner; protect account under approved response decision. |
| FIN-USER | Requires investigation; not confirmed affected | High | Interview user; correlate message, attachment, endpoint, Microsoft 365, MFA, device, and account-change records. |
| SUP-01 | Supporting services require protection and validation; not confirmed compromised | High | Restrict access to records; preserve logs and provenance; use staff phones; validate approved alternate communication and record availability. |

Investigation priorities — questions

| Investigation ID | Related evidence IDs | Priority | Question |
| --- | --- | --- | --- |
| IP-01 | E01; E02 | High | Did the unexpected payroll attachment lead to activity involving the finance officer's Microsoft 365 identity or FIN-PC07? |
| IP-02 | E02; E03 | High | Were the unfamiliar Microsoft 365 sign-in and svc_backup remote logons authorized, automated, or unauthorized? |
| IP-03 | E04 | High | What process, destination account, and files generated the 1.2 GB HTTPS upload from FIN-PC07? |
| IP-04 | E03; E05; E06 | High | Did svc_backup or another actor alter, delete, encrypt, or otherwise compromise FS01 or BAK01 before or during the backup activity? |
| IP-05 | E05; E06; E07 | High | Can a selected FS01/LMS01 backup be restored in an isolated environment and verified as complete, usable, and free of relevant indicators? |
| IP-06 | E06; E07 | High | What is the confirmed extent and cause of the .locked files, ransom note, and learner-facing portal disruption? |
| IP-07 | E04; E06; E07; E08 | Medium | Could learner, finance, admission, assessment, credential, or contact-list data have been accessed or transferred? |

Investigation priorities — evidence and ownership

| Investigation ID | Responsible role | Required logs records artifacts interviews or validation procedures |
| --- | --- | --- |
| IP-01 | Security analyst with forensic support | Preserve the original message and attachment; review message trace, Microsoft 365 audit, MFA and conditional-access records, device sign-in data, EDR process tree, browser history, file metadata, and a finance officer interview. |
| IP-02 | Incident Response Lead with security analyst | Correlate Microsoft 365 sign-in/MFA/device records with Windows Security, PowerShell, task-scheduler, backup-console, VPN/firewall records, source IPs, time synchronization, administrator schedules, and interviews with the account owner and IT staff. |
| IP-03 | Forensic specialist with security analyst | Retain proxy, DNS, firewall, and cloud-provider records; inspect endpoint process/network telemetry, browser or sync-client logs, file-access history, archive creation, destination ownership, object metadata, and approved-transfer records. |
| IP-04 | Forensic specialist with IT operations support | Review Windows and backup-console audit logs, share/file events, task history, administrator commands, backup configuration and retention changes, snapshot metadata, EDR/server telemetry where available, and account activity around the event window. |
| IP-05 | IT operations lead with business owner and forensic support | Export job logs and restore-point metadata; perform a controlled restore without production connectivity; validate file integrity, application dependencies, access controls, malware indicators, and sample examination workflows; document results as a planned validation. |
| IP-06 | Security analyst with IT operations support | Preserve EDR and helpdesk records; collect file-event and filesystem metadata; review FS01 and LMS01 application/web/database logs, permissions, dependency mapping, affected-share inventory, and controlled portal tests; hunt other endpoints and servers. |
| IP-07 | Privacy/legal adviser with data owners and forensic specialist | Review data classification and locations; correlate file access, archive, proxy, cloud, Microsoft 365, FS01, and LMS01 logs; interview data owners; identify the destination account; do not infer personal-data transfer from volume alone. |

Investigation priorities — decision value and status

| Investigation ID | Expected decision value | How findings could change severity or scope assessment | Current status |
| --- | --- | --- | --- |
| IP-01 | Separates a possible initial-access sequence from unrelated user and identity anomalies and identifies what evidence must be preserved next. | Confirmed execution, credential use, persistence, or broader identity access would expand the affected scope; a verified legitimate sign-in and no related endpoint activity would reduce confidence in that link. | Not Investigated |
| IP-02 | Determines whether privileged identity activity indicates one access path or separate operational events. | Evidence of unauthorized privileged access or configuration changes affecting FS01/BAK01 would increase scope and urgency; documented authorized activity would narrow the suspected access path. | Not Investigated |
| IP-03 | Determines whether the transfer was a business operation, backup/synchronization, or possible data disclosure and identifies affected data classes if recoverable. | Evidence of learner, finance, credential, or other confidential data transfer would increase confidentiality impact and scope; a validated approved transfer with unrelated content would reduce that concern. | Not Investigated |
| IP-04 | Tests whether the backup repository and recovery points can be trusted and whether lateral movement reached privileged infrastructure. | Confirmed backup deletion, tampering, encryption, or credential misuse would broaden affected assets and make recovery risk more severe; clean, authorized administration would narrow the hypothesis. | Not Investigated |
| IP-05 | Provides evidence for safe recovery planning while preserving separation between reported backup success and verified recoverability. | A successful clean restore could support a bounded recovery option; restore failure, corruption, or compromise would extend availability impact and increase scope to backup/recovery systems. | Not Investigated |
| IP-06 | Separates confirmed service impact from assumed encryption and identifies whether the examination workflow can be safely supported. | Broader encryption or persistence across servers, LMS01, or endpoints would expand scope; a localized access/configuration issue would narrow the event while still requiring service recovery. | Not Investigated |
| IP-07 | Supports a fact-based confidentiality and notification assessment without turning an unverified claim into a finding. | Evidence of access or transfer of personal data would increase confidentiality scope and require escalation for legal/privacy assessment; absence of evidence would not prove no access but may bound the current assessment. | Not Investigated |
