# Compromise_Accounts:_Cloud_Accounts - T1586003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1586.003 |
| MITRE Sub-TTP | T1586.003 |
| Name | Compromise Accounts: Cloud Accounts |
| Log Sources to Investigate | Examine cloud service provider logs including login and authentication logs from AWS CloudTrail, Azure AD Sign-in logs, Google Workspace Admin logs, and access logs from cloud storage services (e.g., AWS S3 access logs). Review identity provider logs if Single Sign-On (SSO) is used, as well as logs from cloud-based messaging platforms like SendGrid and Twilio. |
| Key Indicators | Multiple unsuccessful login attempts followed by a successful login, especially from unusual locations or IP addresses. Unusual access patterns such as accessing cloud storage services or administrative functions from previously unseen devices or locations. Sudden spikes in the amount of data being transferred to or from cloud accounts. Access to cloud-based messaging services that align with known phishing campaigns. |
| Questions for Analysis | Are there indications of login anomalies, such as access from previously unused devices, locations, or IP addresses? Is there any recent evidence of phishing attempts targeting the user associated with the compromised account? Is there any evidence of data exfiltration, such as large downloads or uploads? Have there been any recent changes to account privileges or access roles? |
| Decision for Escalation | Escalate to Tier 2 if there are confirmed unauthorized accesses, especially if they are associated with key business or sensitive accounts. Escalation is also warranted if there are signs of data exfiltration or if a compromised account has elevated privileges that could impact the security of other systems or data. |
| Additional Analysis Steps for L1 | Verify the login activities against normal behavior for the user, including common login locations, devices, and times. Review company-wide alerts or security advisories for related phishing or credential theft attempts. Check for any alerts or notifications from the cloud service provider about unusual account activity. |
| T2 Analyst Actions | Perform a deep dive into the security logs and network traffic associated with the suspicious account access. Use threat intelligence feeds to correlate IP addresses and user agents with known malicious activities. Conduct a detailed analysis of cloud account configurations and permissions for signs of tampering or misuse. |
| Containment and Further Analysis | Disable the compromised account's access to sensitive services and initiate a password reset. Review and potentially revoke any access tokens or API keys associated with the account. Conduct a full audit of actions taken by the account to identify any potential data leakage or misuse. Implement additional monitoring and alerts on the account and similar accounts to detect further attempts at access. |
