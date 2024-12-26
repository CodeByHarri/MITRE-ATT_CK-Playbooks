# Protocol_Tunneling - T1572

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1572 |
| MITRE Sub-TTP | T1572 |
| Name | Protocol Tunneling |
| Log Sources to Investigate | Network traffic logs, firewall logs, and web proxy logs should be closely monitored. Specific examples include logs from IDS/IPS systems for unusual tunneling behaviors, VPN logs for unauthorized usage patterns, SSH logs for unexpected port forwarding, and DNS logs, particularly for DNS over HTTPS activities. |
| Key Indicators | Unusual encapsulation of protocols within SSH or HTTPS, high volumes of outbound DNS queries with DoH, anomalous port usage patterns, unexpected SSH tunnels, sudden changes in network traffic patterns, and increased latency in specific connections. Look for connections to known tunneling software or services. |
| Questions for Analysis | Are the tunneling activities associated with known legitimate applications or services? Is the IP address associated with known suspicious or malicious domains? Is there any anomaly in user behavior, like accessing systems they normally wouldn't? Are there any correlating alerts or logs indicating suspicious activities from the same source? |
| Decision for Escalation | Escalate to Tier 2 if tunneling is confirmed to be unauthorized or if associated with known threat actors. Also, escalate if there's consistent unusual network activity that cannot be accounted for by the current configuration or known baseline activity. |
| Additional Analysis Steps for L1 | Verify and document the source and destination of the tunneling activity. Identify related processes on the host machine that might be initiating tunneling. Correlate with user activity logs to determine if the activity could be legitimate. Check historical data for similar patterns or connections. |
| T2 Analyst Actions | Perform deeper forensic analysis on the involved hosts to identify any malicious software contributing to the tunneling. Use threat intelligence to match IPs and domains with known malicious sources. Analyze any encrypted traffic for abnormalities, possibly decrypting if feasible. Execute risk assessments on identified suspicious connections. |
| Containment and Further Analysis | Isolate affected systems to prevent further malicious communications. Block identified malicious IPs and domains at the firewall. Reconfigure network devices to limit unnecessary or unauthorized tunneling. Implement enhanced monitoring and logging to detect reoccurrence. Conduct a full security review to identify any other impacted areas or potential vulnerabilities. |
