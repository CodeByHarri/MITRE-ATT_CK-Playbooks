# Traffic_Signaling:_Port_Knocking - T1205001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control, Defense Evasion, Persistence |
| MITRE TTP | T1205.001 |
| MITRE Sub-TTP | T1205.001 |
| Name | Traffic Signaling: Port Knocking |
| Log Sources to Investigate | 1. Firewall logs - Analyze denied and allowed traffic to identify unusual sequences of connection attempts to closed ports.<br>Example: Splunk, ELK Stack. <br>2. Network intrusion detection system (NIDS) - Look for anomalies in traffic patterns that could indicate port knocking.<br>Example: Snort, Suricata. <br>3. Endpoint detection and response (EDR) - Monitor endpoints for processes or network connections associated with port knocking strategies.<br>Example: CrowdStrike, Carbon Black. <br>4. Packet capture and analysis tools - Use network packet capture data to look for specific packet sequences that correspond to port knocking.<br>Example: Wireshark, tcpdump. |
| Key Indicators | 1. Sequence of connection attempts to closed ports within short time intervals.<br>2. Usage of libpcap or raw sockets by unusual or unauthorized processes.<br>3. Unexplained changes in firewall rules allowing traffic through previously closed ports.<br>4. Presence of unusual listening ports that match the timing of known port knocking sequences. |
| Questions for Analysis | 1. Are there sequences of connection attempts to closed ports that don't resemble legitimate network scanning or troubleshooting activities?<br>2. Is there evidence of libpcap or raw socket usage in logs from user accounts or applications that typically do not require such functionality?<br>3. Are there changes in firewall rules that coincide with patterns resembling port knocking?<br>4. Have any endpoint or network defenses flagged suspiciously opened ports or unusual communications immediately following observed sequences? |
| Decision for Escalation | Escalate to Tier 2 if:<br>1. There are confirmed patterns of port knocking without a valid or documented business case.<br>2. Unauthorized usage of libpcap or raw sockets, particularly from unexpected applications.<br>3. Significant deviation in firewall rules or port access consistent with potential compromise.<br>4. Multiple endpoints showing the same suspicious behavior indicative of a coordinated attempt. |
| Additional Analysis Steps for L1 | 1. Correlate firewall logs and NIDS alerts to identify patterns indicative of port knocking.<br>2. Review endpoint behavior through EDR data for process anomalies using libpcap or raw sockets.<br>3. Validate changes in firewall rules or access control lists with network administrators for authenticity.<br>4. Investigate packet sequences in captured network data to find indicators of suspicious activity. |
| T2 Analyst Actions | 1. Perform deep packet inspection on captured data to validate port knocking indicators.<br>2. Conduct forensic analysis on suspicious endpoints utilizing raw sockets or libpcap for potential malware.<br>3. Collaborate with IT teams to verify, log, and potentially reverse unauthorized firewall changes.<br>4. Run network behavior analysis to determine if other systems have been affected similarly. |
| Containment and Further Analysis | 1. Isolate affected systems displaying indications of port knocking to prevent further compromise.<br>2. Work with network and security teams to implement stricter firewall settings to block unauthorized port knocking attempts.<br>3. Remove or quarantine any malware identified through endpoint analysis.<br>4. Review and strengthen network segmentation to minimize the impact of port knocking tactics.<br>5. Conduct a thorough review of security policies and user training to address the risk of similar threats. |