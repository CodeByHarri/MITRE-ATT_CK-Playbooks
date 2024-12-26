# Event_Triggered_Execution:_Windows_Management_Instrumentation_Event_Subscription - T1546003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1546.003 |
| MITRE Sub-TTP | T1546.003 |
| Name | Event Triggered Execution: Windows Management Instrumentation Event Subscription |
| Log Sources to Investigate | Investigate logs from Windows Event Logs specifically under WMI-Activity log (Operational) to track WMI subscriptions and script executions. Security logs for process creation events (Event ID 4688) may also help identify suspicious process execution patterns related to 'WmiPrvSe.exe'. Additionally, monitor PowerShell logs (if enabled) for suspicious scripts creating or modifying WMI subscriptions. |
| Key Indicators | Look for 'WmiPrvSe.exe' executing unexpectedly or in unusual paths, changes to WMI filters and consumers, MOF file compilations (use of mofcomp.exe), and processes started from WMI triggers. Check for creation/modification of WMI namespaces and unusual activity in WMI logs, especially new or modified filters and consumers. |
| Questions for Analysis | Has 'WmiPrvSe.exe' started following any suspicious script execution? Are there any new or unusual WMI filters or consumers? Were there any MOF file compilations? Has there been an increase in process executions related to user logins or system uptimes? |
| Decision for Escalation | Escalate if: multiple unexplained WMI subscriptions are identified; 'WmiPrvSe.exe' shows execution of non-standard programs/scripts; unusual logins accompany WMI changes; if MOF files linked to unauthorized changes are detected. |
| Additional Analysis Steps for L1 | Review Windows Event Logs for any unusual activity related to WMI process and WmiPrvSe.exe. Search for execution of mofcomp.exe suspiciously. Correlate with security event logs for unexpected process launches. Verify whether any detected changes correspond to legitimate administrative activities. |
| T2 Analyst Actions | Conduct deeper investigations on identified WMI subscriptions, focusing on their origin and correlation with known malicious activities. Cross-reference with threat intelligence for any known IOCs. Check system-wide for other signs of compromise such as common payloads or malicious network traffic. Validate and report any false positives with context and remediation if applicable. |
| Containment and Further Analysis | Isolate affected systems from the network if ongoing compromise is suspected. Terminate any identified malicious WMI subscriptions. Remove or modify MOF files that are not recognized as legitimate. Conduct forensic analysis on affected machines to confirm the presence and scope of any compromise. Monitor for recurrence and update security protocols as necessary. |
