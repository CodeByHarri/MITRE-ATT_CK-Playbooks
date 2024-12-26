# Scheduled_Task_Job:_Scheduled_Task - T1053005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution, Persistence, Privilege Escalation |
| MITRE TTP | T1053.005 |
| MITRE Sub-TTP | T1053.005 |
| Name | Scheduled Task/Job: Scheduled Task |
| Log Sources to Investigate | Investigate Windows Event Logs, specifically the Task Scheduler operational logs (Microsoft-Windows-TaskScheduler/Operational) for task creation, modification, or execution events. Check Security Event Logs, especially events related to privilege escalation and user logon activities. System logs should also be reviewed for any process execution events related to 'schtasks' or relevant PowerShell cmdlets like 'Invoke-CimMethod'. Additionally, examine Registry key modifications pertaining to task schedules under 'HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache' and monitor Windows Management Instrumentation (WMI) activity logs. |
| Key Indicators | Creation of new scheduled tasks or modification of existing tasks without prior authorization. Execution of unexpected scheduled tasks using high privilege accounts like SYSTEM. Deletion or modification of Security Descriptor registry values associated with tasks. Usage of 'schtasks.exe' or 'Invoke-CimMethod' with unusual parameters. Discrepancies in the visibility of scheduled tasks (e.g., tasks that don't appear in typical queries but still execute). WMI activity that aligns with known methods to create or modify scheduled tasks. |
| Questions for Analysis | Are there any unexpected scheduled tasks present on the system or network assets? Who initiated or modified the scheduled task, and does this align with expected behavior for that user? Does the scheduled task execute any unusual scripts or binaries? Are there signs of privilege escalation related to scheduled task management? Are there discrepancies in the task visibility when using different enumeration commands or tools? |
| Decision for Escalation | Escalate to Tier 2 if the scheduled task is observed running in high privilege contexts like SYSTEM without corresponding justified change requests. Escalate if there are indicators of irregular task hiding, such as changes to Security Descriptor registry values or metadata obfuscations. Also, escalate if there is evidence of lateral movement attempts via task scheduling. |
| Additional Analysis Steps for L1 | Verify the legitimacy of scheduled tasks by cross-referencing with known benign tasks inventory or change management records. Examine the task actions and trigger settings for any anomalies. Flag tasks with unusual creation times or those created by unknown users. Conduct an initial comparison of tasks visibility using multiple enumeration tools and queries. |
| T2 Analyst Actions | Conduct a thorough historical analysis of the task creation and modification records to trace the origin of any suspicious activity. Investigate associated files or scripts that are executed by suspicious tasks for malicious indicators. Analyze WMI and PowerShell scripting activities related to task scheduling. Review network logs to determine if there is any connection with known threat actor behavior, especially related to lateral movement. |
| Containment and Further Analysis | Suspend or disable any suspicious scheduled tasks while the investigation is active. Revert any unauthorized registry changes related to task scheduling. Use Endpoint Detection and Response (EDR) tools to gather execution traces and artifact collection for further forensic analysis. Implement enhanced monitoring of task scheduling activity across all critical systems to detect and prevent further abuse. Coordinate with IT operations to reinforce security around task management interfaces and permissions. |