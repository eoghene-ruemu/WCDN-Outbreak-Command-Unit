# Findings  
## Outbreak Ticket Summary — WCDN Outbreak Command Unit

This document contains a summary of all identified issues, alerts, and blockers triaged during the Outbreak Command Unit SOC/SIEM simulation. Each ticket includes the severity classification, impact, and escalation actions taken. Screenshots of all tickets are located in `documentation/screenshots/`.

---

## Ticket 01 – Medium Severity  
### **SNS Topic Creation Failure (Notification Workflow Blocker)**  
While configuring the Sprint 3 Notification Workflow, an SNS topic could not be created due to missing permissions for the SOC Analyst role.  
**Impact:** SOC alerts could not be published from the CAL-3 ViroShield Lambda.  
**Action Taken:** Escalated to SOC Lead for topic creation and sns:Publish permission updates.  
(Screenshot: Ticket-01-SNS-AccessDenied.png)

---

## Ticket 02 – Medium Severity  
### **Athena Query Write Failure (Central Logging Blocker)**  
Athena queries in the Archive Ward account failed due to insufficient S3 permissions on the central logs bucket.  
**Impact:** Threat hunting and log correlation workflows were blocked.  
**Action Taken:** Escalated to SOC Lead with recommended IAM policy to enable s3:PutObject and s3:GetObject permissions.  
(Screenshot: Ticket-02-Athena-AccessDenied.png)

---

## Ticket 03 – Medium–High Severity  
### **AWS Config Recorder Start Failure (Compliance Blindspot)**  
Attempt to start the AWS Config recorder failed due to missing permissions in the Containment Lab account.  
**Impact:** Compliance recording and Config rule validation for Sprint 4 could not proceed; SOC visibility into resource changes was lost.  
**Action Taken:** Escalated to SOC Lead requesting either manual Config activation or temporary permissions including config:StartConfigurationRecorder.  
(Screenshot: Ticket-03-ConfigRecorder-Failure.png)

---

## Additional Observations  
- Multiple cross-account permission gaps slowed SOC workflows but did not indicate active threats.  
- Visibility blockers were consistently mitigated through escalation and re-testing.  
- All issues were resolved after updates to IAM roles or service configurations.

---

## Conclusion  
The findings above reflect real-world SOC triage activity including alert analysis, escalation, AWS service troubleshooting, and evidence-rich communication. These tickets demonstrate readiness for Tier 1/2 SOC Analyst roles involving cloud triage, log analysis, and coordinated incident response within a multi-account AWS environment.
