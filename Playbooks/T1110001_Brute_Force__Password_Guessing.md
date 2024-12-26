# Brute_Force:_Password_Guessing - T1110001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1110.001 |
| MITRE Sub-TTP | T1110.001 |
| Name | Brute Force: Password Guessing |
| Log Sources to Investigate | Event logs from authentication systems such as Windows Security Event Logs, which capture login attempts and failures (e.g., Event ID 4625 for failed logon attempts). Network firewall and intrusion detection system (IDS) logs for traffic patterns on commonly targeted ports like 22 (SSH), 3389 (RDP), 445 (SMB). Application logs from services such as SSH, RDP, HTTP servers, and databases that may capture authentication attempts. Cloud services logs, especially if federated authentication is used (e.g., Azure AD Sign-in logs for Office 365). |
| Key Indicators | Multiple authentication failures from a single IP address over a short period. Authentication attempts on accounts not typically accessed by the source IP. Unexpected access attempts on sensitive accounts or services. Authentication attempts outside of normal business hours. Patterns indicating systematic attempts (e.g., sequential username or password attempts). |
| Questions for Analysis | Are there multiple failed login attempts from the same IP address or against the same account? Are the login attempts targeting sensitive accounts or services? Do these login attempts originate from known or expected sources? Are there any successful logins following repeated failures? Are the attempts occurring during off-peak hours or geographically disparate locations? |
| Decision for Escalation | Escalate to Tier 2 if there are concurrent failed login attempts across multiple accounts or services. Escalate if there is evidence of successful logins post multiple failures, especially on sensitive accounts. Escalate if the source IP address is external and unusual based on geolocation or blacklists. |
| Additional Analysis Steps for L1 | Correlate login attempts with current travel or remote work policies if applicable. Verify if the source IP is part of a known VPN or proxy service. Check for any alerts or blocks set by network security tools on the source IP. Look for patterns of behavior aligning with regular automated attacks. |
| T2 Analyst Actions | Conduct a deeper analysis of the source IP addresses for historical malicious activity. Correlate failed attempts with other threat intelligence sources. Review user and entity behavior analytics (UEBA) for anomalies. Collaborate with IT to verify legitimate access scenarios, such as new employees or organizational changes. |
| Containment and Further Analysis | Implement temporary access control measures like account lockouts for impacted accounts. Notify affected users and follow up with password resets or 2FA implementations. Enhance monitoring of the perimeter for additional patterns or new attack vectors. Review and potentially tighten login attempt policies on critical services. |
