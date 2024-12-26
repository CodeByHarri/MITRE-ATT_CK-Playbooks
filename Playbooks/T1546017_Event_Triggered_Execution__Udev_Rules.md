# Event_Triggered_Execution:_Udev_Rules - T1546017

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1546.017 |
| MITRE Sub-TTP | T1546.017 |
| Name | Event Triggered Execution: Udev Rules |
| Log Sources to Investigate | Monitor log files associated with udev and system services, particularly from system logs like '/var/log/syslog', '/var/log/messages', and any logs related to systemd-udevd. Check for any unauthorized changes to files within '/etc/udev/rules.d/', '/run/udev/rules.d/', and similar directories. Use file integrity monitoring solutions to track changes to udev rules and directories. |
| Key Indicators | 1. Creation or modification of udev rule files with suspicious or unexpected actions within directories such as '/etc/udev/rules.d/'.<br>2. Unusual processes initiated by the udev system, especially those that do not typically interact with device events.<br>3. Use of commands or binaries in 'RUN+=' fields within udev rules that do not align with normal operational requirements. |
| Questions for Analysis | 1. Are there recent modifications to udev rule files that correspond with suspicious activity or timings?<br>2. Do the actions specified in the udev rules match expected administrative activities?<br>3. Is there evidence of unauthorized access to or modification of udev directories? 4. Were there any new or unauthorized device events triggering the rules? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized modifications to udev rule files are detected or if associated scripts or binaries appear malicious or unfamiliar. Escalate if there is evidence of lateral movement or further persistence tactics. |
| Additional Analysis Steps for L1 | 1. Verify recent changes to udev rule files through system log correlation.<br>2. Cross-reference any changes with recent admin tasks or maintenance windows.<br>3. Check access logs for unauthorized users accessing critical directories. 4. Look for any unusual or repetitive invocation of udev-triggered processes. |
| T2 Analyst Actions | 1. Conduct a deeper inspection of modified udev rule files to identify malicious content.<br>2. Analyze associated scripts/binaries for signs of malicious activity using static and dynamic analysis tools.<br>3. Assess whether the modified rules could lead to elevation of privileges or pivoting to other network resources. |
| Containment and Further Analysis | 1. Immediately isolate any identified malicious binaries or scripts involved in the attack.<br>2. Restore affected udev rule files from a known good backup.<br>3. Monitor the system for subsequent unauthorized accesses or changes to sensitive directories. 4. Consider the use of enhanced monitoring through EDR solutions for future detections of similar activities. Further analyze network traffic and correlate events if the malicious processes attempted external communication. |
