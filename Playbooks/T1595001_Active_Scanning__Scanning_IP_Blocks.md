# Active_Scanning:_Scanning_IP_Blocks - T1595001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1595.001 |
| MITRE Sub-TTP | T1595.001 |
| Name | Active Scanning: Scanning IP Blocks |
| Log Sources to Investigate | Network traffic logs, firewall logs, and intrusion detection/prevention system (IDS/IPS) logs. Ensure these logs are capturing inbound and outbound connections. Examples include logs from tools like Cisco ASA, Palo Alto firewalls, or Snort. Additionally, analyze DNS query logs for patterns and logs from vulnerability scanning tools if applicable. |
| Key Indicators | Unusual or unexpected network scan patterns such as a high number of ICMP requests from a single IP address, connections attempting to access a large range of IP addresses sequentially, unusually high port scanning on external IP addresses, or multiple incomplete connections (SYN requests without ACKs). Source IPs showing repeated failed connection attempts may also be indicative. |
| Questions for Analysis | 1. Is the observed scanning activity within expected business operations?<br>2. Is the source of the scan an internal system, known external partner, or an unknown/public IP?<br>3. Does the source IP have a history of malicious activity? 4. Are there any signs of data exfiltration or lateral movement following the scans? 5. Has the same or similar scanning activity occurred previously? |
| Decision for Escalation | Escalate to Tier 2 if scans are from unknown or suspicious external IPs, the source IP is associated with known threat actors, there's evidence of attempted exploitation following the scans, or if there are indications of compromise on systems that were scanned. |
| Additional Analysis Steps for L1 | Verify if the source IPs are whitelisted and associated with authorized scanning, identify any scan patterns might correlate with malicious activity, and review related logs for any anomaly or signs of follow-up attack activity. Confirm timestamps and check for overlapping occurrences with other notable events. |
| T2 Analyst Actions | Conduct deeper network traffic analysis to confirm anomalies observed by L1, investigate the context of the scanning IPs by checking threat intelligence sources, execute packet captures for deeper inspection if necessary, and assess potential vulnerabilities revealed by the scan for prioritizing patching. |
| Containment and Further Analysis | Immediately block or throttle suspicious IPs at the perimeter if deemed malicious. Conduct a full network sweep to ensure there is no internal compromise. Review and strengthen firewall rules and access controls based on lessons learned. Consider employing honeypots to further evaluate attacker techniques and gather intelligence. Monitor for repeated attempts or other anomalies in the aftermath. |
