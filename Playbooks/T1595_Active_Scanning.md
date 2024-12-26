# Active_Scanning - T1595

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1595 |
| MITRE Sub-TTP | T1595 |
| Name | Active Scanning |
| Log Sources to Investigate | Investigate firewall logs, intrusion detection system (IDS) logs, and network flow analysis tools like NetFlow. These logs can provide insight into unusual network traffic patterns indicative of scanning activities. Look for repeated connection attempts from a single IP address, high volume of connection requests, and unexpected ICMP requests. Additionally, review web server logs for unusual access patterns and DNS logs for signs of enumeration. |
| Key Indicators | Key indicators include an unusual number of connection attempts or probes from a single IP address, presence of ICMP echo requests (ping sweeps), and access to ports typically not interacted with. Other indicators include scanning patterns such as SYN scanning (half-open requests) and full connection scans. Detection of specific scanning tools signatures, like Nmap, or long periods of continuous network traffic from a new or unexpected IP source. |
| Questions for Analysis | 1. Is the source IP address known to our systems or is it internal?<br>2. Are there any known vulnerabilities in the affected systems that could be exploited?<br>3. What ports or services were being targeted by the scan? 4. Is the volume of traffic consistent with legitimate business activity or typical user behavior? 5. Have similar activities been observed recently, potentially indicating a pattern? |
| Decision for Escalation | Escalate to Tier 2 if the source of the scanning is external and not previously seen, or if it targets critical systems. Also, escalate if the scanning is persistent over time or targets a range of services indicative of information gathering for potential exploitation. The presence of multiple scanning methods or attempts to bypass defenses such as rate limiting is another escalation criterion. |
| Additional Analysis Steps for L1 | For further investigation, conduct an initial IP reputation check to determine if the source IP is associated with malicious activity. Cross-reference the detected scans with recent vulnerability disclosures related to targeted ports or services. Review correlated alerts from IDS/IPS systems to identify possible exploit attempts succeeding scans. |
| T2 Analyst Actions | Tier 2 analysts should perform a deeper historical analysis of the source IP's activity over time. Correlate with any other suspicious activities around the same timeframe. Utilize threat intelligence services to match the scanning patterns against known threat actor TTPs. Additionally, attempt to identify if the scanning originated from a legitimate third-party, such as a security tester or partner organization, potentially negating the threat. |
| Containment and Further Analysis | If malicious activity is confirmed, block the source IP at the firewall and blacklist it on IDS/IPS systems to prevent further scanning. Conduct a full asset review of the targeted systems for signs of vulnerabilities or compromise. Forensic analysis of logs to identify potential data exfiltration or secondary actions taken post-scan. Prepare an incident report for future reference and improve network defense mechanisms, including updating firewall rules to mitigate similar attempts in the future. |