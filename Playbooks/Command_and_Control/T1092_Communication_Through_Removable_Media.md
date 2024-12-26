# Communication_Through_Removable_Media - T1092

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1092 |
| MITRE Sub-TTP | T1092 |
| Name | Communication Through Removable Media |
| Log Sources to Investigate | Investigate logs from endpoint protection platforms (EPP), file access logs, removable media usage logs, and anomaly detection logs specifically focusing on USB insertion/removal events. Examples include security information and event management (SIEM) system logs, Windows Event Logs (specifically Event IDs 4663 and 4660 for file access and deletion, and 560 for object access), and any logs related to access activity on known compromised systems. |
| Key Indicators | Frequent or unusual access to removable media devices, especially on isolated or air-gapped systems; Sudden increase in the use of removable media across a network; Files written to or read from USB drives that were accessed by potentially compromised systems, unusual file names or types commonly used for C2 activities; Repeated insertion/removal of removable media on multiple devices within a short timeframe. |
| Questions for Analysis | Is there an unusual pattern of removable media usage on target systems? Are files on the removable media suspicious or unknown to usual network activity? Have the involved devices experienced suspicious activity or been flagged previously? Are there any known vulnerabilities on the systems where removable media is being heavily used? |
| Decision for Escalation | Escalate to Tier 2 if there are repeated instances of suspicious removable media activity involving systems with known vulnerabilities, if any confirmed malicious files are found on removable media, or if direct communication has been observed between compromised systems using these methods without a legitimate use case. |
| Additional Analysis Steps for L1 | Verify the legitimacy of USB device usage by consulting asset management records. Cross-reference the timestamps of removable media activity with scheduled or usual business activities. Check for any recent patches or vulnerability updates on the affected devices. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the removable media and endpoints involved. Look for malware signatures or anomalous files transferred via removable media. Correlate findings with threat intelligence feeds for any indicators of compromise (IOCs) associated with known APT groups using this technique. |
| Containment and Further Analysis | Isolate any systems confirmed to be compromised to prevent further spread. If malicious activity is confirmed, disable the use of USB ports on key systems as a temporary measure. Examine logs from a wider date range to determine the extent of the compromise. Coordinate with IT to collect and preserve evidence from affected systems, ensuring legal compliance in case further legal action is required. |
