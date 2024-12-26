# Rogue_Domain_Controller - T1207

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1207 |
| MITRE Sub-TTP | T1207 |
| Name | Rogue Domain Controller |
| Log Sources to Investigate | Examine Domain Controller logs, focusing on changes to server and nTDSDSA objects, particularly in the Configuration partition. Review Windows Event Logs, specifically Directory Service logs (Event ID 1102 for unscheduled replication). Monitor network traffic logs for unusual replication patterns or connections to unauthorized DCs. Check Security Information and Event Management (SIEM) solutions for discrepancies in logged events that may indicate bypass or alteration. |
| Key Indicators | Creation of new server and nTDSDSA objects with timestamps matching administrator account activities. Unusual replication traffic between domain controllers, especially involving unknown or recently created DCs. Absence of expected log entries in SIEM for typical DC operations. Unauthorized changes in Active Directory schema or replication metadata. |
| Questions for Analysis | Are there any recent changes to the list of Domain Controllers that were not documented or approved? Has there been any unusual replication activity noted between known DCs? Are there audit logs showing suspicious administrative activities around the time the rogue DC was potentially registered? |
| Decision for Escalation | Escalate to Tier 2 if there is a confirmed unauthorized registration of a new DC, unexpected changes in replication metadata, or if there is corroborated evidence of bypassed security logs suggesting potential rogue DC activities. |
| Additional Analysis Steps for L1 | Conduct a preliminary check of all Domain Controllers via directory service logs to ensure they are all recognized and verified. Use basic network tools to verify the IP addresses and hostnames of all DCs to ensure they're legitimate. Correlate recent administrative activities across the network with the timing of any discovered anomalies. |
| T2 Analyst Actions | Utilize deeper forensic analysis tools to review changes in Active Directory schema and metadata. Verify the integrity of nTDSDSA objects and recent changes against backup or baseline configurations. Analyze any associated SID-History Injection patterns to determine potential persistence mechanisms. |
| Containment and Further Analysis | If a rogue DC is confirmed, immediately isolate it by disabling its network connectivity and removing its replication partners. Conduct a full security audit of domain permissions and restore any unauthorized changes using verified AD backups. Deploy additional monitoring on remaining DCs to watch for further unusual replication or changes. |
