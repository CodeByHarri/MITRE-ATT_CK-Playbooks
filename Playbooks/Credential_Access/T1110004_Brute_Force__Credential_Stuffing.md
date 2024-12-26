# Brute_Force:_Credential_Stuffing - T1110004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1110.004 |
| MITRE Sub-TTP | T1110.004 |
| Name | Brute Force: Credential Stuffing |
| Log Sources to Investigate | Investigate authentication logs from identity providers, web access logs, VPN access logs, and application logs for attempted logins. These may include logs from services like SSH, Telnet, FTP, SMB, LDAP, Kerberos, RDP, HTTP/HTTPS, MSSQL, Oracle, MySQL, and VNC. Specifically focus on login attempts showing the same username across multiple IP addresses or high volumes of failed login attempts. |
| Key Indicators | 1. Multiple failed login attempts for a single account from various IP addresses.<br>2. Unusual login times compared to user behavior baselines.<br>3. Access attempts from IP addresses with no prior login history.<br>4. Use of common usernames such as 'admin', 'administrator', or 'root'.<br>5. High frequency of login attempts from single IP indicating automation. |
| Questions for Analysis | 1. Has this username/IP been involved in multiple failed login attempts recently?<br>2. Are login attempts happening from locations inconsistent with the user's typical patterns?<br>3. Is there a sudden spike in login attempts compared to normal activity volumes? |
| Decision for Escalation | Escalate to Tier 2 if logins are detected from known malicious IP addresses, or if multiple suspicious login attempts across various services are identified within a short time frame indicating automated attempts. |
| Additional Analysis Steps for L1 | 1. Verify if the user's IP location is within expected geographical patterns.<br>2. Cross-reference the attempting IP addresses with threat intelligence databases to check if they are known for malicious activities.<br>3. Check for any recent checks or attempts of the same credentials on breach databases. |
| T2 Analyst Actions | 1. Conduct a deeper investigation on new or unusual IPs attempting access.<br>2. Perform risk scoring of the affected account(s) based on historical patterns.<br>3. Assist in reviewing access logs across different systems to identify any leakage or misuse of credentials. |
| Containment and Further Analysis | 1. Temporarily disable the affected account(s) if breach is suspected.<br>2. Mandate password changes for affected users and possibly implement two-factor authentication.<br>3. Monitor further attempted logins from flagged IPs and/or usernames.<br>4. Analyze breach data for matching or similar username/passwords to prevent future incidents. |
