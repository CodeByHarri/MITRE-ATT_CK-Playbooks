# Command_and_Scripting_Interpreter:_Visual_Basic - T1059005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1059.005 |
| MITRE Sub-TTP | T1059.005 |
| Name | Command and Scripting Interpreter: Visual Basic |
| Log Sources to Investigate | Collect and analyze Windows Event Logs, specifically Event IDs related to script execution such as 4104 (Powershell script block logging), 4688 (Process Creation) especially for CScript or WScript processes, and 4103 (Module logging). Review Microsoft Office applications logs for macros execution if VBA is involved. Network traffic logs should be checked for unusual connections initiated by scripting processes. Endpoint Detection and Response (EDR) solutions should provide telemetry on script execution, parent-child process chains, and context around suspicious activities. |
| Key Indicators | Look for odd instances of script engine process executions such as CScript.exe or WScript.exe, especially when sourced from unusual parent processes or paths. VBScript being launched from unexpected directories, or VBA macros executing shells or external applications within Office documents. Network indicators include outbound connections from script engines or Office applications to unusual or malicious domains/IPs. |
| Questions for Analysis | 1. Is the VBScript/VBA macro execution aligned with user behavior or a regular activity?<br>2. Are there any legitimate use cases or business applications justifying this execution?<br>3. Is there evidence of suspicious network activity in conjunction with the script execution? 4. Are there any known vulnerabilities within the system or software that can be exploited using VB/VBA? |
| Decision for Escalation | Escalate to Tier 2 if script execution is from an unfamiliar or unauthorized source, if there are associated malicious or suspicious network activities (e.g., reaching out to known malicious IPs/domains), or if potential sensitive data access is observed post-execution. Also, escalate if the user is unaware or disclaims initiating the action leading to the script execution. |
| Additional Analysis Steps for L1 | Check whether the use of VBScript/VBA aligns with known and verified business practices. Validate security controls like antivirus and EDR signatures against the suspected script parts. Review the user's activity logs for evidence of targeted phishing or suspicious behavior preceding the script execution. |
| T2 Analyst Actions | Deep dive into the scripting execution detail, validate the script content, and perform static and dynamic analysis to determine purpose and impact. Cross-reference script-network behavior with threat intelligence for IOC matches. Interview end users to gather context and verify the legitimacy of the activity. |
| Containment and Further Analysis | If confirmed malicious, isolate affected endpoints and apply network segmentation to prevent lateral movement. Deploy or update antivirus and EDR signatures to detect and prevent similar execution. Conduct a full system scan to identify potential persistence mechanisms. Report findings to security operations for awareness and threat profiling, and perform a post-incident analysis to improve defenses. |