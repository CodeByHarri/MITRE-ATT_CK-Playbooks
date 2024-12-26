# Indicator_Removal:_Clear_Command_History - T1070003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1070.003 |
| MITRE Sub-TTP | T1070.003 |
| Name | Indicator Removal: Clear Command History |
| Log Sources to Investigate | For Linux/macOS, review bash history files (~/.bash_history) and logs relevant to shell command execution. For Windows, check PowerShell logs (specifically PowerShell/Operational logs) and the content of the PSReadLine history file (ConsoleHost_history.txt). Ensure to collect logs from centralized logging solutions like SIEM for any anomalies and check access logs to see which user accounts have been accessing these logs. |
| Key Indicators | On Linux/macOS, unexplained deletion of ~/.bash_history files or frequent execution of 'history -c'. On Windows, PowerShell logs showing 'Clear-History' command execution or deletion/editing of ConsoleHost_history.txt. Also, unusual gaps in command history or logins followed by sessions with missing history entries. |
| Questions for Analysis | Have there been any recent logins from unusual locations or under unusual circumstances? Has the command history file been deleted or cleared unexpectedly? Are there other indications of compromise on the system, such as unexpected account creations or privilege escalations nearby in time to the history clearing? |
| Decision for Escalation | Escalate if command history files are missing/deleted frequently, if there are matching IOC timelines with known suspicious activities, or if there is matching context with other malicious indicators such as unauthorized access or privilege escalation. |
| Additional Analysis Steps for L1 | Verify any recent user logins and correlate with deleted history events. Check for known malicious IPs or user accounts. Review surrounding logs for other suspicious behavior or signs of intrusion. Ensure no legitimate processes or scripts should have performed these actions. |
| T2 Analyst Actions | Conduct a deeper investigation into the user accounts involved, reviewing their activities across other systems. Look for patterns that might match known TTPs associated with adversarial actions. Check compliance with security policies regarding command history. Engage threat intelligence sources to match the activity with known campaigns or actors. |
| Containment and Further Analysis | If compromise is suspected, initiate the isolation of the affected system(s) for detailed forensic analysis. Recover command history files from backups if needed. Consider deploying enhanced monitoring on the account and system involved. Evaluate current endpoint security measures and potentially increase their sensitivity or coverage. Coordinate with response teams to remediate any identified compromise and ensure all access credentials involved are changed. |
