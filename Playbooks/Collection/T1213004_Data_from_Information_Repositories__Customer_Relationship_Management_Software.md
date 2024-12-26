# Data_from_Information_Repositories:_Customer_Relationship_Management_Software - T1213004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1213.004 |
| MITRE Sub-TTP | T1213.004 |
| Name | Data from Information Repositories: Customer Relationship Management Software |
| Log Sources to Investigate | Monitor CRM application logs (e.g., Salesforce event logs), network traffic logs, access logs for CRM systems, authentication and authorization logs, VPN access logs if CRM access is remote, and cloud service provider logs if CRM is hosted in the cloud. |
| Key Indicators | Unusual login times or IP addresses accessing CRM tools, large data exports or downloads from CRM systems, unusual access patterns such as new users accessing sensitive areas or excessive access to customer records, alerts from data loss prevention tools regarding CRM data, and inconsistencies in CRM system logins and access patterns. |
| Questions for Analysis | 1. Did the activity occur outside typical business hours?<br>2. Is the source IP address known and trusted within the organization?<br>3. Was there an unusual amount of data transferred or downloaded from the CRM system? 4. Are there recent alerts or signals from other security systems related to the same user or device? 5. Has the user accessed these specific CRM resources before? |
| Decision for Escalation | Escalate to Tier 2 if: The source IP is external or unknown, the user involved has no history of accessing CRM data or sensitive areas, there is corroborative evidence of phishing or other nefarious activity targeting the user, large data exports occur, or there is an existing investigation involving the user or data source. |
| Additional Analysis Steps for L1 | Verify the user's usual login behavior and history within the CRM system, corroborate with any recent email or communication that might suggest phishing attempts, check for recent password changes or MFA failures for the user, and cross-reference the originating IP address with known safe or unsafe IP lists. |
| T2 Analyst Actions | Conduct a deeper analysis of the user's activity within the CRM system over a longer time frame, analyze network traffic to and from the CRM platform for anomalies, review system access reports for discrepancies, interview/confirm with the user about unusual CRM access if needed, and check for any wider patterns indicative of a coordinated attack. |
| Containment and Further Analysis | Restrict the compromised account's access to critical systems, enforce a password reset and re-authentication if appropriate, implement stronger network-level monitoring for future CRM access, and review and strengthen user access policies. Further, conduct a forensic analysis of CRM logs and potentially affected systems to understand the scope of data exposure and implement measures to prevent similar intrusions. |
