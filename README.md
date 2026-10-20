Incident Response Planning and Simulation Lab
Course: ICDFA GRC105 --- Incident Management and Business
Continuity, Week 20
Case study: Northbridge Skills Institute --- Suspected Ransomware
Incident
Lab type: Six-task incident response planning and tabletop
simulation
Scenario status: Fictional academic exercise. No live incident
response, system restoration, notification, or team exercise was
performed.

Table of Contents
- Project Overview
- Scenario and Environment
- Lab Objectives
- Methodology and Framework
  Alignment
- Task 1 --- Detection, Classification, and Initial
  Assessment
- Task 2 --- Policy, CSIRT, RACI, and
  Readiness
- Task 3 --- First 24-Hour Playbook and
  Recovery
- Task 4 --- Communication and
  Escalation
- Task 5 --- Tabletop Exercise and Improvement
  Plan
- Task 6 --- Healthcare Ransomware Case Study and
  Reflection
- Key Findings
- Lessons Learned
- Practical Relevance
- Limitations and Assumptions
- References
- Source Document
Project Overview
This portfolio lab develops an incident response approach for a
fictional education provider experiencing a suspected ransomware
incident. It follows the six tasks in the submitted GRC105 assignment:
initial detection and assessment; incident response policy and team
readiness; a first-24-hour response playbook; communication and
escalation; a tabletop exercise and improvement plan; and analysis of a
healthcare ransomware case.

The work focuses on evidence-based decisions under uncertainty. It
distinguishes observed indicators from hypotheses, prioritises
containment and evidence preservation, protects backup recovery paths,
and prevents pressure to restore a service quickly from overriding
security and integrity checks.

The exercise is a planning document and written simulation. Proposed
actions and tabletop results are not evidence of a live investigation,
actual technical restoration, formal notification, or an operational
team exercise.
Scenario and Environment
Northbridge Skills Institute is a fictional education provider with
1,800 learners and 90 staff. One hundred learners are scheduled for
an online examination at 11:00 WAT on Day 0 (Monday). At 08:45 WAT,
the Incident Response Lead assumes control of a suspected critical
incident.
  Evidence          Time              Observation       Interpretation
                                                        and uncertainty
  E01               Day −1, 16:40     A finance officer Possible phishing
                                      opened an         entry point;
                                      unexpected        malicious
                                      payroll           execution is not
                                      attachment on     confirmed.
                                      FIN-PC07.       

  E02               Day 0, 01:15      Microsoft 365     Possible account
                                      finance login     misuse; MFA and
                                      from an           user confirmation
                                      unfamiliar IP/new remain
                                      device.           outstanding.

  E03               Day 0, 01:35      Unusual           Possible lateral
                                      svc_backup      movement, but
                                      remote            legitimate
                                      administrator     administration
                                      logons to FS01  has not been
                                      and BAK01.      ruled out.

  E04               Day 0, 01:50      FIN-PC07 sent   Potential
                                      1.2 GB over HTTPS exfiltration;
                                      to unfamiliar     transfer contents
                                      cloud storage.    and legitimacy
                                                        are unknown.

  E05               Day 0, 02:00      Backup jobs for   Job success does
                                      FS01/LMS01    not prove
                                      reported success. integrity or
                                                        recoverability.

  E06               Day 0, 08:30      Mass file changes Strong ransomware
                                      on FIN-PC07;    indicators;
                                      .locked files   malware family is
                                      and a ransom note unknown.
                                      on FS01.        

  E07               Day 0, 08:40      LMS login page    Learning service
                                      loads, but users  disruption is
                                      cannot access     observed;
                                      materials or      compromise of
                                      submit            LMS01 is not
                                      assessments.      established.

  E08               Day 0, 08:45      Contact list on   Use verified
                                      FS01 is         phones and
                                      unavailable and   alternative
                                      corporate email   secure
                                      trust is          communication
                                  uncertain.        channels.
The scenario does not establish attacker identity, malware family,
confirmed personal-data theft, or the full scope of compromise. Those
questions require evidence and continued analysis.
Lab Objectives
- Classify the incident using evidence and business impact.
- Identify critical assets, confidentiality/integrity/availability
  concerns, and investigative gaps.
- Define response authority, team responsibilities, and readiness
  controls.
- Build a timed playbook coordinating containment, forensic
  preservation, and safe recovery.
- Establish communications and escalation rules if normal email or
  shared contact records are untrusted.
- Evaluate decisions through a tabletop simulation and assign
  measurable corrective actions.
- Apply lessons from a healthcare ransomware case without overstating
  what its evidence proves.
Methodology and Framework Alignment
Four-stage teaching model
The assignment uses the four-stage model presented in the ICDFA teaching
material: 1. Preparation --- policy, team roles, readiness, contact
routes, and backup preparation. 2. Detection and analysis --- review
indicators, classify severity, assess impact, and identify evidence
gaps. 3. Containment, eradication, and recovery --- isolate affected
assets, protect backups, investigate scope, rebuild from trusted
sources, and validate services. 4. Post-incident activity --- review
decisions, record lessons, assign corrective actions, and verify
closure.

This four-stage sequence is attributed to the ICDFA teaching model, not
presented as the structure of NIST SP 800-61 Revision 3.
NIST SP 800-61 Revision 3 and CSF 2.0
The assignment explains the NIST CSF 2.0 alignment used in SP 800-61
Revision 3: Detect, Respond, and Recover are core incident response
functions, supported by Govern, Identify, and Protect. Continuous
improvement feeds lessons back across the functions.
Other guidance
- CISA and partners, #StopRansomware Guide: informs ransomware
  containment, trusted backups, and recovery decisions.
- Nigeria Data Protection Act 2023: considered conditionally in
  the legal discussion. Nigeria is an assumed jurisdiction for that
  discussion, not a fact established by the fictional scenario.
- Evidence handling: planned collections record time, collector,
  source, method, SHA-256 hash after acquisition, encrypted storage,
  and custody transfers. No hashes are invented and evidence is not
  described as collected unless collection is confirmed.
These are educational alignments; they do not imply certification,
formal compliance, or a completed operational assessment.
Task 1 --- Detection, Classification, and Initial Assessment
Approach
The E01--E08 timeline separates observed facts from working
interpretations and uncertainty. The initial classification is
Critical / Severity 1 because of encryption indicators, loss of
shared resources, examination disruption, privileged-account anomalies,
and uncertain backup trust.
Assets and impact
  Asset or service        Main concern            Initial response
                                                  priority
  FS01 shared server    Files appear encrypted  Contain and
                          or altered; learner and investigate; preserve
                          financial records may   evidence and plan clean
                          be exposed.             recovery.

  LMS01 learning portal Learners cannot access  Validate service and
                          materials or submit     dependencies before
                          assessments; assessment reopening.
                          integrity must be
                          protected.              

  FIN-PC07              Mass file changes and   Isolate and
                          unexplained 1.2 GB      investigate.
                          transfer.               

  BAK01 / svc_backup  Privileged access may   Protect backup path and
                          affect backup trust.    investigate access.

  Microsoft 365           Unfamiliar sign-in      Review sessions, MFA,
                          needs validation.       device, and sign-in
                                              records.
Investigative questions
The plan calls for checking endpoint execution and file-modification
history; Microsoft 365 sign-in and MFA records; privileged logons and
change records; proxy, DNS, firewall, and transfer metadata; backup
repository integrity; and the scope of affected hosts and accounts.

Outcome: The incident is treated as urgent without asserting that
data theft, attacker identity, or a specific malware family has been
proven. Severity is reassessed as evidence changes.
Task 2 --- Policy, CSIRT, RACI, and Readiness
Policy and authority
The proposed policy aims to protect learners, staff, data, and essential
academic services through timely, evidence-based response. It covers
endpoints, servers, cloud identity, learning services, backups, third
parties, and personnel.

The incident is logged as NSI-IR-001. The Incident Response Lead may
declare a Critical incident, activate the CSIRT, coordinate containment,
and direct evidence preservation. IT may immediately disconnect a
clearly compromised endpoint during an emergency, recording the action
and notifying the lead. Restoration of critical academic services
requires Director approval informed by technical and academic sign-off.
CSIRT roles
  Role                                Responsibility
  Incident Response Lead (IRL)        Coordinates response, severity,
                                      decisions, escalation, and review.

  Security Analyst (SA)               Reviews alerts, identity records,
                                      network evidence, and scope.

  Digital Forensics Specialist (DF)   Preserves and analyses forensic
                                      artefacts.

  IT Operations Lead (IT)             Executes containment, access
                                      changes, backup validation, and
                                      recovery tasks.

  Academic Operations Lead (AO)       Assesses examination impact and
                                      accepts academic service
                                      arrangements.

  Legal/Privacy Adviser (LP)          Assesses legal obligations and
                                      potential personal-data exposure.

  Communications Officer (CO)         Issues approved stakeholder
                                      communications.

  Institute Director (DIR)            Makes major business decisions and
                                      approves critical service
                                  restoration.
RACI summary
  Activity                     Accountable   Responsible
  Detection and triage         IRL           SA, IT
  Technical analysis           IRL           SA, DF
  Containment                  IRL           SA, IT
  Evidence handling            IRL           SA, DF
  Stakeholder communications   IRL           CO
  Regulatory obligations       LP            LP
  Restoration approval         DIR           IT, AO
  Closure and review           IRL           IRL, SA, IT
Readiness gaps and controls
- Backup trust: introduce protected/offline backups and quarterly
  isolated restoration tests.
- Incomplete server EDR: improve monitoring coverage and verify it
  with a coverage report and alert test.
- Contact dependency on FS01: maintain encrypted offline contact
  copies and test the call tree quarterly.
- Broad svc_backup privileges: review permissions, apply least
  privilege and privileged-access controls, and test login alerts.
- Limited internal capacity: consider an external
  incident-response/forensics retainer.
- Stale restoration assurance: document restore-test outcomes and
  track corrective actions.
Task 3 --- First 24-Hour Playbook and Recovery
First 60 minutes: 08:45--09:45 WAT
  Time window             Action                  Owner / completion
                                                  evidence
  08:45--08:50            Declare Severity 1,     IRL; incident log and
                          activate CSIRT, open    role acknowledgements.
                          NSI-IR-001.           

  08:50--08:55            Use verified phone      IRL/CO; recipient and
                          tree; avoid untrusted   channel log.
                          email for incident
                          coordination.           

  08:50--09:05            Isolate FIN-PC07,     IT; isolation
                          preserving volatile     verification and host
                          evidence where          notes.
                          feasible.               

  08:55--09:10            Contain FS01 and      IT; logs and
                          identify affected       connectivity checks.
                          shares.                 

  09:00--09:15            Protect BAK01; review IT/SA; access logs and
                          and restrict suspicious session review.
                          svc_backup sessions.  

  09:05--09:20            Review Microsoft 365    SA; exported
                          sign-ins and sessions.  sign-in/MFA records and
                                                  account status.

  09:10--09:30            Preserve ransom note,   DF/SA; chain-of-custody
                          alerts, file metadata,  records.
                          and relevant logs.      

  09:20--09:35            Examine transfer        SA/LP; evidence
                          metadata for E04;       register and assessment
                          request legal/privacy   request.
                          assessment.             

  09:25--09:40            Assess LMS impact and   AO; decision options
                          prepare examination     and learner plan.
                          contingency.            

  09:40--09:45            Brief the Director on   IRL; approved briefing
                          impact, uncertainty,    and next update.
                      and decisions.          
Remainder of the first 24 hours
- Scope affected endpoints, privileged accounts, lateral movement, and
  the E04 transfer.
- Decide whether to postpone the examination unless an independently
  verified safe alternative exists.
- Validate backup copies in an isolated environment, including the
  disconnected Day −3 backup; preserve originals.
- Plan eradication through trusted rebuilds, patching, token
  revocation, and credential rotation.
- Restore essential identity and monitoring, FS01, and LMS01 in
  stages only after validation.
- Continue monitoring, reassess scope, and produce a next-day recovery
  plan.
Proposed recovery targets
These are planning assumptions, not proven commitments.
  Service                 Proposed RTO         Proposed RPO Release
                                                            condition
  FS01 shared               12 hours              4 hours Isolated
  server                                                    restoration,
                                                            malware checks,
                                                            integrity
                                                            validation,
                                                            owner sign-off.

  LMS01                      8 hours              4 hours Dependencies
  learning portal                                           verified, safe
                                                            submissions
                                                            confirmed, AO
                                                            sign-off.

  Finance                     24 hours             24 hours Trusted rebuild
  workstation                                               and user
                                                            validation.

  Trusted backup  8 hours to establish       Not applicable Successful
  recovery path                                             isolated restore
                                                            test and no
                                                            evidence of
                                                            repository
                                                            contamination.

  Identity and      As early as safely        Not specified Known-good
  monitoring                  possible                      identity state,
                                                            monitoring, and
                                                            account
                                                        controls.
The disconnected Day −3 backup is approximately 63 hours 45 minutes
old at 08:45 WAT. It cannot satisfy a four-hour RPO by itself. No
service should return to production solely to meet the examination
deadline.
Evidence register
Planned evidence sources include FIN-PC07 telemetry and disk/memory
where feasible; FS01 ransom note and server logs; Microsoft 365
sign-in and MFA records; proxy/firewall/DNS/transfer logs;
FS01/BAK01 privileged-access logs; and backup job/repository/restore
logs. These are planned collections, not completed acquisitions.
Task 4 --- Communication and Escalation
Communication matrix
  Stakeholder    Trigger         Owner          Channel          Cadence
  Director /     Severity 1 or   IRL            Secure briefing  Hourly
  management     major decision                 / verified phone initially

  IT / security  Activation or   IRL            Approved bridge  Continuous;
                 new finding                    / verified phone 30-minute
                                                                 check-ins

  Learners       Portal          CO             Verified         On decision
                 disruption or                  website/portal / and change
                 exam decision                  SMS              

  Academic staff Exam or         AO             Staff platform / On activation
                 assessment                     phone tree       and changes
                 impact                                          

  Service        Specialist      IT             Verified         As needed
  provider       support                        provider portal
                 required                       / emergency
                                                phone            

  Legal /        Possible        IRL            Secure channel / Immediately
  privacy        personal-data                  verified phone   and on
                 exposure                                        material
                                                                 changes

  Employees      Operational     CO             Staff platform / Initial and
                 restrictions                   SMS              material
                                                                 changes

  Regulator, if  Legally         LP             Official portal  Applicable
  required       reportable                     / designated     statutory
             breach                         secure channel   schedule
Learner notice (draft)
Dear Learners, we are currently experiencing a technical disruption
affecting access to learning materials and assessment submissions on
the Northbridge Skills Institute portal. Our technical team is working
to restore services safely. Due to this disruption, the online
examination scheduled for 11:00 today has been postponed until further
notice. A revised examination schedule will be shared through verified
official channels once confirmed. Please do not attempt repeated
submissions or use unofficial links claiming to provide alternative
examination access. You do not need to take any further action at this
stage. We understand the inconvenience and appreciate your patience.
Please watch for updates on the official website or by SMS.
Academic Operations Team, Northbridge Skills Institute

This notice is a draft and should be issued only after postponement
approval.
Escalation and legal assessment
Continuing compromise, possible privileged-account misuse, or possible
exfiltration is escalated immediately to the IRL and Legal/Privacy
Adviser. Legal/Privacy must establish jurisdiction, controller/processor
status, affected data, risk, recipients, and deadlines. A routine
service notice is not treated as a formal personal-data breach
notification.

The assignment discusses the Nigeria Data Protection Act 2023 only on
the assumption that Nigerian law applies. The scenario itself does not
specify jurisdiction; applicability and the notification clock must be
assessed by Legal/Privacy based on the facts of a qualifying breach.
Task 5 --- Tabletop Exercise and Improvement Plan
Exercise design
The exercise is a 60-minute individual role-play simulation, with
the student simulating the IRL, SA, DF, IT, AO, LP, CO, and DIR. It is
not a live team drill or technical recovery test.
  Time                    Inject                  Simulated response
  0--10 min               Brief roles, facts, and IRL activates the
                          Severity 1 status.      response and confirms
                                                  role ownership.

  10--20 min              Management demands LMS  IT/SA advise against
                          reopening before the    unsafe restoration; DIR
                          exam despite unverified considers postponement.
                          backups.                

  20--35 min              Attacker claims 1,800   Preserve the claim,
                          records and threatens   investigate E04, and
                          publication in 12       involve Legal/Privacy.
                          hours; screenshot is
                          unverified.             

  35--45 min              Latest network backup   Preserve the error and
                          test fails due to an    test a protected
                          unreadable snapshot.    offline copy in
                                                  isolation.

  45--50 min              Social media says the   CO/AO issue approved
                          exam is cancelled;      status without
                          journalist asks about   asserting unverified
                          exposure.               data theft.

  50--55 min              svc_backup attempts   Restrict sessions,
                          another administrative  examine privileged
                          login to BAK01.       accounts, and reassess
                                                  scope.

  55--60 min              Debrief and assign      IRL documents gaps,
                      actions.                owners, and follow-up.
Evaluation
The written role-play addressed six criteria: escalation within 10
minutes, decisions within five minutes of each inject, no unverified
restoration, approved communications, privacy/evidence escalation, and a
safe examination alternative. This is a self-assessment of written
decisions, not measured staff performance.
Corrective actions
  Priority       Action                        Owner          Target         Completion
                                                                             evidence
  Critical       Protected/immutable backup    IT             30 days        Configuration
                 and quarterly restore tests                                 and successful
                                                                             isolated
                                                                             restore report

  Critical       Privileged access review and  IT             14 days        Reviewed
                 monitoring                                                  permissions,
                                                                             alert test, and
                                                                             credential
                                                                             controls

  High           Breach                        LP             21 days        Approved
                 assessment/notification                                     procedure and
                 procedure                                                   assessment
                                                                             template

  High           Emergency communication       CO             14 days        Approved
                 templates and channel test                                  templates and
                                                                             documented test

  High           EDR/monitoring on critical    SA             30 days        Coverage report
                 servers                                                     and alert test

  High           Offline incident contact list IRL            7 days         Verified copy
                                                                             and call-tree
                                                                             test

  Medium         External                      DIR            45 days        Signed
                 incident-response/forensics                                 agreement and
                 retainer                                                    tested contacts

  Medium         Role-specific exercise and    IRL            60 days        Attendance,
                 training programme                                          debrief, and
                                                                         tracked actions
The written tabletop review is due within five working days. For a real
incident, the assignment proposes a formal post-incident review within
ten working days of stabilisation. The IRL verifies evidence and tracks
closure; the Director oversees critical actions.
Task 6 --- Healthcare Ransomware Case Study and Reflection
The teaching case describes a healthcare organisation with 2,500
employees compromised through a phishing attachment. A Ryuk variant
persisted and moved laterally for about 72 hours before encryption. The
slide reports that EDR alerts triggered on Day 4, critical systems were
restored within 72 hours, and full restoration took seven days.
Three response strengths
1. Rapid team activation after detection supported coordinated
   response decisions.
2. Isolation of affected systems and network segments helped
   contain spread.
3. Verified offline backups enabled recovery without paying the
   ransom.
Two limitations or unresolved issues
1. The malware remained undetected for approximately three days,
   showing a detection gap.
2. The slide reports that no patient data exfiltration was confirmed
   but does not detail the evidence or limitations behind that
   conclusion.
A defensible assessment of potential data theft would examine
endpoint/server forensic records, database access logs,
proxy/firewall/DNS and cloud transfer records, unusual outbound traffic,
and missing logging. Incomplete visibility may prevent an absolute
conclusion that no data was stolen.
Critical restoration versus full restoration
Restoring critical systems within 72 hours means priority services were
returned first. Full restoration over seven days includes remaining
systems, data validation, security hardening, testing, and operational
handover. These are different milestones.
Lessons transferred to Northbridge
- Test protected offline backups routinely; Northbridge's recovery
  routes had not been tested in 90 days, and a tabletop inject made
  the latest network snapshot unreadable.
- Improve network segmentation and server monitoring to detect lateral
  movement earlier and reduce spread.
- Revise the backup fallback decision after the tabletop: protect the
  original, assess compromise indicators, and test a copy in an
  isolated environment rather than assuming the disconnected backup is
  clean.
Key Findings
- Severity: The evidence supports an initial Critical / Severity 1
  classification, while important facts remain unverified.
- Availability and integrity: The learning service is unavailable
  and shared files show ransomware indicators; service restoration
  must include integrity checks.
- Backup uncertainty: Successful job status does not prove that a
  backup is safe or usable.
- Privileged access: Unusual svc_backup activity makes the
  backup environment a priority for investigation and protection.
- Data exposure: The 1.2 GB transfer is suspicious but does not
  prove that personal data was stolen.
- Business pressure: The 11:00 examination creates urgency, but an
  unverified LMS must not be reopened just to meet the schedule.
- Resilience gaps: Offline contacts, server monitoring,
  independent backups, restoration testing, and specialist support
  need improvement.
- Governance: Decisions, evidence custody, legal assessment,
  communications, and action closure need clear owners and records.
Lessons Learned
1. Separate facts from hypotheses and revisit severity as evidence
   changes.
2. Contain likely affected assets quickly while preserving evidence
   where feasible.
3. Protect backup systems and privileged credentials before starting
   recovery.
4. Gate recovery on a trusted source, isolated restoration, security
   checks, data integrity, and business acceptance.
5. Prepare offline contact methods because normal email and contact
   records may be untrusted.
6. Agree in advance who can postpone an examination, approve
   restoration, and issue communications.
7. Use exercises to expose gaps and assign measurable corrective
   actions with owners and deadlines.
8. State evidence limitations clearly, especially when assessing
   possible exfiltration.
Practical Relevance
The lab demonstrates GRC and incident-response skills relevant to
organisations that depend on shared infrastructure and time-sensitive
services: - incident severity classification and evidence-based
triage; - CSIRT design, role clarity, and RACI assignment; - containment
and recovery planning under time pressure; - evidence register and
chain-of-custody planning; - backup assurance and restoration gates; -
stakeholder communications and legal/privacy escalation; - tabletop
exercise design, evaluation, and corrective-action tracking.

The scenario is fictional, but the methods provide a structured way to
reason about incident response without confusing a proposed plan with
proven operational capability.
Limitations and Assumptions
- All Northbridge names, evidence IDs, timestamps, and response
  decisions are fictional.
- The suspected entry point, attacker identity, malware family, full
  scope, and data-theft question remain unconfirmed.
- Recovery targets are proposed planning assumptions, not measured
  commitments.
- Evidence collections, restoration tests, communications, and
  tabletop outcomes are described as planned or simulated where
  applicable.
- The legal discussion assumes Nigeria only conditionally;
  jurisdiction is not specified in the case.
- The healthcare ransomware case is summarised as presented in the
  ICDFA teaching slide; the slide does not provide detailed forensic
  evidence for its statement about patient-data exfiltration.
References
1. Cybersecurity and Infrastructure Security Agency, Federal Bureau of
   Investigation, Multi-State Information Sharing and Analysis Center,
   & National Security Agency. (2023). #StopRansomware guide.
   https://www.cisa.gov/resources-tools/resources/stopransomware-guide
2. Federal Republic of Nigeria. (2023). Nigeria Data Protection Act,
   2023 (section 40).
   https://ndpc.gov.ng/wp-content/uploads/2024/03/Nigeria_Data_Protection_Act_2023.pdf
3. International Cybersecurity and Digital Forensics Academy. (n.d.).
   Incident response planning (GRC105, Week 20, slides 1--18)
   \(Teaching slides\).
4. Nelson, A., Rekhi, S., Souppaya, M., & Scarfone, K. (2025).
   Incident response recommendations and considerations for
   cybersecurity risk management: A CSF 2.0 community profile (NIST SP
   800-61 Rev. 3). National Institute of Standards and Technology.
   https://doi.org/10.6028/NIST.SP.800-61r3
