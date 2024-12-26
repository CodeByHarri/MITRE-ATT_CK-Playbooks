# Data_Manipulation:_Stored_Data_Manipulation - T1565001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1565.001 |
| MITRE Sub-TTP | T1565.001 |
| Name | Data Manipulation: Stored Data Manipulation |
| Log Sources to Investigate | Monitor file access logs, particularly those related to databases, Office files, and other shared file storage systems. Analyze logs from applications managing these data files and databases, such as SharePoint logs, database transaction logs, and email server logs for anomalies. Pay attention to data integrity events reported by data loss prevention (DLP) tools. Collect logs from backup systems to compare data versions over time. |
| Key Indicators | Unusual file access patterns, such as unexpected modifications or deletions by non-authorized users; Changes in database records without corresponding legitimate transactions; Textual or structural discrepancies in documents or database records, potentially identified by file hash changes; Unscheduled data manipulation activities flagged by DLP solutions. |
| Questions for Analysis | Is there documented evidence of who modified the data? Are the modifications aligned with business hours and roles associated with legitimate data access? Are multiple unrelated data sources showing similar anomalous patterns? Do the changes reflect any known adversary tactics, techniques, or procedures (TTPs)? |
| Decision for Escalation | Escalate if data alterations cannot be attributed to legitimate activities or users, especially after checking user permissions and activity logs. Escalate if data manipulation coincides with other known malicious activities or if source IPs and accounts involved exhibit suspicious patterns, such as originating from high-risk locations. |
| Additional Analysis Steps for L1 | Perform a thorough review of the context surrounding data access events, such as examining recent access control changes. Look for correlated alarms or alerts that may indicate multi-vector attacks. Check for recent software or configuration changes in data storage systems that could affect data integrity. |
| T2 Analyst Actions | Conduct a deep dive into access logs and user activity to trace any potential unauthorized access paths. Use advanced forensic tools to recover deleted or altered data, corroborating findings against historical data backups. Engage with system owners to verify the integrity and accuracy of critical datasets impacted. |
| Containment and Further Analysis | Initiate measures to prevent further unauthorized access by modifying access controls or revoking compromised credentials. Restore data from unaltered backups while performing rigorous consistency checks. If malicious activity is confirmed, activate the incident response protocol to identify breach causes, scope, and execute comprehensive remediation. |
