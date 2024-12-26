# Boot_or_Logon_Initialization_Scripts:_RC_Scripts - T1037004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1037.004 |
| MITRE Sub-TTP | T1037.004 |
| Name | Boot or Logon Initialization Scripts: RC Scripts |
| Log Sources to Investigate | Monitor file access logs and configuration changes on RC scripts such as /etc/rc.local, /etc/rc.common, and similar, depending on the Unix-like distribution. Investigate command history logs for any unusual modifications and systemd logs for those distributions that support backwards compatibility. The presence of unexpected modifications, especially from user accounts with fewer privileges, can indicate compromise. Consider using OSSEC or similar tools to track RC file integrity. |
| Key Indicators | Look for unauthorized changes in the timestamps or content of RC scripts. Note the presence of unexpected or non-standard file paths or binary names. Detect any addition of unusual shell commands, especially scripts that may be attempting to connect to external IP addresses immediately upon startup. |
| Questions for Analysis | Has there been any recent administrative activity that could explain the change? Are there any scheduled tasks or established IT processes that modify these files? Do the macOS versions still support RC scripts, and are they properly configured not to execute them? Can any deviations in the file's change history be correlated with suspicious IP addresses or user activity? |
| Decision for Escalation | Escalate to Tier 2 if file changes are detected that do not align with other concurrent system changes or expected administrative tasks, or if modifications persist after they have been reverted. Escalate immediately if suspicious binaries aiming for persistence are detected. |
| Additional Analysis Steps for L1 | Correlate log entries with user activity records to identify the origin of change. Restore the scripts to a previous known good state and verify any repeated attempts on modifications. Execute hash checks of the binaries being pointed to by the modifications. |
| T2 Analyst Actions | Perform a deeper investigation into the origins of the change, analyzing the altered script files to identify any malicious payloads. Use network monitoring tools to detect outbound connections that coincide with system startup. Conduct a comprehensive review of the last known good state of the system files versus current configurations. |
| Containment and Further Analysis | Revert changes to RC scripts or eliminate malicious entries. Enforce stricter file permissions to prevent unauthorized access. Configure use of tools such as AppArmor or SELinux for stronger runtime security policies. If identified, isolate affected systems from the network to prevent lateral movement. Implement monitoring for unusual startup activity post-cleanup, and conduct user awareness training if human factors are identified. |
