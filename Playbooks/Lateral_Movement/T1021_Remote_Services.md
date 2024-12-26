# Remote_Services - T1021

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Lateral Movement |
| MITRE TTP | T1021 |
| MITRE Sub-TTP | T1021 |
| Name | Remote Services |
| Log Sources to Investigate | Network logs capturing remote connection attempts, such as SSH, RDP, and VNC logs. Examples include Windows Event Logs for Terminal Services (Event ID 4624 for logons and 4625 for failures), Linux auth logs (/var/log/auth.log) for SSH connections, and logs from centralized authentication systems like Active Directory or LDAP. Additionally, SaaS application access logs and cloud infrastructure provider logs should be reviewed, especially if federated authentication is used. |
| Key Indicators | Unusual or unexpected remote login attempts, especially those using valid domain credentials from atypical locations or at unusual times. Login attempts from previously unseen IP addresses, or IPs known to be associated with malicious activity. Multiple login attempts from a single account in short succession, especially if moving laterally across multiple hosts. |
| Questions for Analysis | Is the source IP of the login considered normal for the user or system? Is the timing of the login consistent with the user's typical behavior? Are there multiple failed login attempts before a successful one? Has the account been used to log into other services or systems without prior precedence? |
| Decision for Escalation | Escalate if logins occur from known malicious IP addresses, if there is evidence of brute force access attempts, or if sensitive or critical systems are accessed by accounts with no prior history. Additionally, escalate if multiple systems or services are being accessed outside of known patterns. |
| Additional Analysis Steps for L1 | Verify the authenticity of the account being used by confirming recent activities with the account owner. Check for any user-reported issues or recent password changes. Gather information on the IP address and geographical location associated with the login attempt to determine if it aligns with the user's regular pattern. |
| T2 Analyst Actions | Conduct a deeper investigation into the logs, including cross-referencing with threat intelligence databases for the IPs involved. Look for correlated events in network traffic or endpoint detection systems that might indicate further compromise. Review additional logs for any signs of lateral movement or data access. |
| Containment and Further Analysis | If a compromise is confirmed, disable the affected accounts and any associated sessions immediately. Engage with IT to isolate affected systems from the network. Conduct a full forensic analysis of affected systems to determine the extent of the breach and whether any data exfiltration has occurred. Ensure all remote service configurations are reviewed and hardened to prevent future unauthorized access. |
