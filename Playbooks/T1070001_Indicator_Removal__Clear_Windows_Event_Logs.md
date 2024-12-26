# Indicator_Removal:_Clear_Windows_Event_Logs - T1070001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1070.001 |
| MITRE Sub-TTP | T1070.001 |
| Name | Indicator Removal: Clear Windows Event Logs |
| Log Sources to Investigate | Investigate the Security, System, and Application event logs for signs of unauthorized clearing. Review PowerShell logs (Operational log under ‘Microsoft-Windows-PowerShell/Operational’) for any execution of commands related to `Remove-EventLog`. Check Sysmon logs for process creation events specifically for `wevtutil` or suspicious PowerShell activity. Also, consider monitoring the File System events for changes or deletions within `C:\Windows\System32\winevt\logs\`. Examine user actions within the System audit logs for unusual privilege escalation activities. |
| Key Indicators | Execution of the `wevtutil` utility with 'cl' argument. Invocation of the `Remove-EventLog` command in PowerShell. Presence of `evtx` file deletions or modifications without corresponding normal activities. Unexpected privilege escalation in logs preceding event log modifications. High-frequency log clearing without scheduled maintenance. |
| Questions for Analysis | Who executed the log-clearing commands? Was the command executed by a legitimate administrative user? Were there legitimate system maintenance activities scheduled at the time? Is there evidence of unauthorized access or account compromise in surrounding logs? |
| Decision for Escalation | Escalate if there's no documented maintenance at the time of the event log clearance. Escalate if events are cleared by non-standard users or accounts showing signs of potential compromise (e.g., new accounts without administrative history). Escalate if correlated indicators suggest broader malicious activity. |
| Additional Analysis Steps for L1 | Verify user account legitimacy and recent activities. Cross-reference the cleared logs' timeframe with other logs for lateral movement or privilege escalation indicators. Look for anomalies in network activity or new service creation immediately around the event log clearing event. |
| T2 Analyst Actions | Conduct deeper forensics on the affected host to retrieve remnants of the cleared log files, possibly using file recovery tools. Analyze timestamps and metadata of altered logs to reconstruct the timeline. Investigate any suspicious accounts for illegitimate administrative actions. |
| Containment and Further Analysis | Isolate affected hosts from the network to prevent further compromise. Conduct a thorough vulnerability scan to close any exploited vulnerabilities. Consider implementing more robust log monitoring and storage practices, such as offloading logs to a secure, centralized log server. Perform a user audit and enforce strong password policies and multi-factor authentication to mitigate future unauthorized accesses. |
