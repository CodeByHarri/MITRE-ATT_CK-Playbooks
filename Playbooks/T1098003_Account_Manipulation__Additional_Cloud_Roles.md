# Account_Manipulation:_Additional_Cloud_Roles - T1098003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1098.003 |
| MITRE Sub-TTP | T1098.003 |
| Name | Account Manipulation: Additional Cloud Roles |
| Log Sources to Investigate | Investigate cloud service provider logs, such as AWS CloudTrail, Azure Activity Logs, and Google Cloud Audit logs. Look for IAM policy changes, role assignments, and user activity logs. Examples include 'AttachUserPolicy', 'CreatePolicyVersion' in AWS and changes in IAM roles or permissions in Azure or Google Cloud. |
| Key Indicators | Unusual IAM policy version creation or attachment to user accounts. Modifications to IAM policies or addition of new roles in user accounts, especially those not typically involved in IAM management. Alerts from AWS CloudTrail or Azure Security Center indicating unusual role/permission changes. |
| Questions for Analysis | Was the role addition or IAM policy change performed by an account that typically manages IAM roles? Is the activity logged during abnormal hours or from unfamiliar locations or IP addresses? Is there corresponding suspicious activity on related accounts? |
| Decision for Escalation | Escalate if the IAM policy changes or role additions are performed by unexpected users, if they happen outside of normal hours, or if they are associated with other indicators of compromise, such as login anomalies or privilege escalations in logs. |
| Additional Analysis Steps for L1 | Verify if the account is authorized to make IAM changes. Check the time and location of the activities for anomalies. Review associated accounts and activities for similar alterations or suspicious behaviors. |
| T2 Analyst Actions | Correlate the suspicious role changes with any other anomalous activities in the network or cloud environment, such as data exfiltration attempts or novel access patterns. Verify any alerts against known threat intelligence related to account manipulation. |
| Containment and Further Analysis | Revoke or rollback the recent IAM policy changes or role modifications for compromised or suspicious accounts. Conduct a comprehensive review of all access rights and policies across cloud accounts. Consider implementing multi-factor authentication (MFA) for elevated roles and monitor for further suspicious activities over an extended period. |
