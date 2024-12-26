# System_Binary_Proxy_Execution:_Control_Panel - T1218002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1218.002 |
| MITRE Sub-TTP | T1218.002 |
| Name | System Binary Proxy Execution: Control Panel |
| Log Sources to Investigate | Investigate Windows Event Logs, specifically Security and Application logs for suspicious Control Panel executions. Monitor PowerShell logs, Process Creation Logs, and Sysmon logs for .cpl and renamed .dll files being executed. Check for any modifications to the registry key HKCU\Software\Microsoft\Windows\CurrentVersion\Control Panel\Cpls. Network logs should be reviewed for any unusual outbound connections post Control Panel item execution. |
| Key Indicators | Presence of .cpl or .dll files with irregular naming schemes. Registry modifications under HKCU\Software\Microsoft\Windows\CurrentVersion\Control Panel\Cpls indicating newly registered Control Panel items. Execution of control.exe with unusual arguments or from uncommon directories. Suspicious network traffic following Control Panel item execution. Absence of CPlApplet functions in .cpl files that are nonetheless executed. |
| Questions for Analysis | 1. Was control.exe executed with an unusual or unexpected command-line argument?<br>2. Are there any recent registry modifications related to Control Panel items?<br>3. Is the source of the executed .cpl or renamed .dll file known and trusted? 4. Are there any subsequent unauthorized network connections or data exfiltration attempts? |
| Decision for Escalation | Escalate to Tier 2 if: There are unexplained or unauthorized registry changes, the .cpl or .dll file does not have a legitimate source, there is accompanying suspicious network activity, or there is evidence that these files were delivered through a phishing campaign. |
| Additional Analysis Steps for L1 | Verify the file path and the hash of the .cpl or .dll file through a reputable threat intelligence source. Inspect recent changes or additions to registry entries related to Control Panel items. Look for related alerts or logs indicating possible phishing activity. |
| T2 Analyst Actions | Conduct a deeper analysis by inspecting the binary of the suspect .cpl or .dll file for malicious code or behaviors. Use sandboxing to observe the file’s behavior during execution. Analyze any suspicious network activity detected and corroborate with known Indicators of Compromise (IOCs). |
| Containment and Further Analysis | Quarantine the involved .cpl or .dll file. Block any detected unauthorized outbound network connections. Revert unauthorized registry changes. Conduct a sweep of endpoints to check for similar suspicious Control Panel items. Investigate affected endpoints for signs of further compromise and propagate threat intelligence updates to containment measures. |
