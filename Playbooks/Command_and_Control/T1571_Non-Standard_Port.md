# Non-Standard_Port - T1571

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1571 |
| MITRE Sub-TTP | T1571 |
| Name | Non-Standard Port |
| Log Sources to Investigate | Network traffic logs, such as those from firewalls, intrusion detection/prevention systems (IDS/IPS), and network flow data, are critical for identifying non-standard port usage. For example, firewalls might show traffic originating from ports other than the expected standard ports (e.g., HTTP on 8088 instead of 80, or HTTPS on 587 instead of 443). Log aggregation systems like SIEMs can correlate events indicating unusual protocol-port pairings. Additionally, system logs from endpoint protection platforms may reveal changes to configuration settings or registry values. |
| Key Indicators | 1. Unusual protocol-port pairings detected in network logs (e.g., HTTPS traffic over non-standard ports).<br>2. Unexpected changes in system configurations, such as altered registry keys for service ports.<br>3. Anomalous patterns of traffic volume on ports commonly associated with different services. 4. Connection attempts from new, foreign IP addresses to non-standard ports. |
| Questions for Analysis | 1. Is there legitimate business justification for the use of this non-standard port-protocol pairing?<br>2. Has there been any recent authorized configuration change that altered ports on monitored systems?<br>3. Are the source and destination IPs associated with known or legitimate business relations? 4. Does the traffic pattern match any known malicious behavior, such as known C2 protocols? |
| Decision for Escalation | Escalate to Tier 2 if: 1. The traffic is from an unknown or suspicious IP address.<br>2. Non-standard ports are used without any known business justification.<br>3. There is evidence of configuration changes to enable such non-standard port usage without approval. 4. There are patterns suggesting data exfiltration, lateral movement, or known attack frameworks. |
| Additional Analysis Steps for L1 | 1. Verify the protocol and port pairing from network logs.<br>2. Check recent configuration changes on the affected systems for deliberate port changes.<br>3. Consult with system owners to confirm any authorized changes to protocol-port configurations. 4. Isolate incidents and collect relevant context from threat intelligence sources. |
| T2 Analyst Actions | 1. Perform in-depth analysis of traffic patterns and behaviors associated with the non-standard ports.<br>2. Correlate with known threat intelligence sources to look for signature or behavioral matches.<br>3. Investigate system configurations and changes to understand if modifications were legitimate or malicious. 4. Conduct packet analysis to uncover potential command and control traffic or data exfiltration. |
| Containment and Further Analysis | 1. Block suspicious IP addresses and alert relevant teams.<br>2. Restrict or revert configuration changes altering port usage.<br>3. Apply network segmentation to limit access from affected systems. 4. Monitor for recurring or new attempts to use non-standard ports and analyze the potential scope of compromise. 5. Conduct a post-incident review to understand root causes and improve detection strategies. |