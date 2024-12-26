# Cloud_Service_Dashboard - T1538

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1538 |
| MITRE Sub-TTP | T1538 |
| Name | Cloud Service Dashboard |
| Log Sources to Investigate | Investigate cloud service provider logs, such as AWS CloudTrail, Azure Activity Logs, and Google Cloud Audit Logs for anomalous activity. Look for GUI login activities, especially logins from unfamiliar or foreign IP addresses, and access to cloud dashboards in services like the GCP Command Center. Pay special attention to login events that do not match typical user behavior patterns or logins outside of normal operating hours. |
| Key Indicators | Unusual login time; Access from IP addresses outside of expected geographical locations; Multiple failed login attempts followed by successful access; Access to high-sensitivity cloud dashboards like command centers; Reviewing information read activity focused on asset inventory, security findings, and querying service configurations. |
| Questions for Analysis | Did the login occur from an unusual IP address? Was the login attempt made outside typical hours? Is the user account associated with this login compromised previously? Was there a pattern of failed logins preceding the successful one? Are the accessed resources or actions unusual for this user role? |
| Decision for Escalation | Escalate to Tier 2 if logins are from atypical IP addresses or at unusual times without proper justification. Escalate if there is a mismatch between the user's usual role and the accessed resources or actions. Consider further analysis if there are indications of credential compromise such as multiple failed attempts followed by a successful login. |
| Additional Analysis Steps for L1 | Verify the legitimacy of IP addresses and geographical locations associated with the login; Check if the user credentials were part of any recent breach; Review access patterns for the last 30 days to establish normal behavior; Confirm if the actions are aligned with legitimate business needs by reaching out to the user or their manager. |
| T2 Analyst Actions | Conduct a deeper investigation by correlating this dashboard access with other suspicious activities such as data exfiltration attempts; Analyze whether the access aligns with legitimate workflows as documented by the organization. Confirm whether accessed information could facilitate lateral movement or privilege escalation; Engage with stakeholders in IT security to evaluate if further inquiries are warranted. |
| Containment and Further Analysis | If unauthorized access is confirmed, immediately disable the compromised credentials and force a password reset. Review and potentially revoke permissions for any overly privileged accounts. Conduct a broader audit of all accounts for similar suspicious behavior. Consider implementing multi-factor authentication if not already present to strengthen access control. |
