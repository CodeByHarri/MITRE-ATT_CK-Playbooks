# Active_Scanning:_Vulnerability_Scanning - T1595002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1595.002 |
| MITRE Sub-TTP | T1595.002 |
| Name | Active Scanning: Vulnerability Scanning |
| Log Sources to Investigate | Network intrusion detection system (NIDS) logs to detect scanning activity, firewall logs to identify unusual port scan patterns, IDS/IPS alerts for exploitation tests, web server access logs for unexpected requests, and vulnerability scanner logs to cross-reference authorized scanning activities. Example sources include Suricata, Snort, and Palo Alto Firewall logs. |
| Key Indicators | Repeated access to a range of ports within a short timeframe from the same IP address, unusual increase in connection attempts to public-facing IPs, alerts from NIDS/IPS regarding known scanning tools or patterns, and discrepancies between expected and actual network traffic baselines. |
| Questions for Analysis | Is the source IP of the scan known and authorized for vulnerability scanning? Is there a pattern or reconnaissance behavior matching known scanning techniques? Are there any current vulnerabilities on the scanned host that could be exploited? |
| Decision for Escalation | Escalate to Tier 2 if the source IP is unknown or external, if scanning is targeted at critical infrastructure or sensitive applications, or if there is evidence of reconnaissance behavior followed by suspicious activity. |
| Additional Analysis Steps for L1 | Verify if the scanning IP is within the list of approved vulnerability scanners or internal systems. Check recent configurations for any authorized scanning activities. Look for corresponding alerts or activities in other security tools. Document the scanning pattern and any associated IPs or domains. |
| T2 Analyst Actions | Deep dive into the network traffic to analyze the patterns and potential intent of the scanning activity. Correlate events with threat intelligence to identify known malicious IP addresses or scanning tools. Conduct a vulnerability assessment of the affected hosts to determine potential risks. |
| Containment and Further Analysis | If unauthorized scanning is confirmed, block the offending IP address on the perimeter firewall. Monitor for any follow-up activity from related IP ranges. Conduct forensic analysis of affected systems to ensure no exploitation occurred. Update threat intelligence databases with new indicators gathered. |
