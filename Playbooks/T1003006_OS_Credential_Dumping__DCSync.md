# OS_Credential_Dumping:_DCSync - T1003006

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1003.006 |
| MITRE Sub-TTP | T1003.006 |
| Name | OS Credential Dumping: DCSync |
| Log Sources to Investigate | Collect and analyze logs from domain controllers, focusing on Security Event Logs, especially event IDs like 4662 (Access Logs), 4624 (Logon Events), and 4672 (Special Privilege Logon). Check for unusual access or replication requests using tools like Mimikatz through the 'lsadump::dcsync' module. Network traffic logs should also be reviewed for suspicious DC replication traffic from non-domain controllers. |
| Key Indicators | Unexpected replication requests in logs where the requestor is not a recognized domain controller. Sudden access to sensitive Active Directory data, particularly replication of credential data like KRBTGT accounts. Usage of known tools such as Mimikatz in the network, especially with modules related to DCSync activity. |
| Questions for Analysis | Is the source account authorized to initiate replication requests? Are the observed events consistent with legitimate administrative activity? Is there evidence of known vulnerability exploitation or indicators of compromise? Were any unexpected changes or replications noticed in KRBTGT or other high-value accounts? |
| Decision for Escalation | Escalate if unauthorized users or non-domain controller machines initiate replication requests. Escalate if there are logged events indicating access to or replication of sensitive AD data. Escalate upon detection of tool usage (e.g., Mimikatz) or anomalous account behavior. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the account used for initiating DCSync by corroborating with AD administrative logs. Cross-reference unusual replication activities with recent changes or permission grants in AD. Contact relevant administrators to confirm if the replication activity was authorized. |
| T2 Analyst Actions | Conduct a deeper investigation into compromised account indicators by reviewing related logs. Perform correlation analysis with other detected suspicious activities or lateral movements. Look for broader exposure or signs of privilege escalation. Confirm the credentials' integrity for AD critical accounts, especially KRBTGT and Administrator accounts. |
| Containment and Further Analysis | Restrict the compromised accounts and review their activity history. Reset the KRBTGT account password twice to invalidate any created Golden Tickets. Isolate affected systems and revoke any malicious access. Develop a recovery plan that includes patching vulnerabilities, strengthening AD security posture, and confirming all administrative activities are verified. Consider implementing enhanced monitoring using SIEM tools. |
