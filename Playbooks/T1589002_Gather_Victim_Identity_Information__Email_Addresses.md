# Gather_Victim_Identity_Information:_Email_Addresses - T1589002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1589.002 |
| MITRE Sub-TTP | T1589.002 |
| Name | Gather Victim Identity Information: Email Addresses |
| Log Sources to Investigate | Investigate log sources such as email server logs (e.g., Exchange, Office 365 audit logs), web server logs to detect any suspicious activity attempting to access email-related endpoints, and firewall logs to identify abnormal traffic patterns. Monitor authentication logs from identity providers like Azure AD for any username enumeration activity. |
| Key Indicators | Key indicators include increased traffic to autodiscover API endpoints, spikes in authentication attempts without a clear pattern, unusual error response rates from login services indicating potential enumeration, and the appearance of recognizable patterns or automated scripts from specific IP addresses. Look for large quantities of email addresses accessed or abnormal use of APIs related to email management. |
| Questions for Analysis | 1. Are there multiple failed login attempts from a single IP to different email addresses?<br>2. Is there unusual access to autodiscover services?<br>3. Was there any unauthorized attempt to access sensitive accounts? 4. Are there anomalies corresponding with known threat intelligence about email enumeration tools or tactics? |
| Decision for Escalation | Escalate to Tier 2 if there are confirmed patterns of malicious enumeration or reconnaissance activity, detected use of known enumeration scripts, corroborated threat intelligence suggesting ongoing campaigns, or any indication of compromised or exploited email addresses. |
| Additional Analysis Steps for L1 | Review specific logs flagged for abnormal activity, investigate known suspicious IP addresses or user agents, and validate if accessed email addresses are publicly available or previously exposed in any breach. Check for correlation with existing threat intelligence regarding similar reconnaissance techniques. |
| T2 Analyst Actions | Perform deeper scrutiny of network traffic and endpoints related to the suspicious activity, confirm the legitimacy of access requests, cross-reference email addresses with known databases of compromised accounts, and use advanced detection tools to uncover hidden connections or larger patterns suggesting a coordinated attack. |
| Containment and Further Analysis | Implement IP-based restrictions or rate limiting on email-related API endpoints, conduct a thorough review and potential disabling of accounts identified during suspicious activities, monitor further access attempts to the affected resources, and engage in proactive threat hunting to uncover any additional reconnaissance or attack vectors. |
