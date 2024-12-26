# Inter-Process_Communication:_Component_Object_Model - T1559001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1559.001 |
| MITRE Sub-TTP | T1559.001 |
| Name | Inter-Process Communication: Component Object Model |
| Log Sources to Investigate | Investigate Windows event logs, specifically 'Microsoft-Windows-Security-Auditing', looking at event IDs around process creation (e.g., 4688) and service changes (e.g., 7045). Check PowerShell logs for script execution, focusing on module logs (e.g., 4103 or 4104). Examine application logs for COM object interactions and ensure Sysmon logs are reviewed for process activity related to COM execution. Look into network traffic logs for signs of remote COM execution. |
| Key Indicators | An increase in 4688 logs indicating unusual COM server calls from unexpected processes. Sudden spikes in process activity involving `dllhost.exe`, `rundll32.exe`, or `svchost.exe` without clear justification. PowerShell scripts executing unusual COM objects as observed in event logs. Signs of `CLSID` registry reads or modifications indicating new or altered COM objects. |
| Questions for Analysis | Is the process initiating the COM object known and expected for this host? Are there any recent changes or updates to the software that might justify this activity? Are there any external communications associated with this COM activity, suggesting remote interaction? |
| Decision for Escalation | Escalate if COM object execution is tied to suspicious or unknown processes, particularly if associated with known malware indicators, atypical user accounts, or involving modifications to COM-related registry entries without a clear business context. |
| Additional Analysis Steps for L1 | Compare the initiating process paths with known application directories. Verify if the process owner is a legitimate or elevated user account. Cross-reference execution times with any known patching or software deployment activities. |
| T2 Analyst Actions | Perform deeper forensic analysis on the system using tools like Velociraptor or Mandiant's Redline. Cross-reference with threat intelligence to check for known malicious activity patterns. Look for persistence mechanisms tied to COM execution. |
| Containment and Further Analysis | Isolate the affected system if malicious activity is confirmed. Capture memory and disk images for further examination. Review other systems for similar COM activity to identify potential lateral movement or propagation. If needed, disable or restrict problematic COM objects via group policies or through registry changes, ensuring no disruption to legitimate business processes. |
