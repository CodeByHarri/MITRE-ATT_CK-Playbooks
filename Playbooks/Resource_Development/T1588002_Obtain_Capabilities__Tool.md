# Obtain_Capabilities:_Tool - T1588002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1588.002 |
| MITRE Sub-TTP | T1588.002 |
| Name | Obtain Capabilities: Tool |
| Log Sources to Investigate | Monitor procurement logs, web traffic, and executable downloads. Check enterprise software license management systems for unusual activity. Analyze endpoint and network traffic logs for anomalous downloads or acquisitions. Example log sources include network intrusion detection systems (NIDS), web proxy logs, and software asset management systems. |
| Key Indicators | Sudden increase in software downloads, particularly security tools or utilities. Unusual access patterns to software license servers. Unexpected outbound web traffic to known tool download or piracy sites. Large data transfers possibly indicating software acquisition or licensing data exfiltration. |
| Questions for Analysis | Did the user or system typically download similar tools in the past? Are the tools being downloaded commonly used within our environment? Do network patterns indicate contact with known threat actor tool repositories? Is there any evidence suggesting license or software manipulation? |
| Decision for Escalation | Escalate if the tool or software acquisition involves known red-team tools like Cobalt Strike or if there are indicators of license cracking activities. If the download source is associated with recognized malicious domains or threat actor patterns, escalate to Tier 2. |
| Additional Analysis Steps for L1 | Verify the legitimacy of any procurement requests for relevant tools. Analyze the source and destination of network traffic related to software acquisition. Look for any associated anomalous login or access attempts credibly linked to the download activities. |
| T2 Analyst Actions | Conduct a deeper dive into the forensic data to assess the potential impact of the acquired tools. Correlate with threat intelligence feeds for updated indicators of compromise (IOCs) involving these tools. Confirm whether acquisitions were unauthorized or suspicious. |
| Containment and Further Analysis | Isolate systems involved in suspicious software acquisitions. Audit and review any newly installed or downloaded tools for malicious code or indicators of unauthorized modifications. Monitor network activity closely to detect any post-acquisition actions, like internal lateral movement attempts. |
