# Task 6 — Case Study Analysis and Critical Reflection

> Extracted from the complete ICDFA GRC105 assignment. Content is organised by task; tables and source terminology are retained as Markdown where possible.

## 8	Task 6 — Case Study Analysis and Critical Reflection

The illustrative healthcare case on Week 20 slide 16 shows several response strengths. First, EDR alerts triggered detection and the incident-response team activated immediately, reducing the time between discovery and coordinated action. Second, network segmentation and quarantine limited the ransomware spread while affected systems were isolated. Third, offline backups were verified intact, enabling recovery without paying a ransom. The case also describes forensic analysis, phased rebuilding, strengthened controls, sector information sharing and a later lessons-learned review. These are mutually reinforcing preparation and response practices rather than isolated technical fixes.

Two limitations remain. The case reports that no patient-data exfiltration was confirmed, but it does not explain the complete scope of email, endpoint, identity, network and cloud-log review that supports that conclusion. “Not confirmed” is therefore not proof that no access occurred. It also reports critical-system restoration within 72 hours but full downtime of seven days; the distinction is useful, yet the case does not identify the recovery dependencies or business services that remained unavailable during the additional four days.

Two improvements transfer directly to Northbridge. Northbridge should protect and test offline or isolated backups because its network backups are not immutable, the last disconnected copy is from Day minus 3, and restoration has not been tested in 90 days. It should also strengthen segmentation and server monitoring around FS01, LMS01 and BAK01 because server EDR coverage is incomplete and LMS01 depends on FS01. These changes address the case lessons while responding to Northbridge-specific uncertainty rather than assuming the same outcome.

Restoring critical systems within 72 hours is a service-priority milestone, not full recovery. Critical clinical functions may be restored first while identity, peripheral services, records reconciliation, monitoring, user support and less-critical systems continue recovery over seven days. Before claiming that no patient data was stolen, investigators would need preserved identity, endpoint, email, network, proxy, cloud and application logs; evidence of access and transfer review; validated retention and time coverage; scope analysis; and documented privacy/legal assessment. Absence of an alert alone is insufficient.

Following the tabletop, I would revise Northbridge’s examination decision: the 11:00 examination should not be treated as a reason to reopen LMS01 from an unvalidated backup. The plan should require an early documented alternative-arrangement decision while isolated recovery and security validation continue. This preserves availability planning without converting schedule pressure into unsafe restoration.

Source: ICDFA, Incident Response Planning, Week 20 teaching presentation, slide 16. The Northbridge transfer is analytical interpretation, not a finding from the healthcare case.

## 9	References

ICDFA. GRC105 Incident Response Planning Assignment. Supplied course document, pp. 1–6.

ICDFA. Incident Response Planning. GRC105 Week 20 teaching presentation, slides 1–18. Supplied course presentation.

Nelson, A., Rekhi, S., Souppaya, M., and Scarfone, K. (2025). NIST SP 800-61 Revision 3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management: A CSF 2.0 Community Profile. https://csrc.nist.gov/pubs/sp/800/61/r3/final

Cichonski, P., Millar, T., Grance, T., and Scarfone, K. (2012). NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response. https://csrc.nist.gov/pubs/sp/800/86/final

CISA and partners. #StopRansomware Guide. https://www.cisa.gov/stopransomware/ransomware-guide

The report uses the supplied assignment and Week 20 slides as the scenario and marking sources. NIST SP 800-61 Revision 3 is used for CSF 2.0-aligned incident-response governance; the Week 20 four-stage teaching model is retained as a course-facing organisation aid and is not attributed to Revision 3 as its lifecycle.

## 10	AI-assistance acknowledgement

AI assistance was used transparently for document preparation, technical structuring, evidence-register presentation, visual conversion support, cross-artifact consistency checks and quality assurance. The student remains responsible for reviewing, validating and explaining the report, its evidence interpretations, citations and final submission.
