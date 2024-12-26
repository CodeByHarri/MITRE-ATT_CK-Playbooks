# Data_Staged:_Remote_Data_Staging - T1074002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1074.002 |
| MITRE Sub-TTP | T1074.002 |
| Name | Data Staged: Remote Data Staging |
| Log Sources to Investigate | Investigate logs from file transfer utilities, command-line execution logs, cloud service activity logs, and file access events. Examples include system logs from SCP or rsync for data transfers, Windows Event Logs with command execution records, cloud provider logs for instance creation and VM activity, and file system audit logs for unusual file access or modifications. |
| Key Indicators | Look for large volumes of data transfer to a specific host, anomalies in the creation of compressed or encrypted files, unexpected cloud instance creations, unusual high-volume file read/write activities, and redundant file access patterns over short durations. Example: A large file modification event shortly followed by a network transfer initiated from cmd.exe. |
| Questions for Analysis | Is there a larger than normal volume of data being accessed or transferred? Are there signs of data archiving or encryption activities that cannot be accounted for? Is there evidence of new cloud instances being created with atypical configurations? Are these activities aligned with known business operations? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of unauthorized data aggregation or transfer, especially if associated with abnormal file transfer mechanisms or script execution. Also, escalate if unexpected cloud instance creation aligns with periods of suspicious data access. |
| Additional Analysis Steps for L1 | Verify if data transfer volumes correlate with known scheduled jobs. Check user authentication logs for anomalous login attempts related to staging actions. Validate if the accessed or modified data set is linked to business processes or if it involves sensitive or critical data, potentially indicating an exfiltration attempt. |
| T2 Analyst Actions | Conduct deeper packet inspection for network data traffic to identify any anomalies in data patterns that suggest staging. Cross-reference with threat intelligence for known tactics, techniques, or compromised IPs. Evaluate the integrity and content of any cloud instances identified for unusual artifacts indicative of staging activity. |
| Containment and Further Analysis | Isolate affected systems or network segments displaying staging activity. Conduct a forensic analysis to track the source of unauthorized data aggregation. Review access controls and permissions to prevent further unauthorized data staging. Document all investigative findings and engage with incident response if potential data breach is confirmed. |
