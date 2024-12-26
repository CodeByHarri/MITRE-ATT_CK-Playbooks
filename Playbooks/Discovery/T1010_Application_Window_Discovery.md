# Application_Window_Discovery - T1010

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1010 |
| MITRE Sub-TTP | T1010 |
| Name | Application Window Discovery |
| Log Sources to Investigate | Monitor process creation logs, especially those invoking commands associated with window enumeration like 'tasklist', 'Get-Process', or WinAPI calls like 'FindWindow'. Security Event Logs, particularly those related to process execution and command line processes, can provide insight. Endpoint Detection and Response (EDR) tools often log API calls and script executions that might enumerate windows. |
| Key Indicators | Unusual process executions of command-line utilities or scripts querying window information, particularly by unknown or unauthorized users. Use of specific API functions related to window handling and enumeration, such as 'EnumWindows' or 'GetWindowText'. |
| Questions for Analysis | What process or application executed the window enumeration commands? Is the process typically associated with this behavior? Are there any known vulnerabilities or recent alerts connected to the system executing these commands? Is there an ongoing suspicious activity that correlates with these findings? |
| Decision for Escalation | Escalate to Tier 2 if the enumeration is not associated with normal operational processes, or if it has been executed by a user or service without the appropriate permission level. Suspicious patterns of multiple window enumeration attempts within a short period also warrant escalation. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the process executing enumeration activities by cross-referencing with known safe lists. Review recent login activities for unusual access patterns. Check for the presence of suspicious scripts or binaries in common directories. |
| T2 Analyst Actions | Conduct a deeper analysis of the process and parent-child relationships of suspicious applications involved in window enumeration. Investigate any persistence mechanisms that may suggest an adversary’s presence. Correlate findings with other security events such as failed login attempts or abnormal outbound traffic. |
| Containment and Further Analysis | Quarantine the system if indicators of unauthorized access are confirmed. Use forensic tools to image the device and preserve context for further investigation. Conduct root cause analysis to determine the origin of the enumeration commands. Consider enhancing endpoint monitoring and deploying enhanced logging for application window activities. |
