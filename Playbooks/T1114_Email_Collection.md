# Email_Collection - T1114

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1114 |
| MITRE Sub-TTP | T1114 |
| Name | Email Collection |
| Log Sources to Investigate | Email server logs (e.g., Microsoft Exchange, Office 365), email client application logs (e.g., Outlook, Thunderbird), network traffic analysis (e.g., firewall logs, proxies), and security information and event management (SIEM) solutions to correlate events. Specifically, look for logs showing unexpected email forwarding rules, mass email exports, or unauthorized login attempts. |
| Key Indicators | Unusual email forwarding rules set up on a user’s account, especially to external addresses; excessive accessing and downloading of email data; logins from unusual geographic locations indicative of suspicious behavior; anomalies in email server logs indicating potential unauthorized access or data exfiltration; high volume of SMTP traffic compared to baseline. |
| Questions for Analysis | Is there evidence of new or modified email rules that forward emails to unauthorized external addresses? Are there unusual login patterns or failed login attempts from IPs not previously associated with the user's account? Has there been a spike in the volume of email downloads or exports by a single account? Is there any unauthorized remote access? |
| Decision for Escalation | Escalate to Tier 2 if there are new or suspicious email forwarding rules to external domains, confirmed unauthorized logins, or evidence of bulk email data access indicating potential compromise. Escalation should also occur if pattern analysis suggests correlation with known threat actor TTPs. |
| Additional Analysis Steps for L1 | Verify user accounts and assess whether recent logins and activities align with known user behavior. Check for recent changes in email settings, including forwarding rules. Establish a timeline of the observed activities and cross-reference against organizational baselines. Determine if IP addresses involved are known threats or unusual. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the compromised accounts, reviewing detailed access logs and identifying any additional users targeted by similar methods. Assess related systems and credentials that may be affected due to the compromise. Correlate findings with threat intelligence feeds to identify potential threat actors. |
| Containment and Further Analysis | Temporarily disable compromised accounts and reset credentials. Remove suspicious email forwarding rules. Notify affected users and provide guidance on secure email practices. Implement additional email security controls, such as multifactor authentication (MFA) for all users. Compile a comprehensive report detailing the incident for senior management and adjust security policies to prevent recurrence. |
