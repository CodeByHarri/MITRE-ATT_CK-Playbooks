# Email_Collection:_Local_Email_Collection - T1114001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1114.001 |
| MITRE Sub-TTP | T1114.001 |
| Name | Email Collection: Local Email Collection |
| Log Sources to Investigate | Review file access logs for `C:\Users\<username>\Documents\Outlook Files` and `C:\Users\<username>\AppData\Local\Microsoft\Outlook`, especially focusing on .ost and .pst files. Investigate process monitoring logs to check for unusual processes accessing these files, and user activity logs for suspicious patterns or unauthorized access attempts. Network logs should be analyzed to detect any exfiltration attempts of large .ost/.pst files. |
| Key Indicators | Unusual access to or modification of .ost/.pst files, especially outside of normal business hours. Processes not associated with Outlook accessing data files, such as command-line utilities or unknown applications. High-volume data transfer activity in network logs that coincide with file accesses in the Outlook directories. |
| Questions for Analysis | Is the accessing process legitimate and associated with Outlook or another recognized email client? Were files accessed outside of standard workflow hours? Are there signs of elevated privileges or attempts to hide file access (e.g., accessing files in stealthy modes)? Is there corroborating evidence of data exfiltration? |
| Decision for Escalation | Escalate if unauthorized processes are accessing email files, if there is evidence of out-of-hours file access and modification, or if network monitoring indicates data exfiltration consistent with email collection activities. |
| Additional Analysis Steps for L1 | Verify the legitimacy of processes accessing Outlook files via process execution logs. Check recent user login activity for anomalies. Confirm if accessed files align with user roles and responsibilities, potentially consulting with IT security for user context. |
| T2 Analyst Actions | Conduct deeper inspection into process execution chains to understand if malware or unauthorized scripts are involved. Analyze full network transaction logs for potential data exfiltration routes, focusing on any outbound traffic anomalously large or frequent. Interview affected users if necessary to establish communication and access norms. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent data exfiltration. Forensically copy .ost/.pst files and capture memory for further analysis. Assess and possibly disable any rogue software or scripts. Implement monitoring to prevent further unauthorized access. Engage with digital forensics team to establish the full scope of the incident and mitigate risks. |
