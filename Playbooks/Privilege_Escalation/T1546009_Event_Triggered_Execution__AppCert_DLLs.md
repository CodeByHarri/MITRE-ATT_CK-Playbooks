# Event_Triggered_Execution:_AppCert_DLLs - T1546009

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1546.009 |
| MITRE Sub-TTP | T1546.009 |
| Name | Event Triggered Execution: AppCert DLLs |
| Log Sources to Investigate | Monitor Windows Event Logs, specifically Sysmon for DLL load events (Event ID 7), which can show the loading of AppCert DLLs. Utilize Process Creation Logs (Event ID 4688) to identify processes initiated by the API functions associated with AppCert DLLs. Registry Logs should be analyzed to detect modifications to the HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager\AppCertDLLs key. |
| Key Indicators | Presence of unusual or unsigned DLLs in the AppCertDLLs registry key. Frequent DLL loading events associated with unexpected processes or user accounts. Anomalous or newly created files in system directories or suspicious DLL paths. Sudden appearance or modification of the AppCertDLLs registry key. |
| Questions for Analysis | Are there unsigned or unusual DLL files being loaded by legitimate system or application processes? Has there been a recent change to the AppCertDLLs registry key and by which account? Are there any patterns in the DLL loading events that suggest malicious activity (e.g., same DLL loaded across multiple unrelated processes)? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized modifications to the AppCertDLLs registry key are detected, if unusual DLLs are persistently loaded across critical processes, or if the source of the change is unknown or tied to an account with suspicious activity. |
| Additional Analysis Steps for L1 | Verify the list of loaded DLLs with known benign or approved application lists. Check the file hashes of the DLLs loaded from AppCertDLLs against threat intelligence feeds and malware databases. Review recent registry changes and correlate with known patches or legitimate application updates. |
| T2 Analyst Actions | Conduct a deeper inspection of the suspect DLL by reverse engineering to determine malicious intent. Assess the integrity of affected systems by examining changes in system behavior, unexpected network connections, or other artifacts indicative of persistence mechanisms. Analyze system and network activity around the time of DLL loading events for lateral movement or data exfiltration behaviors. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent lateral movement. Remove or remediate any unauthorized DLLs loaded via AppCertDLLs. Execute a full system scan with updated antivirus signatures. Engage digital forensics to capture and analyze memory dumps to identify intrusions or indicators of compromise not visible in traditional logs. |
