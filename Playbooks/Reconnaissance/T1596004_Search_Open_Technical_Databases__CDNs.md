# Search_Open_Technical_Databases:_CDNs - T1596004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1596.004 |
| MITRE Sub-TTP | T1596.004 |
| Name | Search Open Technical Databases: CDNs |
| Log Sources to Investigate | Analyze logs from CDN access logs, firewall logs, and web server logs for unusual access patterns or requests. Examine logs for the use of common lookup tools or known threat actor IP addresses querying CDN resources. Investigate DNS logs for requests related to CDN content servers that deviate from expected patterns. |
| Key Indicators | Frequent CDN-related queries or scan patterns in a short time frame, especially from IP addresses known for malicious activities. Access to CDN configurations or data from geographic locations inconsistent with usual traffic. Discovery of requests attempting to access CDN misconfigurations or exposed resources. |
| Questions for Analysis | Is there an unusually high volume of requests to CDN servers from a particular IP address or geography? Are there access attempts to CDN configurations that appear unauthorized or illegitimate? Do log files show any pattern of reconnaissance behavior such as enumeration of CDN resources? |
| Decision for Escalation | Escalate if there are signs of targeted reconnaissance activities, especially if linked to known threat actor IP addresses or patterns. Additionally, escalate if there are attempts to exploit CDN misconfigurations with potential exposure of sensitive data or unauthorized access attempts. |
| Additional Analysis Steps for L1 | Verify access patterns against typical CDN traffic to identify anomalies. Check IP addresses against threat intelligence feeds for known malicious actors. Correlate high-frequency queries or unusual patterns with known threat indicators or exploits. |
| T2 Analyst Actions | Conduct deeper analysis of suspicious activities by reviewing detailed logs and appending metadata for suspect queries. Examine the network for potential breaches or data exfiltration incidents linked to CDN access. Engage with threat intelligence resources to discern if a known exploit or attacker TTP matches the observed behavior. |
| Containment and Further Analysis | If a threat is confirmed, work with CDN providers to temporarily restrict or block suspect IP addresses. Update firewall rules to mitigate future unauthorized attempts. Continue to monitor and investigate all related network assets for signs of further exploitation or secondary attacks. Conduct a thorough audit of CDN configurations for vulnerabilities or misconfigurations. |
