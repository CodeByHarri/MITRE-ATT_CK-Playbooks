# File_and_Directory_Permissions_Modification:_Windows_File_and_Directory_Permissions_Modification - T1222001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1222.001 |
| MITRE Sub-TTP | T1222.001 |
| Name | File and Directory Permissions Modification: Windows File and Directory Permissions Modification |
| Log Sources to Investigate | Investigate Windows Security Event Logs, especially Event ID 4670 (Permissions on an object were changed) and Event ID 5145 (A network share object was accessed). Check Windows PowerShell logs for cmdlets related to DACL changes. File access logs and audit logs where DACL changes are tracked can also be important. Additionally, monitor command line activity logs for suspicious commands like `icacls`, `cacls`, `takeown`, and `attrib`. |
| Key Indicators | Unusual or unauthorized modification of file and directory ACLs, especially if performed by non-admin users. Execution of commands like `icacls` and `takeown` on sensitive directories. Spike in file access attempts following permission changes. Use of PowerShell scripts or cmdlets to modify DACLs. |
| Questions for Analysis | Was the permission modification authorized or part of a known administrative task? Are the changes consistent with the behavior of legitimate users? Are there other suspicious activities correlating with the identified permission modifications (e.g., new user accounts, unexpected file deletions, or new processes running)? Has there been an unexpected spike in access attempts following these changes? |
| Decision for Escalation | Escalate to Tier 2 if permission changes are unauthorized, correlate with other suspicious activities, or are executed by non-admin users on sensitive files/directories. Also, escalate if there's evidence of privilege escalation attempts or potentially compromised user accounts. |
| Additional Analysis Steps for L1 | Validate the user's identity and typical behavior patterns. Correlate permission change events with recent changes in user roles or group memberships. Check for recent administrative tasks or scheduled operations that may justify the changes. Alert on commands like `icacls`, `takeown`, and their context of execution. |
| T2 Analyst Actions | Perform a deeper investigation into the user's activity who made the changes. Review associated logs for any anomalous patterns or linked events. Analyze file access patterns to ensure no unauthorized access followed the DACL changes. Confirm if change matches documented change management activities. |
| Containment and Further Analysis | If unauthorized changes are confirmed, revert DACL changes to their original state. Isolate the host if there are signs of compromise. Initiate a thorough endpoint investigation to check for other signs of compromise (e.g., unexpected processes, network connections). Report findings to risk management and initiate end-user awareness if necessary to prevent future occurrences. |
