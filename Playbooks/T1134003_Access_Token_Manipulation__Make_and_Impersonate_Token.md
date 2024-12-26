# Access_Token_Manipulation:_Make_and_Impersonate_Token - T1134003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1134.003 |
| MITRE Sub-TTP | T1134.003 |
| Name | Access Token Manipulation: Make and Impersonate Token |
| Log Sources to Investigate | Monitor Security Event Logs, specifically Windows Security Event ID 4672 (Special privileges assigned to new logon) and Event ID 5140 (A network share object was accessed). Pay attention to logon events where a logon session is created (Event ID 4624) with types indicative of network or remote interactive. Track usage of the `LogonUser` and `SetThreadToken` functions through process auditing, capturing detailed command line usage where available. |
| Key Indicators | Unusual creation of logon sessions without corresponding user interactive logon activity. Usage of `LogonUser` function with privilege assignment. Abnormal token creation and assignment to threads related to privilege escalation. Look for unusual patterns or timings for these actions, which may not align with standard user behavior. |
| Questions for Analysis | Is there any known or expected activity from this user account at the time the token was created? Does the account have a history of logging in from the source machine observed in the logs? Are there any other suspicious activities surrounding the same timeframe, such as file access or suspicious process execution? |
| Decision for Escalation | Escalate if the token creation and impersonation activities are unexpected for the user's typical behavior, or if they are associated with privileged accounts. Additionally, escalate if this activity coincides with data exfiltration attempts or anomalous network access. |
| Additional Analysis Steps for L1 | Correlate events related to the newly created token with any subsequent access or modifications to sensitive resources. Cross-reference with user input logs or applications running under the context of that user. Validate if the account is compromised by checking for open sessions or unusual login anomalies. |
| T2 Analyst Actions | Perform a detailed historical analysis of the user account activities and track access patterns over the last few weeks. Forensically examine any systems accessed using the token for signs of lateral movement or pivoting. Verify if any known vulnerabilities could have been exploited to facilitate token creation and impersonation. |
| Containment and Further Analysis | Immediately disable or restrict compromised accounts and conduct a password change. Isolate affected systems for in-depth analysis. Conduct a full investigation and vulnerability assessment to identify any exploitation methods used. Implement additional monitoring on the network for further signs of malicious activity and strengthen authentication mechanisms to prevent reoccurrence. |
