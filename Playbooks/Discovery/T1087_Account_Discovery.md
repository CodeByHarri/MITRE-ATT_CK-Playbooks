# Account_Discovery - T1087

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1087 |
| MITRE Sub-TTP | T1087 |
| Name | Account Discovery |
| Log Sources to Investigate | Monitor logs from authentication services such as Active Directory, Azure AD, and other IAM providers for unusual account enumeration activity. Analyze PowerShell logs, command-line logging, and cloud management APIs such as AWS CloudTrail or Google Cloud Audit logs for commands related to listing user accounts. Network traffic logs should also be reviewed for requests to directory services or suspicious DNS queries that might indicate account enumeration activity. |
| Key Indicators | Unusual PowerShell commands or command-line execution designed to list user accounts, such as 'Get-ADUser' or similar. Sudden spike in calls to IAM-related APIs (e.g., AWS IAM ListUsers, Google IAM Service Accounts List) within short timeframes without prior authorization. Cross-reference user account enumeration commands executed by non-admin accounts or from unexpected sources/IP addresses. |
| Questions for Analysis | Is the account enumeration activity happening during non-business hours or from atypical user accounts? Are there multiple enumeration attempts in a short period of time, specifically from new or unapproved locations and IPs? Is there any correlation between this activity and any recent email or phishing attempts reported? |
| Decision for Escalation | Escalate to Tier 2 if account enumeration is accompanied by failed login attempts, especially if originating from external or unrecognized IP addresses. Also, escalate if there is any indication of possible data exfiltration or if enumeration is tied to a privileged account or administrative commands. |
| Additional Analysis Steps for L1 | Cross-check the account names or emails enumerated with recent changes in application access rights or configurations. Verify if any newly created service accounts or roles correlate with the enumeration logs. Validate if any known security updates or patches have been applied around the time of the activity. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the involved systems, including memory capture and disk imaging if necessary. Cross-verify the enumeration activity with any existing security incidents. Liaise with stakeholders to verify if any legitimate administrative tasks could account for the activity. Analyze broader network traffic patterns to check for similar suspicious activities. |
| Containment and Further Analysis | Immediately isolate any systems displaying unauthorized user enumeration behavior from the network. Implement temporary access controls or disable suspicious accounts. Review access logs thoroughly and leverage SIEM to search for related patterns or corroborating evidence of compromise. Consider resetting shared credentials and conducting a security awareness session for potentially affected users. |
