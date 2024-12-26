# Account_Manipulation:_Additional_Cloud_Credentials - T1098001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1098.001 |
| MITRE Sub-TTP | T1098.001 |
| Name | Account Manipulation: Additional Cloud Credentials |
| Log Sources to Investigate | Investigate logs from cloud management platforms like AWS CloudTrail, Azure Activity Logs, and GCP Cloud Audit Logs. Check for API calls related to credential management such as CreateKeyPair, ImportKeyPair, CreateAccessKey, CreateLoginProfile in AWS or corresponding API calls in Azure and GCP. Additionally, consider logs from identity management services such as Azure AD Sign-Ins and Identity Protection logs, as well as any SIEM alerts regarding unusual credential activity or changes in account permissions. |
| Key Indicators | Look for unexpected or unauthorized creation of new credentials, such as SSH keys, access keys, or app passwords, especially during off-hours or from unusual locations. Check for anomalies associated with the use of credential management APIs by non-administrative accounts or service principals. Monitor for the addition of new credentials under service principals in Azure or similar activity in other cloud environments. |
| Questions for Analysis | 1. Are there recent additions of new cloud credentials that lack corresponding change requests or approvals?<br>2. Did the action occur outside of normal business hours or from an unusual geographic location?<br>3. Does the account making the changes have a history of suspicious or anomalous activity? |
| Decision for Escalation | Escalate to Tier 2 if: 1. Unauthorized credential modifications are detected.<br>2. Changes were made by accounts that typically do not perform such actions.<br>3. There is a pattern of similar activity or if multiple accounts are affected. |
| Additional Analysis Steps for L1 | 1. Verify the identity and role of the user or service principal that performed the changes.<br>2. Check if the account's recent activities align with its usual behavior.<br>3. Review IP addresses or device types associated with the log entries for anomalies. |
| T2 Analyst Actions | 1. Conduct a deeper investigation into the logs for additional context around the suspicious activity.<br>2. Correlate with threat intelligence to determine if this behavior matches known adversary techniques.<br>3. Assess if there are any other impacted resources or accounts within the environment. |
| Containment and Further Analysis | 1. Revoke or suspend suspicious credentials immediately to prevent further unauthorized access.<br>2. Conduct a full audit of the affected accounts and any related applications or services to identify potential breaches.<br>3. Strengthen access controls and enforce MFA on affected accounts. 4. Communicate with stakeholders to inform them of potential security issues and planned mitigation steps. |
