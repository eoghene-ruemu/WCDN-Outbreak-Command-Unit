# Methodology

This project followed a structured SOC/SIEM workflow including:

1. Alert intake from GuardDuty, Security Hub, CloudTrail, and VPC Flow Logs.
2. Classification using the outbreak severity matrix (Urgent, High, Medium, Low).
3. Evidence collection from AWS logging sources.
4. MITRE ATT&CK mapping for each alert type.
5. Escalation routing to Threat Hunters or Command Ops.
6. Communication updates and outbreak status reporting.
7. Documentation of incident flow and containment recommendations.

