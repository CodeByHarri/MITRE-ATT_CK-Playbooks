# Modify_Registry - T1112

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1112 |
| MITRE Sub-TTP | T1112 |
| Name | Modify Registry |
| Log Sources to Investigate | 1. Windows Event Logs: Look for Security Event IDs 4657 and 4663 for registry key and value modifications.<br>2. Sysmon Logs: Check for Event ID 13 that indicates registry object modifications by processes.<br>3. PowerShell Logs: Monitor for unexpected use of Reg.exe or Windows API calls to modify the registry. 4. Endpoint Detection and Response (EDR) Tools: Identify changes in registry entries, especially in persistence locations like HKLM\Software\Microsoft\Windows\CurrentVersion\Run. 5. Network Logs: Examine SMB traffic to identify remote registry modification attempts. |
| Key Indicators | 1. Unauthorized registry changes, especially in startup keys.<br>2. Use of Reg.exe by non-administrative accounts.<br>3. Frequent attempts to access HKLM and HKCU hives. 4. Registry entries with null character prefixes. 5. Unusual remote registry modifications over SMB. |
| Questions for Analysis | 1. Was the registry modification initiated by a known administrative account?<br>2. Is there a legitimate business reason for recent registry changes?<br>3. Does Reg.exe or a related utility appear in process logs around the time of registry modifications? 4. Are there associated SMB or RPC logs indicating lateral movement attempts? |
| Decision for Escalation | Escalate to Tier 2 when: 1. Registry changes occur outside of maintenance windows.<br>2. Modifications are tied to non-standard accounts or abnormal process executions.<br>3. Indicators suggest potential lateral movement or persistence establishment. |
| Additional Analysis Steps for L1 | 1. Correlate the registry modification with user and process activity within the same timeframe.<br>2. Verify the legitimacy of any registry changes by consulting change management records.<br>3. Investigate historical trends in registry modifications for anomalous patterns. |
| T2 Analyst Actions | 1. Conduct a deeper investigation into the process and network activities surrounding the modification.<br>2. Review related security logs for patterns of intrusion or other suspicious behavior.<br>3. Analyze any associated artifacts or new binaries on the system. 4. Engage in memory forensics if necessary to identify in-memory threats. |
| Containment and Further Analysis | 1. Isolate affected systems from the network if unauthorized changes are verified.<br>2. Remove or revert unauthorized registry changes and monitor for re-occurrence.<br>3. Perform a thorough malware scan using advanced endpoint protection tools. 4. Consider resetting credentials if valid accounts were used for unauthorized activity. 5. Report findings to incident response for comprehensive threat assessment and mitigation. |
