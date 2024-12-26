# Data_from_Information_Repositories:_Messaging_Applications - T1213005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1213.005 |
| MITRE Sub-TTP | T1213.005 |
| Name | Data from Information Repositories: Messaging Applications |
| Log Sources to Investigate | Monitor logs from messaging applications such as Microsoft Teams, Google Chat, and Slack. Specifically, look for chat history, file transfer logs, user access logs, and integration logs if available. Additionally, review email notifications related to new user logins, modified credentials, and unusual activity alerts from these platforms. |
| Key Indicators | Unusual chat activity such as excessive messages containing links, attachments, or credentials. Large-scale downloading or exporting of chat histories or files. Sudden increase in file uploads, especially those labeled with keywords such as 'password', 'secret', or 'confidential'. Unexpected changes in chat application configuration or unauthorized API calls. |
| Questions for Analysis | Is there a pattern of unusual login attempts or access times? Are there specific users who are frequently involved in suspicious chat activities? Is there a sudden increase in the volume of data being sent or received by certain users? Are there any alerts from the messaging platform indicating potential security risks? |
| Decision for Escalation | Escalate if there are clear signs of unauthorized access or data exfiltration, such as confirmed credential leaks, sensitive data transfers, or if the potential impact is high (e.g., critical business data). Escalate when multiple indicators align with known TTP patterns, despite initial uncertainty in individual logs. |
| Additional Analysis Steps for L1 | Verify the legitimacy of suspicious login attempts by checking IP addresses and corresponding user geolocation. Cross-reference timestamps of unusual chat activities with other log sources such as identity and access management (IAM) tools. Attempt to contact the user in question to confirm recent activities. |
| T2 Analyst Actions | Perform a deeper analysis of user activities, examining historical data for patterns of behavior. Review associated files transferred or linked in the chat logs against known threat intelligence databases. Conduct interviews if necessary with involved personnel to understand context or verify anomalies. |
| Containment and Further Analysis | Immediately disable compromised accounts and reset credentials. Implement IP blocking or quarantine affected systems dependent on severity. Perform a thorough audit trail of affected messaging platforms to assess the extent of data exposure. Engage with incident response teams to prepare for public disclosure if the breach is significant. |
