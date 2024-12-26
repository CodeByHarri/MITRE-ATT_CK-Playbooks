# Network_Denial_of_Service:_Direct_Network_Flood - T1498001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1498.001 |
| MITRE Sub-TTP | T1498.001 |
| Name | Network Denial of Service: Direct Network Flood |
| Log Sources to Investigate | Monitor network flow data and firewall logs for anomalous traffic patterns, including significant deviations in traffic volume. Review web server logs, DNS server logs, and network intrusion detection system (NIDS) alerts for unusual activity. Examples include high-volume UDP/ICMP traffic, excessive SYN packets, and large numbers of failed connection attempts. |
| Key Indicators | Unusual spike in traffic volume against one or multiple endpoints. High rate of incoming packets per second or bandwidth usage. Anomalous traffic from multiple IP addresses, particularly if originating from diverse geolocations. Consistent patterns of failed connection attempts and timeouts, especially on services typically less trafficked. |
| Questions for Analysis | Is there a sudden and unexplained increase in network traffic volume? Are the source IPs associated with known botnets or flagged for malicious activity? Is there consistent evidence of service disruption or performance degradation correlating with the traffic patterns observed? |
| Decision for Escalation | Escalate to Tier 2 if the traffic pattern is sustained, involving multiple source IPs, and there is evidence of service disruption. Prioritize escalation if impacted services are mission-critical or if there is corroboration with threat intelligence indicating an organized attack. |
| Additional Analysis Steps for L1 | Verify the source IP addresses against threat intelligence databases to identify known malicious entities. Check for alerts on correlated events over network and endpoint logs. Ensure that anomaly baselines are updated for normal traffic behavior to help identify deviations. |
| T2 Analyst Actions | Validate the attack by correlating logs from different network boundaries and internal endpoints. Utilize threat intelligence to identify and confirm the nature of the attack, such as its method and potential attribution. Engage with IT teams to ensure traffic analysis tools such as NetFlow or sFlow are appropriately configured to gather relevant data. |
| Containment and Further Analysis | Apply temporary access control lists (ACLs) or firewall rules to filter out attack traffic, balancing between blocking threats and maintaining legitimate access. Engage DDoS protection services if available. Collaborate with ISP to mitigate attack vectors upstream. Perform root cause analysis to discern weak points and improve resilience against future attacks. |
