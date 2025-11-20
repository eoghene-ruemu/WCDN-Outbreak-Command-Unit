# Methodology  
## Outbreak Triage Workflow — WCDN Outbreak Command Unit

As the Outbreak Triage Specialist for the Wakanda Cyber Defense Network (WCDN), my primary responsibility was to evaluate incoming alerts, classify severity, and ensure proper escalation to Threat Hunters, Containment teams, or Command Ops. The methodology below outlines the structured process used throughout the SOC/SIEM outbreak simulation.

---

## 1. Alert Intake  
All alerts were monitored through AWS-native tooling including:
- GuardDuty findings  
- Security Hub aggregated findings  
- CloudTrail event anomalies  
- VPC Flow Log indicators (if applicable)  

Each alert was reviewed immediately upon detection.

---

## 2. Initial Analysis  
For every incoming alert or system error:
- Identified the affected service (SNS, Athena, Config, CloudTrail, IAM, etc.)  
- Reviewed available log evidence  
- Determined whether the alert represented a threat, misconfiguration, or visibility blocker  

This ensured accurate triage and prevented misclassification.

---

## 3. Severity Classification  
Each alert was classified using the WCDN Outbreak Severity Matrix:

### **Urgent**
Active threat indicators such as credential compromise, privilege escalation attempts, or malicious network activity.

### **High**
Potentially dangerous activity including brute-force attempts, suspicious API calls, or reconnaissance behaviors.

### **Medium**
Failures that blocked SOC workflows (e.g., missing permissions, AWS Config recorder issues, Athena query failures), impacting visibility but not representing active threats.

### **Low**
Benign or informational findings requiring monitoring but no immediate action.

Severity informed the escalation path and response time.

---

## 4. Ticket Creation & Documentation  
Each event was documented as a ticket with:
- Summary of issue  
- Evidence (GuardDuty logs, error messages, screenshots)  
- Severity classification  
- Recommended next steps  

These tickets were then escalated to the SOC Lead or the appropriate response team.

---

## 5. Escalation Workflow  
Depending on severity:

- **Urgent / High** → Escalated immediately to Threat Hunters and Command Ops  
- **Medium** → Routed to SOC Lead with remediation request  
- **Low** → Logged for visibility and monitoring  

Clear communication ensured that incidents were not blocked or delayed.

---

## 6. Evidence Collection  
For each ticket:
- Captured screenshots of findings  
- Included JSON policy examples when permissions were missing  
- Recorded relevant CloudTrail or GuardDuty snippets  
- Attached all material for upstream analysis  

This enabled efficient downstream investigation.

---

## 7. Continuous Status Reporting  
Throughout each sprint:
- Provided updates to the SOC Lead  
- Reported blockers related to IAM, Config, Athena, or SNS  
- Verified when fixes were implemented  
- Re-tested workflows after permissions were updated  

---

## 8. Verification & Closure  
Once escalated tasks were resolved:
- Re-tested the affected service  
- Verified that SOC capabilities were restored (SNS alerts, Config recording, Athena queries, etc.)  
- Closed the ticket with final notes  

---

## Summary  
This methodology reflects a structured, reliable outbreak triage workflow designed to ensure rapid classification, accurate escalation, strong communication, and complete evidence gathering throughout the SOC/SIEM simulation.
