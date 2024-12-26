# Domain_or_Tenant_Policy_Modification:_Trust_Modification - T1484002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1484.002 |
| MITRE Sub-TTP | T1484.002 |
| Name | Domain or Tenant Policy Modification: Trust Modification |
| Log Sources to Investigate | Review Azure Active Directory audit logs and AWS CloudTrail logs for AWS IAM Identity Center. Specifically, examine logs for creation or modification of domain trust relationships, new federated identity providers, and changes to trust settings. Look for any entries indicating the addition of new signing certificates or alterations to claim issuance rules in AD FS. Example log sources include Azure AD Activity Reports and AWS IAM Identity Center Federation Reports. |
| Key Indicators | Indicators include sudden additions or modifications to domain trusts, unusual changes to federation configurations, unexpected new identity providers, and unauthorized signing certificate modifications. Atypical activities from known identity providers and any new or unusual federation paths being used for authentication are also key indicators. |
| Questions for Analysis | Did the changes to the domain trust or identity federation align with any scheduled maintenance or legitimate requests? Are there any accounts with elevated privileges that were used to make these changes? Have there been any prior warnings or alerts from the accounts involved in the activities? Does the timing of the trust modifications align with known attack patterns or activity from suspicious IP addresses? |
| Decision for Escalation | Escalate if any unauthorized changes to domain trusts or identity federation settings are discovered, especially if these changes were made by accounts without appropriate admin privileges. Also, escalate if there are indications of a compromised certificate or any unauthorized signing certificate addition. |
| Additional Analysis Steps for L1 | Cross-reference the timelines of logged events with scheduled changes in the organization. Validate the authenticity of accounts making the changes by checking recent authentication patterns and locations. Verify if there are correlating alerts for atypical user behavior or failed login attempts from the accounts involved. |
| T2 Analyst Actions | Perform a deeper investigation into any suspicious or unauthorized trust or identity provider modifications. Audit all recent actions taken by suspect accounts with elevated privileges. Analyze network traffic for evidence of data exfiltration or communication with known malicious IPs. Conduct threat intelligence analysis to see if related indicators have been seen elsewhere. |
| Containment and Further Analysis | If unauthorized changes are confirmed, immediately roll back any unauthorized trust modifications or federated identity configurations. Disable or isolate any accounts that were used to make the unauthorized changes. Conduct a full security assessment of the affected systems and domains. Update credentials for any sensitive accounts and monitor for further suspicious activity. Communicate with stakeholders about potential security implications and update security policies and incident response plans to prevent future occurrences. |