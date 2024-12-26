# System_Binary_Proxy_Execution:_Regsvcs_Regasm - T1218009

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1218.009 |
| MITRE Sub-TTP | T1218.009 |
| Name | System Binary Proxy Execution: Regsvcs/Regasm |
| Log Sources to Investigate | Monitor process creation logs for the execution of regsvcs.exe and regasm.exe, particularly under unusual user accounts or at atypical times. Windows Event Logs (Event ID 4688 for command execution) and Sysmon logs should be scrutinized. Look for command lines indicating the use of [ComRegisterFunction] or [ComUnregisterFunction] attributes. EDR solutions can provide visibility into process executions and network connections initiated by these binaries. |
| Key Indicators | Unusual execution of regsvcs.exe or regasm.exe, especially under non-administrative accounts. Look for command line arguments that include references to [ComRegisterFunction] or [ComUnregisterFunction]. Check for persistence mechanisms being established or suspicious network connections originating from these processes. |
| Questions for Analysis | Was the execution of regsvcs.exe or regasm.exe expected or scheduled? Was it executed by a legitimate user, or does it coincide with other suspicious behaviors like new file creations or network connections? Are there any known legitimate software deployments or updates that may account for their usage? |
| Decision for Escalation | Escalate if regsvcs.exe or regasm.exe is executed under suspicious circumstances, such as being triggered by untrusted users or at unusual times, or if they are part of a broader pattern of anomalous behavior indicating potential compromise. |
| Additional Analysis Steps for L1 | Verify if there are legitimate reasons or approved software installations that justify the execution of regsvcs or regasm. Check related file creation and modification events for suspicious activity. Cross-reference actions with known threats in threat intelligence databases. |
| T2 Analyst Actions | Perform deeper investigation of the origin of regsvcs or regasm execution. Analyze associated files for malicious content. Utilize threat intelligence to determine if similar TTPs have been observed in recent campaigns. Assess network logs to identify and stop any potentially malicious outbound communication. |
| Containment and Further Analysis | Isolate the affected system to prevent potential lateral movement. Block identified malicious indicators at network and host levels. Conduct a comprehensive forensic analysis of the device to trace back adversary actions and assess potential data exposure. Engage with IT to clean or re-image the system as necessary. |
