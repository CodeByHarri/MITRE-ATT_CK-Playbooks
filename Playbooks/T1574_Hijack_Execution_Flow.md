# Hijack_Execution_Flow - T1574

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Persistence, Privilege Escalation |
| MITRE TTP | T1574 |
| MITRE Sub-TTP | T1574 |
| Name | Hijack Execution Flow |
| Log Sources to Investigate | Investigate Process Execution logs, Windows Registry logs (specifically for suspicious modifications), DLL load logs, and file system changes. Examples include Windows Event Logs (Event ID 4688 for process creation), Sysmon logs (Event ID 7 for DLL loading), and PowerShell logs. Check logs from EDR solutions for indicators of execution flow hijacking and anomaly detection based on process execution sequences. |
| Key Indicators | Unexpected changes to program execution paths, unauthorized modifications in the Windows Registry (such as under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options), unusual DLL paths, or libraries loaded from unexpected locations. Frequent creation or modification of application-related directories and suspicious process trees. |
| Questions for Analysis | Has the registry been modified to alter the execution path of known applications? Are there unauthorized changes or entries observed in the Image File Execution Options? Which processes have loaded DLLs from untrusted paths? Are there any patterns of execution that do not align with expected application behaviors? |
| Decision for Escalation | Escalate to Tier 2 if there are verified unauthorized registry changes related to execution paths, confirmed loading of suspicious DLLs, or anomalous behavior observed in high-value or sensitive areas. Evidence of privilege escalation or bypass of application controls is also grounds for escalation. |
| Additional Analysis Steps for L1 | Verify the integrity of application directories and critical system files. Cross-reference revision history of registry changes with known updates or maintenance schedules. Look into recent account changes or privilege modifications around the same timestamp as the detected malpractices. |
| T2 Analyst Actions | Conduct a deeper investigation into historical patterns of registry access and file creation events. Use threat intelligence feeds to correlate discovered DLLs or executables with known threats. Execute memory dumps and forensic examination for suspicious processes to identify malware presence. |
| Containment and Further Analysis | Isolate impacted systems from the network to prevent further abuse. Use IT asset management tools to restore original execution paths and registry settings. Coordinate with IT to reinstall or repair affected applications. Monitor network traffic for signs of command and control activities, and apply patches or updates as necessary. |
