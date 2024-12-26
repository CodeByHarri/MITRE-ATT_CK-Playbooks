# Credentials_from_Password_Stores - T1555

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1555 |
| MITRE Sub-TTP | T1555 |
| Name | Credentials from Password Stores |
| Log Sources to Investigate | Examine logs from Endpoint Detection and Response (EDR) tools to identify access attempts on password store locations. Review Windows Event Logs, particularly those related to processes and accessing sensitive directories. Check logs from password managers and cloud secrets vaults for unauthorized access patterns. Review application logs for unexpected login attempts or access patterns. |
| Key Indicators | Unusual access attempts to known password storage directories, such as the Windows Credential Manager or specific locations where password managers store their data. Unscheduled access to cloud-based secret vaults or unusual API calls accessing credential stores. |
| Questions for Analysis | 1. Was there a legitimate need for accessing the password stores during the timeframe in question?<br>2. Are there known legitimate applications that should be interacting with the password store at the time of the event?<br>3. Has the account accessing the password stores shown signs of compromise like failed logins from unusual IP addresses? |
| Decision for Escalation | Escalate if there is evidence of unauthorized access to password stores or credential dumping techniques. Also escalate if the investigation reveals access from anomalous locations or new, unexplained processes interacting with sensitive storage areas. |
| Additional Analysis Steps for L1 | Verify if the process and user account involved in accessing the password store are consistent with normal activity. Review recent access attempts and correlate with user activity to spot anomalies. Check for any subsequent suspicious behavior indicating lateral movement attempts. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the accessed system, focusing on process snapshots and memory dumps. Review network logs to identify any data exfiltration activities. Validate if related compromised credentials have been used on other systems. |
| Containment and Further Analysis | If unauthorized access is confirmed, immediately disconnect the affected system from the network to prevent further data leaks. Reset credentials for affected users and invalidate any compromised tokens or keys. Conduct a comprehensive review of access logs to identify other potential breaches and strengthen access controls around password stores. |
