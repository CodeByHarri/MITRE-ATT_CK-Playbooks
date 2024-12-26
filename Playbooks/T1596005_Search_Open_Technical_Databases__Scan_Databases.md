# Search_Open_Technical_Databases:_Scan_Databases - T1596005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1596.005 |
| MITRE Sub-TTP | T1596.005 |
| Name | Search Open Technical Databases: Scan Databases |
| Log Sources to Investigate | Monitor web traffic logs for unusual outbound requests to known scan database services such as Shodan, Censys, or ZoomEye. Investigate network flow logs for any large outgoing data transfers to these services. Additionally, evaluate DNS logs for queries resolving to IP addresses associated with scan databases. |
| Key Indicators | Frequent or large DNS queries to domains associated with scanning services, spikes in outbound network traffic to these services, or unusual user-agent strings typical of automated scraping or scanning activities. |
| Questions for Analysis | Are there any unexpected or unauthorized systems contacting known scan databases? Has there been a sudden increase in traffic volume from internal systems to these databases? Are there any user credentials involved in these requests suggesting potential insider threat activity? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of compromised accounts making these requests or if any system with elevated privileges is involved. Also, escalate if there is a pattern of activity that could indicate an impending targeted attack. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the originating systems and users by checking asset management and user activity logs. Confirm if there are legitimate business reasons for accessing the identified external services. Review recent patches and vulnerability management context related to any systems involved. |
| T2 Analyst Actions | Perform deep packet inspection of the network traffic to understand the data being sent to the scan databases. Check for historical data to identify any recurring patterns or past occurrences of similar activities. Liaise with internal asset owners to verify if such activities align with business purposes. |
| Containment and Further Analysis | Isolate systems suspected of illegitimate data transmission to limit potential data exfiltration. Conduct a comprehensive vulnerability assessment of affected systems. Use threat intelligence sources to corroborate whether similar techniques have been attributed to known adversaries or campaigns. |
