# Data_Transfer_Size_Limits - T1030

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Exfiltration |
| MITRE TTP | T1030 |
| MITRE Sub-TTP | T1030 |
| Name | Data Transfer Size Limits |
| Log Sources to Investigate | Network traffic logs (e.g., packet capture logs), SIEM logs analyzing data transfer patterns, firewall logs with data exfiltration rules, IDS/IPS logs for potential data leakage patterns, and host-level data transfer logs. Example sources include Wireshark, Splunk, Cisco ASA, Palo Alto Networks, and SNORT for examining anomalous data transfer volumes and methods. |
| Key Indicators | Unusually frequent data transfers of consistent, fixed sizes across the network; data transfers to external, non-corporate IP addresses; unusually low data packets just below typical alert thresholds; repetitive patterns of data size consistency in packet captures against typical traffic norms. |
| Questions for Analysis | Are there consistent patterns of fixed-size data transfers noted in the logs? Are there transfers to IP addresses not typically associated with business partners? Does the data transfer pattern align with known malicious exfiltration techniques or threat actor methodologies? Is there evidence of user accounts transferring data unusual for their access level or typical activity? |
| Decision for Escalation | Escalate to Tier 2 if fixed-size data transfers are verified to external destinations without clear business justification, the source of data transfer is associated with a compromised or suspicious endpoint, or if the network behavior deviates significantly from established baseline operations. |
| Additional Analysis Steps for L1 | Correlate network traffic with user activity logs to determine context of the transfers. Check for known malicious IP addresses using threat intelligence feeds. Validate whether these events align with normal business operations or occur outside regular business hours. Note any recurring patterns that suggest the use of automated scripts or tools. |
| T2 Analyst Actions | Conduct detailed examination of endpoint involved in the transfers for signs of compromise. Use threat intelligence to cross-reference related IP addresses or domains with known indicators of compromise. Analyze historical data to find precedents for the identified traffic patterns, and verify if there is an ongoing data exfiltration campaign. |
| Containment and Further Analysis | Isolate affected systems and IP addresses from the network to prevent further data loss. Engage with Network Security teams to enforce block rules on identified external IPs. Gather additional forensic data from involved systems for deeper analysis. Collaborate with IT teams to patch potential vulnerabilities exploited for the data transfers and review access controls to prevent unauthorized exfiltration attempts. |
