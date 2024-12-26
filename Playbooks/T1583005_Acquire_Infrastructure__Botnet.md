# Acquire_Infrastructure:_Botnet - T1583005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1583.005 |
| MITRE Sub-TTP | T1583.005 |
| Name | Acquire Infrastructure: Botnet |
| Log Sources to Investigate | Network traffic logs, intrusion detection system (IDS) alerts, firewall logs, and endpoint detection and response (EDR) logs are critical for investigating potential botnet activity. Examples include analysis of outbound traffic for abnormal volumes, unusual destination IP addresses, or packet sizes. Monitoring DNS traffic for excessive or anomalous queries might indicate botnet command and control (C&C) channels. |
| Key Indicators | Increased network traffic or spikes in outbound connections, particularly to known botnet C&C IP addresses. Unusual traffic patterns that deviate from normal baselines. Patterns of communication consistent with botnet behavior, such as periodic check-ins or beaconing. Sudden use of previously dormant processes or services on endpoints. |
| Questions for Analysis | Is there an unexplained increase in outbound network connections? Are there connections to known malicious IP addresses linked to botnet activity? Do the DNS logs show any unusual, repetitive queries to specific domains? Are any endpoint systems showing signs of unexpected or unusual behavior? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmation of connections to known botnet C&C nodes, significant deviations from baseline network activity, or if endpoint activity aligns with botnet infection patterns. Also, escalate if initial assessment cannot eliminate a false positive and potential risk to operations is high. |
| Additional Analysis Steps for L1 | Review detailed network flow logs and look for patterns in source and destination IP address relationships. Correlate suspicious network events with endpoint activity logs. Assess the origin and nature of the aforementioned traffic anomalies and attempt to attribute to any known benign operations or services within the organization. |
| T2 Analyst Actions | Conduct deeper inspection of affected systems to determine the presence of malware artifacts or indicators of compromise (IoCs) that verify botnet activity. Leverage advanced threat intelligence feeds to correlate identified IP addresses, domains, and other indicators with known threat actor activity. If botnet involvement is confirmed, coordinate with IT to initiate containment procedures. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent further spread and command execution. Perform in-depth forensic analysis on compromised devices to identify the botnet strain and any secondary payloads. Update firewall rules and intrusion prevention systems (IPS) to block known malicious IPs and domains. Conduct a full environment sweep using updated signatures to ensure no other assets are impacted. |
