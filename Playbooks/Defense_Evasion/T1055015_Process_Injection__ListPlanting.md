# Process_Injection:_ListPlanting - T1055015

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1055.015 |
| MITRE Sub-TTP | T1055.015 |
| Name | Process Injection: ListPlanting |
| Log Sources to Investigate | Investigate security logs from Endpoint Detection and Response (EDR) systems for process injection events, specifically looking for interactions with the SysListView32 control. Audit logs from Windows Event Viewer, focusing on API calls like FindWindow, EnumWindows, PostMessage, and SendMessage. Memory analysis logs from threat hunting tools, checking for suspicious memory allocations or code execution in unexpected processes. |
| Key Indicators | Unusual API calls involving list-view controls (e.g., FindWindow targeting SysListView32), unexpected memory allocations in non-standard processes, frequent PostMessage or SendMessage API usage with LVM_SETITEMPOSITION and LVM_SORTITEMS messages, execution of code from non-standard or newly allocated memory regions. |
| Questions for Analysis | Did the targeted process typically interact with list-view controls prior to the alert? Were any legitimate software updates or installations occurring at the time of the activity? Are there any known vulnerabilities in the process that could be leveraged for this method of injection? |
| Decision for Escalation | Escalate to Tier 2 if there are clear signs of unsanctioned memory changes or API calls in critical system processes. Also, escalate if the targeted process does not normally interact with list-view controls or if there are indications of newly executed code with no legitimate correlation to software updates or routine operations. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the processes involved using application whitelisting tools. Check for known good hashes and certificates for executed code. Investigate whether similar injection patterns have been detected in other systems or users in the organization. Compare the timeline of events with known legitimate activities like user actions or software updates. |
| T2 Analyst Actions | Perform a more detailed forensic analysis of the memory dumps of the affected systems. Utilize dynamic analysis tools to emulate and observe the behavior of the injected code, ensuring isolation from the rest of the environment. Research threat intelligence sources for any matching TTPs and lately identified IoCs. |
| Containment and Further Analysis | If a malicious injection is confirmed, isolate the affected host from the network to prevent further propagation. Revoke any suspicious code execution permissions and run a comprehensive malware scan using updated threat signatures. Forensic analysis should be performed to understand the entry vector and impact of the injected code, followed by remediation and patching of any exploited vulnerabilities. |
