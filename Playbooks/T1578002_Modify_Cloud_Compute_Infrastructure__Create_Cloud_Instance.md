# Modify_Cloud_Compute_Infrastructure:_Create_Cloud_Instance - T1578002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1578.002 |
| MITRE Sub-TTP | T1578.002 |
| Name | Modify Cloud Compute Infrastructure: Create Cloud Instance |
| Log Sources to Investigate | Cloud Service Provider (CSP) logs, such as AWS CloudTrail, Azure Activity Logs, or Google Cloud Audit Logs. Specifically, look for events related to 'RunInstances' or 'Insert VM' API calls. Review IAM Authentication logs to check which accounts or roles initiated the instance creation. Also, monitor configuration changes in firewall or security group rules. |
| Key Indicators | Unusual instance creation events, especially from accounts that typically do not perform this action. API requests from unfamiliar IP addresses or regions. Sudden changes in firewall rules or access permissions followed by a new instance launch. High volume of data read/write from unfamiliar instances. |
| Questions for Analysis | Was the instance creation initiated by a known and authorized user? Was it created during regular business hours? Did the action come from a recognized IP address or geographic location? Are there signs of additional suspicious changes like altered security groups? |
| Decision for Escalation | Escalate to Tier 2 if the instance creation is unauthorized, associated IP address is unfamiliar, or if there are concurrent suspicious events like unusual data transfers, changes in permissions, or non-standard activity times. |
| Additional Analysis Steps for L1 | Verify the user account used for creating the instance and check its recent activity logs. Confirm if the new instance is listed in any recent official capacity upgrade requests or projects. Check other activities from the same IP or user for anomalies. |
| T2 Analyst Actions | Perform a deeper audit of the user's recent activity, including any changes to permissions or security configurations. Correlate with any known threat intelligence on similar activities or IP addresses. Conduct a risk analysis of the new instance's access level and network reach. |
| Containment and Further Analysis | If unauthorized, isolate the new instance by adjusting firewall and security rules. Terminate if confirmed malicious. Ensure logging and monitoring are heightened for future instance creation events. Conduct a formal security review and engage with the relevant team to mitigate further access or configuration issues. |
