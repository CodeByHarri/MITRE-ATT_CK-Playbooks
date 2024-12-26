# Indicator_Removal:_Clear_Linux_or_Mac_System_Logs - T1070002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1070.002 |
| MITRE Sub-TTP | T1070.002 |
| Name | Indicator Removal: Clear Linux or Mac System Logs |
| Log Sources to Investigate | For T1070.002, investigators should review logs in the /var/log/ directory, given its involvement in storing system and user activity logs. Key logs to examine include: /var/log/auth.log or /var/log/secure for authentication entries that may have been tampered with, /var/log/messages for general system activity, and /var/log/wtmp or /var/log/utmp for suspicious login and logout records. These logs could show evidence of unauthorized log deletions or alterations. |
| Key Indicators | Key indicators of system log clearing include sudden gaps in the log file timeline, changes in file size without corresponding log content increases, or the absence of expected error or activity logs. Specifically, a complete absence of log files or the presence of empty log files where there should normally be activity can indicate suspicious erasure activities. |
| Questions for Analysis | Tier 1 analysts should consider the following: Are there unexplained gaps in the system log files? Have any log files been drastically reduced in size or turned into zero-byte files unexpectedly? Are there recent authentication events that correspond with the times where logs show anomalies? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of substantial log file manipulation without corresponding system administration activities. Examples include sudden and unexplained zero-byte log files or missing logs for extended periods during which activity should be logged. Additionally, escalate if abnormal patterns of authentication attempts coincide with when logs were cleared. |
| Additional Analysis Steps for L1 | Tier 1 analysts should verify the time stamps of logs across different categories to identify unusually synchronized gaps. They should also check for recent changes in file permissions or ownership of logs, and look for any related suspicious admin or root activities. |
| T2 Analyst Actions | Tier 2 analysts should conduct a deeper forensic investigation, including recovering deleted log files if possible and correlating the log timelines with other system events like file modifications or installation of unknown software. They should also review user and process histories to identify potential unauthorized users or processes. |
| Containment and Further Analysis | Immediately isolate the affected system to prevent further log manipulation. Consider implementing enhanced logging mechanisms and file integrity monitoring to detect further unauthorized changes. Coordinate with IT operations to review and potentially restore logs from backups. Lastly, ensure that all access credentials, especially administrative ones, are changed or audited for misuse. |
