# Access_Token_Manipulation:_Parent_PID_Spoofing - T1134004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1134.004 |
| MITRE Sub-TTP | T1134.004 |
| Name | Access Token Manipulation: Parent PID Spoofing |
| Log Sources to Investigate | Investigate Windows Event Logs, specifically Security logs (Event ID 4688 for process creation), and Sysmon logs (Event ID 1 for process creation with a parent PID field). Examine EDR solutions logs for process spawning details, focusing on unusual parent-child process relationships. Additionally, review logs from PowerShell or other scripting engines if they are involved. |
| Key Indicators | Look for processes where common applications like PowerShell or Rundll32 have a parent process of explorer.exe rather than more expected parents like Office applications (e.g., winword.exe or excel.exe). Anomalous parent-child relationships, especially involving SYSTEM level processes as the parent when not typical, and the use of CreateProcess API with explicit PPID manipulation are key signs. |
| Questions for Analysis | Does the timeline or sequence of the process creation make contextually inappropriate parent-child relationships? Are there legitimate reasons for the processes in question to start with the observed parent process? Is there evidence of recent spearphishing activities or executables delivered via email? |
| Decision for Escalation | Escalate if there are no legitimate explanations for the process relationships, if SYSTEM level processes are being spoofed without proper justification, or if related user accounts exhibit anomalous behaviors or source addresses. Analyze based on internal threat intelligence or past incidents. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the process parent-child relationship with the user and IT admin. Cross-check against known good baselines of process trees. Investigate if there are any recent spearphishing campaigns, and verify process creation details using external threat intelligence sources. |
| T2 Analyst Actions | Perform a deeper investigation into the execution context of the process using memory analysis or forensic tools. Correlate with other events or alerts involving the same system or user. Examine historical logs for previous instances of similar behavior. |
| Containment and Further Analysis | Contain affected systems by isolating them from the network. Examine impacted accounts and consider forced password changes if necessary. Check for additional signs of lateral movement or persistence mechanisms. Conduct a detailed audit of system changes and create patch management schedules if needed. Engage with incident response teams for a tailored remediation plan. |
