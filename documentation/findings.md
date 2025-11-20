# Findings
## Ticket 01 – Medium Severity: SNS Authorization Failure

While configuring the notification workflow in the Containment Lab account, an SNS topic creation attempt failed due to insufficient IAM permissions. The “PAN-1_PathogenAlertNetwork” topic is required for sending SOC alerts from the CAL-3 ViroShield Lambda function during outbreak detection.

**Services:** SNS, IAM  
**Error:** sns:CreateTopic – AccessDenied  
**Impact:** SOC alerts cannot be generated until permissions are corrected  
**Action Taken:** Escalated to SOC Lead for topic creation and permission update  
(Screenshot included in documentation/screenshots)

## Ticket 02 – Medium Severity: Athena Results Write Permission Error
Amazon Athena queries failed due to missing S3 permissions on the central logs bucket. 
This prevented log analysis workflows in the Archive Ward account. 
Escalated to SOC Lead with recommended IAM permissions.
(Screenshot included)

## Ticket 03 – Medium–High Severity: AWS Config Recorder Failure
AWS Config recording could not start due to missing IAM permissions in the Containment Lab account.
This blocked compliance recording and Sprint 4 evidence collection. 
Escalated with recommended permissions.
