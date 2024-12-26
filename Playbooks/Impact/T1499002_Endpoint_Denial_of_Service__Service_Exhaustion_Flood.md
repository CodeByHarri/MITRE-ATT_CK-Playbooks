# Endpoint_Denial_of_Service:_Service_Exhaustion_Flood - T1499002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1499.002 |
| MITRE Sub-TTP | T1499.002 |
| Name | Endpoint Denial of Service: Service Exhaustion Flood |
| Log Sources to Investigate | Examine web server logs (e.g., Apache access logs, Nginx logs), network traffic logs particularly those from firewalls or intrusion detection/prevention systems, SSL/TLS logs for renegotiation attempts, and content delivery networks (CDNs) monitoring if used. Check for any logs indicating abnormally high requests from single or multiple IP addresses. |
| Key Indicators | Unusual spikes in HTTP request volumes to a web server, repeated SSL/TLS renegotiation from the same IP address, network bandwidth saturation, increased response times from affected services, and any corresponding error logs indicating resource exhaustion. Look for patterns in request rates that exceed normal baselines or coincide with service performance degradation. |
| Questions for Analysis | Has there been a significant increase in traffic from a specific IP or range? Are there repeated patterns of requests that could suggest automated activity? Are there any error logs corresponding with the timeline of the event? Is there any intelligence indicating similar attacks on peer organizations? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of an ongoing denial of service attack, such as persistent logs of service exhaustion patterns, negative impact on service availability continuously for more than a set threshold duration (e.g., 15 minutes), or if attack vectors suggest a more complex threat requiring advanced analysis. |
| Additional Analysis Steps for L1 | Request more detailed network logs if available, verify current mitigation measures in place (e.g., rate limiting, CDN protections), assess baselines for normal traffic volumes at the time of suspected attack, and correlate with known threat actor behaviors or recent alerts from security bulletins. |
| T2 Analyst Actions | Conduct a deep dive analysis on suspicious IPs or request patterns using threat intelligence feeds to identify known malicious entities, analyze historical data for similar patterns, confirm if the spike has subsided or if the attack vector has shifted, and engage with web hosting and external service providers for additional insights. |
| Containment and Further Analysis | Implement IP blacklisting for known malicious IPs, engage rate-limiting rules to mitigate ongoing attack vectors, coordinate with your CDN provider for additional DDoS protections, consider using web application firewalls (WAFs) to block malicious traffic, and prepare a report for potential involvement of law enforcement if the attack is significant and sustained. |
