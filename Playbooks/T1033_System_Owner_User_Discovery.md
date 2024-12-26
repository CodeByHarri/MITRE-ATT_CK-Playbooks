# System_Owner_User_Discovery - T1033

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1033 |
| MITRE Sub-TTP | T1033 |
| Name | System Owner/User Discovery |
| Log Sources to Investigate | For detection of T1033 - System Owner/User Discovery, focus on logs that capture user account activities such as Windows Security Event Log (Event IDs 4624, 4798, 4800, etc.), authentication logs on Linux/macOS systems, and command-line auditing logs. Network device logs capturing CLI commands like 'show users' or 'show ssh'. Additionally, monitor SIEM alerts from operating system and endpoint detection tools that include process execution events and environment variable access. |
| Key Indicators | Look for unusual patterns or times of account enumeration activity, such as the use of commands like 'whoami', 'w', 'who', 'dscl', 'show users', and 'show ssh' outside of normal administrative operation hours. Identify spikes or anomalies in the execution of these commands, particularly when executed by non-administrative users. |
| Questions for Analysis | Is the user account executing the command typically involved in system administration tasks? Did the command execution occur outside of normal business hours or usage patterns? Are there any associated failed login attempts or unusual authentication events in the surrounding timeframe? Are there any lateral movement indicators or signs of privilege escalation attempts? |
| Decision for Escalation | Escalate to Tier 2 if the execution of discovery commands is confirmed to be performed by non-administrative users, during unusual times, or if there is other co-occurring suspicious activity such as privilege escalation or lateral movement attempts. Escalate if commands are executed in environments where they are seldom used. |
| Additional Analysis Steps for L1 | Verify execution context for the detected commands: cross-reference with user roles and typical activity. Review recent system access logs and correlate them with any suspicious patterns or anomalies in behavior. Check for any newly created accounts or account changes in the active directory. |
| T2 Analyst Actions | Conduct deeper analysis on the user's activity across hosts and evaluate for potential compromise. Review associated network traffic for unusual data exfiltration or command-control communication. Perform account review and validation with the original user or organizational point of contact if needed. Utilize threat intelligence to cross-reference with known actor behaviors. |
| Containment and Further Analysis | If unauthorized user discovery is confirmed, isolate the affected systems to prevent further unauthorized actions. Reset credentials and review all associated user accounts and permissions. Enhance logging and monitoring around user account activity. Conduct a full investigation to determine if other systems were compromised using similar tactics. |
