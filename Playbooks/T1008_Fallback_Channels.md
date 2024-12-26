# Fallback_Channels - T1008

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1008 |
| MITRE Sub-TTP | T1008 |
| Name | Fallback Channels |
| Log Sources to Investigate | Network traffic logs, especially network flow data, DNS logs, and firewall logs, are crucial to monitor for fallback channels. Specific examples include inspecting logs from IDS/IPS systems for anomalies or patterns that show usage of uncommon ports or protocols, and NetFlow data for unexpected external communication. Additionally, proxy logs and endpoint detection and response (EDR) logs may show attempts to establish alternate C2 channels. |
| Key Indicators | Indicators of fallback channel usage include an increase in encrypted outbound traffic on non-standard ports, a sudden switch to using different protocols for outbound communication, repeated failed attempts to access a C2 server followed by successful communication through an alternate means, and unusual DNS queries that could be associated with dynamic DNS services. |
| Questions for Analysis | Are there patterns of communication with external IP addresses over non-standard ports? Do logs show a sudden switch to alternative protocols for outbound traffic? Are there attempts to resolve unusual domain names that correlate with recent connection attempts? Have there been any repeated connection failures followed by resumed communication indicating potential fallback usage? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed evidence of communication with known malicious IPs or domains via alternate channels, if a clear pattern of fallback channel usage is detected, or if there are repeated indicators pointing to advanced evasive techniques being used to bypass normal security controls. |
| Additional Analysis Steps for L1 | Perform a preliminary review of network logs for any deviations from the baseline of normal communication patterns. Check for any alerts related to unusual DNS queries or traffic over non-standard ports. Cross-reference IPs and domains involved in suspicious communication with threat intelligence sources for potential matches with known bad actors. |
| T2 Analyst Actions | Conduct deeper packet analysis to determine the nature of the traffic involved in suspected fallback channels. Correlate events across multiple data sources to confirm the use of fallback strategies. Investigate other hosts within the network for similar patterns of behavior to identify possible lateral movement or broader compromise. |
| Containment and Further Analysis | If fallback channel activity is confirmed, isolate affected systems from the network to prevent further data exfiltration or C2 communication. Conduct a full scan of the environment for malware or persistence mechanisms linked to the detected activity. Update firewall and IDS/IPS rules to block identified malicious IPs/domains and strengthen detections for similar suspicious patterns. |
