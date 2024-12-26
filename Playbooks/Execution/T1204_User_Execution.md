# User_Execution - T1204

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1204 |
| MITRE Sub-TTP | T1204 |
| Name | User Execution |
| Log Sources to Investigate | Review email logs for indicators of phishing attempts such as suspicious senders, subjects, or attachments. Analyze web proxy logs for access to known malicious domains or IP addresses. Inspect endpoint security logs for execution of unusual scripts or applications. Check DNS logs for queries to suspect domains. Examine user activity logs for anomalies like unexpected logins or file accesses. |
| Key Indicators | Presence of phishing emails with malicious attachments or links. Execution of scripts or software not commonly used in business operations, especially from user directories. Network communications to known malicious IPs/domains shortly after suspicious user activities. Multiple failed login attempts or new successful logins from unusual locations. |
| Questions for Analysis | Did the user receive any suspicious emails around the time of the detected activity? Is there a correlation between user actions and any known phishing campaigns? Are there unexplained instances of new software or scripts being executed on the user's system? Has there been any unusual network activity associated with the user or endpoint in question? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of suspicious email delivery combined with execution of unverified code or scripts. Also escalate if there are signs of potentially malicious network activity following user execution. If the user reports unexpected behavior aligning with technical indicators, escalate for deeper investigation. |
| Additional Analysis Steps for L1 | Correlate email logs with endpoint activity to determine if a specific email led to execution. Check recent security alerts for any signatures matching the executed scripts or applications. Gather information on user’s recent actions and any deviations from their typical behavior pattern. |
| T2 Analyst Actions | Perform a thorough forensic analysis of the endpoint for malware artifacts. Investigate all network connections made by the suspicious binary or script. Check user’s past behavior for patterns of responding to phishing or social engineering tactics. Collaborate with threat intelligence teams to match observed indicators with known threats. |
| Containment and Further Analysis | Isolate the affected endpoint from the network to prevent further spread. Revoke any credentials that may have been compromised. Conduct a malware scan and remove any confirmed threats. Review the organization's security awareness training efficacy and update as necessary. Consider implementing additional security controls, like more stringent email filtering policies or enhanced endpoint monitoring. |
