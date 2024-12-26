# Valid_Accounts:_Local_Accounts - T1078003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Initial Access, Persistence, Privilege Escalation |
| MITRE TTP | T1078.003 |
| MITRE Sub-TTP | T1078.003 |
| Name | Valid Accounts: Local Accounts |
| Log Sources to Investigate | Investigate logs from Windows Security Event Logs (specifically Event IDs 4624, 4625 for logon attempts; 4720, 4722, 4723, 4724 for account management events), Sysmon logs for process creation (Event ID 1), and authentication logs from Active Directory Domain Controllers. Also, review endpoint security logs and EDR solutions for suspicious local account use. |
| Key Indicators | Look for unusual logon activities from local accounts outside of normal operating hours or from unfamiliar locations, multiple failed logon attempts indicating a brute force attempt, new local accounts being created without proper authorization, and unusual privilege escalation attempts. |
| Questions for Analysis | Has this local account exhibited suspicious behavior previously? Are there multiple failed logon attempts recorded for this account? Is the access attempt coming from an unusual location or endpoint? Does the account have recent changes in privilege or being used for lateral movement on the network? |
| Decision for Escalation | Escalate to Tier 2 if there are confirmed unauthorized access attempts from unusual locations or times, repeated small-scale brute force attempts on local accounts, unauthorized privilege escalation activities, or if the account was used for further malicious activity such as lateral movement. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the logged activities by cross-referencing the suspicious logon events with approved backup or support access logs. Ensure that user activity patterns match known patterns for the specific user or role, and correlate account activities with network flow logs for unusual traffic. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the endpoint to look for signs of credential dumping or malware. Review network traffic from the time of the suspicious logon for signs of lateral movement. Identify and interview users associated with the account to rule out false positives and confirm suspicious activities. |
| Containment and Further Analysis | Isolate affected systems to prevent further unauthorized access. Reset the compromised local accounts' passwords. Block any IP addresses or domains associated with suspicious access attempts. Conduct a full review of the affected system for unknown software or scheduled tasks that could indicate persistence mechanisms. Review network security policies to limit local account privileges and improve monitoring. |
