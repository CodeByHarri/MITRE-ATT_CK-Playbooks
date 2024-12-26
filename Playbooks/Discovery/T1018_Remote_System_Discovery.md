# Remote_System_Discovery - T1018

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1018 |
| MITRE Sub-TTP | T1018 |
| Name | Remote System Discovery |
| Log Sources to Investigate | Network traffic logs, Windows Event Logs (specifically Security and System logs), Linux system logs, logs from network devices, IDS/IPS logs, and DNS query logs. Examples include examining logs for unusual 'net view' or 'ping' usage, sudden increases in ARP requests or DNS queries, and commands executed on network devices that might indicate reconnaissance tasks such as 'show arp' or 'show cdp neighbors'. |
| Key Indicators | Presence of 'net view', 'ping', or equivalent commands executed with higher frequency than normal, unusual access patterns involving ARP cache, log entries from hosts executing commands targeting network infrastructure, and anomalous DNS queries that seek internal network systems. |
| Questions for Analysis | Have these commands been run by a legitimate user, or during non-standard hours? Are the commands reflective of typical user behavior? Is there an associated increase in failed lateral movement attempts? Are there any corresponding alerts from IDS/IPS regarding unexpected traffic patterns? |
| Decision for Escalation | Escalate to Tier 2 if there are multiple indicators of reconnaissance, such as repeated use of discovery tools accompanied by suspicious lateral movement attempts, or if any identified anomalies have no clear legitimate business justification or user authentication. |
| Additional Analysis Steps for L1 | Verify the time and context of any suspicious commands run from user endpoints. Check for any logged network connections to unknown or unusual IP addresses. Cross-reference logs for simultaneous activity from the same IP or user account. |
| T2 Analyst Actions | Conduct deeper analysis of network traffic patterns to identify potential lateral movement paths. Correlate the events from different log sources to piece together a timeline of activities. Investigate the originating user or system for historical anomalies or similar past activities. |
| Containment and Further Analysis | Isolate affected systems to prevent further unwanted network interactions. Implement network segmentation to restrict unauthorized access. Conduct a full forensic investigation of affected systems, focusing on recently executed binaries or scripts that may have facilitated network discovery and reviewing any user account compromise indications. |
