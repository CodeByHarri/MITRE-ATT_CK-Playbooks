# Resource_Hijacking:_Bandwidth_Hijacking - T1496002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1496.002 |
| MITRE Sub-TTP | T1496.002 |
| Name | Resource Hijacking: Bandwidth Hijacking |
| Log Sources to Investigate | Network traffic logs, firewall logs, proxy server logs, and endpoint security logs are crucial for this TTP. Examples include inspecting unusual spikes in outbound traffic from individual hosts, analyzing logs related to peer-to-peer traffic, and reviewing alerts from endpoint detectors for unauthorized or suspicious processes consuming high network bandwidth. |
| Key Indicators | Indicators include unusual outbound internet connections at non-standard ports or protocols, sudden spikes in data transfer rates, significant variance from typical usage patterns, and alerts from network monitoring systems regarding known botnet command and control activity or proxyware usage. |
| Questions for Analysis | 1. Has the affected system shown a sudden increase in outbound traffic?<br>2. Are there any connections observed to known malicious IP addresses or domains?<br>3. Does the traffic pattern correspond with known botnet or proxyjacking characteristics? 4. Are there any unauthorized or suspicious processes observed on the host endpoint? |
| Decision for Escalation | Escalate to Tier 2 if there is corroborative evidence of bandwidth misuse for botnet activity, proxyjacking, or if connections to known malicious infrastructure are confirmed. Also, escalate if detected anomalies are outside L1's ability to resolve effectively and disruptively. |
| Additional Analysis Steps for L1 | Verify if the traffic spike coincides with known legitimate activities. Check if the IPs or domains involved are flagged in threat intelligence feeds. Ensure suspicious activities align with user or system activity patterns, and gather additional system logs from affected endpoints to correlate behavior. |
| T2 Analyst Actions | Conduct a deeper forensic analysis on affected systems, including memory and disk analysis, to identify any malicious binaries or scripts. Review configurations and logs for evidence of unauthorized proxy setup or scanning activities. Cross-reference observed indicators with threat intelligence to confirm maliciousness. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent further data exfiltration or malicious activities. Perform full malware removal procedures and re-image affected systems if necessary. Improve network monitoring rules and update firewall rules to block malicious IPs or domains. Conduct a wider scope analysis to determine possible lateral movement or additional compromised hosts. |
