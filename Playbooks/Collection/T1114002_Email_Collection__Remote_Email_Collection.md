# Email_Collection:_Remote_Email_Collection - T1114002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1114.002 |
| MITRE Sub-TTP | T1114.002 |
| Name | Email Collection: Remote Email Collection |
| Log Sources to Investigate | Analyze email server logs (e.g., Exchange server logs), authentication logs for Office 365 or Google Workspace, and network traffic logs. Specific examples include event logs from Microsoft Exchange Server, audit logs from Office 365's Security & Compliance Center, and Google Workspace Admin audit logs. Network traffic logs (firewall, proxy logs) could show suspicious connections to email services. |
| Key Indicators | Unusual login attempts or logins from multiple geographic locations or anomalous IP addresses. Usage of scripts or tools like MailSniper. High volume of email export actions or file downloads. Authentication attempts using OAuth tokens or anomalous device identifiers. Sudden activity outside normal business hours or patterns indicative of data extraction. |
| Questions for Analysis | Is the login occurring from a known or suspicious IP address? Are there multiple failed login attempts followed by a successful login? Is the activity occurring during normal hours and from usual geographic locations for the user? Have there been recent password changes or alerts of compromised credentials? |
| Decision for Escalation | Escalate if there are logins from known malicious IPs, multiple failed login attempts followed by success, any use of unauthorized applications to access email data, or if email data is being accessed or extracted at unusual volumes or times. Consider escalation if the user is unable to verify legitimate access to the email resources. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the IP addresses logging into email accounts. Cross-check user-reported anomalies with log data. Confirm if the email client and device identifiers used for access match the user's typical patterns. Look for anomalies in device profiles and login times. |
| T2 Analyst Actions | Conduct a detailed review of the email headers and access history. Correlate with threat intelligence for known malicious IPs or tools. Verify with the user for suspicious logins to confirm if legitimate access occurred. Analyze email content access patterns and check for potential PII or sensitive data extraction. |
| Containment and Further Analysis | If malicious activity is confirmed, block or quarantine the user account to prevent further access. Reset the user's credentials and ensure 2-factor authentication is enforced. Conduct a complete investigation into the scope of accessed emails and potential exfiltration. Notify affected employees or stakeholders as necessary and improve monitoring for targeted mail systems. |
