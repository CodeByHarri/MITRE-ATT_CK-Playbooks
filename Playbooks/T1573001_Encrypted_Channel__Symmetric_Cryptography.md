# Encrypted_Channel:_Symmetric_Cryptography - T1573001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1573.001 |
| MITRE Sub-TTP | T1573.001 |
| Name | Encrypted Channel: Symmetric Cryptography |
| Log Sources to Investigate | Network traffic logs, firewall logs, proxy logs, and intrusion detection/prevention system (IDS/IPS) alerts. Examples include logs from network appliances such as Palo Alto Networks, Cisco Firepower, Fortinet Fortigate, and proxy logs from devices like Blue Coat ProxySG or Zscaler. These sources are crucial for identifying encrypted command and control traffic. |
| Key Indicators | Uncommon ports being used for communication, unusual data transfer rates by a host, known symmetric encryption signatures like AES, DES in network traffic patterns, sudden increase in outbound encrypted traffic from endpoints that do not typically generate such traffic, and presence of compromised protocols like RC4 or DES if observed in modern environments. |
| Questions for Analysis | Is the source IP associated with known malicious entities or threat lists? Are the symmetric encryption algorithms used typical for the organization's current communication protocols? Is there any deviation from normal traffic patterns for this endpoint or user? Have other security alerts or events been triggered around the same time as this encryption behavior? |
| Decision for Escalation | Escalate to Tier 2 if traffic is using known risky symmetric encryption algorithms (e.g., DES, 3DES), if multiple indicators (like uncommon ports and encryption signatures) coincide, if the communication is with known malicious IPs or domains, or if the endpoint in question has demonstrated prior suspicious behavior. |
| Additional Analysis Steps for L1 | Cross-reference involved IPs and domains with threat intelligence feeds and reputation services. Check for related alerts from endpoint security tools. Correlate current network activity with historical logs to identify patterns or deviations. Conduct basic OSINT to identify any new threats related to the observed behavior. |
| T2 Analyst Actions | Perform deep packet inspection to further analyze encrypted traffic content. Consult with threat intelligence to verify if the encryption is characteristic of advanced persistent threats (APTs). Initiate host-based analysis on endpoints generating suspicious traffic for signs of malware or system compromise. Use sandboxing techniques to test involved domains and IPs. |
| Containment and Further Analysis | Block communication to known malicious IP addresses or domains at the network firewall level. Isolate affected endpoints to prevent further potential compromise. Conduct a full forensic analysis on isolated systems to identify entry vectors and affected data. Review and update firewall and IDS/IPS rules to detect and alert on similar suspicious traffic patterns moving forward. |
