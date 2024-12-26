# Modify_Cloud_Compute_Infrastructure:_Create_Snapshot - T1578001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1578.001 |
| MITRE Sub-TTP | T1578.001 |
| Name | Modify Cloud Compute Infrastructure: Create Snapshot |
| Log Sources to Investigate | Cloud service provider logs (e.g., AWS CloudTrail, Azure Activity Logs, Google Cloud Audit Logs) that capture snapshot creation events. Review access logs to monitor API calls related to snapshot management, especially 'CreateSnapshot' or equivalent operations. |
| Key Indicators | Unusual or unauthorized 'CreateSnapshot' API calls. Repeated snapshot creation outside typical business hours. Snapshot creation by non-standard users or service accounts. Rapid successive API calls related to snapshot operations. |
| Questions for Analysis | Was the 'CreateSnapshot' activity performed by an account with a history of such actions? Are there associated login anomalies with the account involved in the snapshot creation? Did the event occur during regular operational hours, or does it stand out? Are there any known vulnerabilities or excessive permissions associated with the account? |
| Decision for Escalation | Escalate to Tier 2 if the snapshot was created by an unfamiliar account, or if the action is linked with other suspicious activities like privilege escalation, unusual access times, or known compromised accounts. |
| Additional Analysis Steps for L1 | Verify the account responsible for the action and cross-reference it with past actions. Check if there are other associated anomalies, like multiple failed login attempts. Confirm the legitimacy of the activity by cross-referencing with ticketing systems or direct communication with relevant stakeholders. |
| T2 Analyst Actions | Conduct deeper analysis on the user's recent activity and permissions. Validate any changes in firewall rules or network configurations post-snapshot creation. Engage with the cloud infrastructure team to explore any discrepancies in the expected vs. actual usage of resources. |
| Containment and Further Analysis | Revoke snapshot creation permissions for suspicious accounts. Review and tighten roles and permissions associated with creating snapshots. Implement monitoring for all snapshot activities and establish a baseline for normal operations. Conduct a deeper investigation into any linked instances or VMs to ensure that no further compromise has occurred. |
