# Day 26 — SOC Documentation & Investigation Templates

## 1. Overview

SOC analysts do not only investigate alerts; they must also document their findings clearly.

SOC templates provide a standardized structure for recording incidents, evidence, actions, escalation details, and handovers.

Good documentation helps a SOC team:
- Track incidents consistently
- Preserve important evidence
- Communicate findings clearly
- Support escalation to L2/L3 or Incident Response teams
- Maintain an audit trail
- Continue investigations smoothly across shifts

---

## 2. Types of SOC Templates

Common SOC templates include:

1. Alert Triage Template
2. Incident Response Template
3. Case Management Template
4. Communication Template
5. Escalation Template
6. SOC Handover Template
7. Phishing Analysis Template
8. Malware Analysis Template
9. Evidence Checklist

---

## 3. Alert Triage Template

An Alert Triage Template records the initial investigation of a security alert.

### Typical information:

- Alert ID
- Alert name/type
- Timestamp
- Source
- Affected user/host/IP
- Initial severity
- Evidence collected
- Investigation findings
- False Positive / True Positive
- Recommended action
- Escalation requirement
- Analyst notes

### Purpose

It helps the analyst decide whether an alert should be:

- Closed
- Monitored
- Investigated further
- Escalated

---

## 4. Incident Response Template

An Incident Response (IR) Template documents the complete incident.

### Important sections:

1. Executive Summary
2. Incident Details
3. Detection Information
4. Affected Systems
5. Indicators of Compromise (IOCs)
6. Timeline
7. Root Cause
8. Containment Actions
9. Eradication Actions
10. Recovery Actions
11. Lessons Learned
12. Recommendations

### Example

Incident: Phishing Attack

Initial Event:
A user received a phishing email and clicked a malicious link.

Possible actions:

- Block malicious domain
- Secure the affected account
- Check endpoint logs
- Search for related activity
- Collect IOCs
- Escalate if compromise is suspected

---

## 5. Case Management Template

A Case Management Template helps track an investigation from creation to closure.

### Typical fields:

- Case ID
- Case Title
- Description
- Priority/Severity
- Assigned Analyst
- Related Alerts
- Evidence
- Investigation Notes
- Actions Taken
- Status
- Escalation Details
- Closure Reason

A case should contain enough information for another analyst to understand the investigation without repeating the entire process.

---

## 6. Communication Template

Communication templates standardize messages sent to relevant teams.

A good security communication should include:

- What happened
- When it happened
- Affected asset/user
- Current impact
- Evidence/findings
- Actions already taken
- Required action
- Severity
- Contact/escalation information

Communication should be:

**Clear + Concise + Factual + Professional**

---

## 7. Escalation Template

Escalation is required when an analyst cannot safely close an alert or when deeper investigation is required.

### Escalation should include:

1. Incident Summary
2. Evidence Collected
3. Indicators of Compromise
4. Affected Systems/Users
5. Actions Already Performed
6. Current Severity
7. Reason for Escalation
8. Recommended Next Steps

### Important Principle

Do not escalate an incident by simply saying:

"This looks suspicious."

Instead, provide evidence and explain why it is suspicious.

---

## 8. SOC Handover Template

A SOC handover transfers important information from one SOC shift to another.

### Include:

- Critical/active incidents
- Pending investigations
- Alerts requiring follow-up
- Actions already completed
- Actions still pending
- Assigned analyst/team
- Important IOCs
- Deadlines
- Relevant case/ticket IDs

### Example

Incident:
Suspicious PowerShell Execution

Status:
Investigation ongoing

Actions completed:
Endpoint isolated and user contacted.

Pending:
Review additional endpoint logs.

Next Action:
Continue investigation and update the case.

### Importance

A proper handover prevents:

- Missed actions
- Duplicate investigation
- Loss of investigation context

---

## 9. Phishing Analysis Template

A phishing investigation can document:

1. Email Content Summary
2. Sender Information
3. Recipient
4. Subject
5. URLs
6. Attachments
7. Email/Header Analysis
8. Domain/IP Reputation
9. Authentication Results
10. User Interaction
11. Indicators of Compromise
12. Final Verdict
13. Recommended Actions

### Possible Verdicts

- Benign
- Spam
- Suspicious
- Malicious
- Confirmed Phishing

---

## 10. Malware Analysis Template

A Malware Analysis Template may contain:

1. File Name and Hash
2. File Type
3. Source
4. Detection Information
5. Static Analysis Findings
6. Dynamic Analysis Findings
7. Network Indicators
8. Persistence Indicators
9. Behavioral Observations
10. IOCs
11. Severity
12. Recommended Actions
13. Final Classification

---

## 11. Evidence Checklist

Before closing or escalating a case, verify that important evidence has been collected.

### Checklist:

- Alert details logged
- Relevant screenshots attached
- Logs collected
- IP/domain/hash recorded
- User/host information recorded
- Timeline created
- Investigation notes updated
- Actions documented
- Escalation documented if required
- Ticket/case status updated

---

## 12. Why Documentation Matters in a SOC

Documentation helps with:

- Incident tracking
- Knowledge sharing
- Shift handovers
- Auditing
- Compliance
- Incident reconstruction
- Root-cause analysis
- Future threat detection

### Key Rule

**If it is not documented, it is difficult to prove that it was investigated or handled correctly.**

---

## 13. SOC Documentation Flow

Alert Generated
        ↓
Initial Triage
        ↓
Create/Update Case
        ↓
Collect Evidence
        ↓
Analyze & Validate
        ↓
Document Findings
        ↓
Close OR Escalate
        ↓
Update Incident Record
        ↓
Handover if Still Active