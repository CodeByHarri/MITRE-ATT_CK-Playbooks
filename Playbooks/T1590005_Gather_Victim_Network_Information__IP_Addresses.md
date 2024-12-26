# Gather_Victim_Network_Information:_IP_Addresses - T1590005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1590.005 |
| MITRE Sub-TTP | T1590.005 |
| Name | Gather Victim Network Information: IP Addresses |
| Log Sources to Investigate | Investigate logs from network traffic monitoring solutions such as firewall logs, intrusion detection/prevention system (IDS/IPS) logs, and web server logs to identify any unusual inbound or outbound requests related to IP enumeration. Also, review DNS query logs to detect any unusual activity, as well as web access logs for signs of information gathering. |
| Key Indicators | Key indicators include repeated access attempts from an external source scanning for IP addresses, unusual patterns of DNS queries that attempt to resolve multiple subdomains or IP addresses in a rapid sequence, and spikes in network traffic volumes directed towards external IP address ranges. |
| Questions for Analysis | Are there unusual patterns of access to public-facing resources? Are there any known malicious IPs involved in accessing our endpoints? Do accessed or queried IP ranges align with any recognized reconnaissance patterns? What is the frequency and volume of DNS queries, and do they correspond with potential IP address gathering? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of repeated scanning activity from the same source IP, attempts to enumerate internal IP addresses not typically visible externally, or if queries are linked to IP addresses previously associated with known threat actor activity. Additionally, escalate if there are signs of compromise or unauthorized access. |
| Additional Analysis Steps for L1 | Cross-reference accessed IP addresses or querying domains against threat intelligence databases for any previous suspicious activity. Verify whether IP addresses in question are part of any ongoing approved security exercises or red team activities. Correlate network logs with user activity logs to check for legitimate access. |
| T2 Analyst Actions | Perform a deeper analysis using advanced network monitoring tools to trace the source and intent of reconnaissance activities. Engage with network security teams to validate the suspected scanning activity. Use threat intelligence platforms to further investigate involved IP addresses for historical threat data. |
| Containment and Further Analysis | Implement blocking rules at the firewall for any IPs identified as malicious. Conduct a thorough network audit to identify any vulnerabilities exposed by the reconnaissance attempt. Consider employing honeypots to gather more intelligence on the adversary's methods and intent. Continue to monitor network traffic closely for any signs of escalated activities after initial attempts at gathering IP information. |
