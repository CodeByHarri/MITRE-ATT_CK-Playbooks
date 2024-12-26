# Encrypted_Channel - T1573

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1573 |
| MITRE Sub-TTP | T1573 |
| Name | Encrypted Channel |
| Log Sources to Investigate | Network traffic logs, IDS/IPS logs, Full packet capture systems, Host-based logs from endpoint detection and response systems. For example, Zeek logs can provide insights into the network traffic patterns, and host-based logs from tools like Sysmon can show new processes or unusual communication patterns. |
| Key Indicators | Use of non-standard ports for expected protocols, suspicious outbound traffic to known bad IP addresses or domains, detection of unusual encrypted traffic patterns, endpoint processes making frequent or lengthy connections to external IPs, evidence of known malicious C2 domains or IP addresses. |
| Questions for Analysis | Is the encrypted traffic conforming to any well-known protocol normally used by the organization? Does the destination of the encrypted traffic align with known organizational infrastructure or suppliers? Are there any known indicators of compromise (IOCs) related to the destination? Does the timeframe of the network anomalies coincide with any known security events or changes? |
| Decision for Escalation | Escalate to Tier 2 if encrypted traffic is observed to external destinations that are not associated with legitimate communications. Escalate if traffic bears signatures or characteristics of known C2 frameworks or follows patterns consistent with previous incidents. If there are no clear explanations for anomalies after initial investigation, escalate. |
| Additional Analysis Steps for L1 | Verify the source and destination of suspicious traffic using internal asset and network inventories. Check for correlated alerts within a similar timeframe. Search for shared artifacts or repeated patterns in network traffic indicating C2 activity. Review historical logs for repeat occurrences of similar traffic from the same endpoints. |
| T2 Analyst Actions | Conduct deep packet analysis to better understand the nature of the encrypted traffic. Correlate network and host-based anomalies with current threat intelligence reports. Analyze user behavior for unusual logins or access patterns that may relate to encrypted traffic. Utilize sandboxing to inspect any suspects executables or libraries involved. |
| Containment and Further Analysis | If malicious encrypted traffic is confirmed, block the identified IPs/domains at network perimeter devices. Quarantine affected endpoints for further forensic analysis. Review system processes for any unauthorized changes or additions. Engage with threat intelligence teams to update detection rules and refine preventive measures. Document findings comprehensively for incident reporting and future reference. |
