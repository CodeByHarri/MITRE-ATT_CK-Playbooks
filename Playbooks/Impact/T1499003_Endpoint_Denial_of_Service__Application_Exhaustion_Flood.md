# Endpoint_Denial_of_Service:_Application_Exhaustion_Flood - T1499003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1499.003 |
| MITRE Sub-TTP | T1499.003 |
| Name | Endpoint Denial of Service: Application Exhaustion Flood |
| Log Sources to Investigate | Network traffic logs, web server logs, application server logs, firewall logs, and intrusion detection system (IDS) logs. Look for logs from tools like Apache, Nginx access logs, or WAF logs. Capture resource utilization metrics from system performance monitoring tools to observe spikes in CPU or memory usage. |
| Key Indicators | High volume of requests to specific, resource-intensive endpoints, unusual patterns of repeated API calls or web requests, spikes in network traffic correlated with decreased system performance, and alerts from WAF or IDS on unusual request patterns. |
| Questions for Analysis | Are there identifiable patterns, such as specific IP addresses or user agents that are repeatedly accessing the targeted application endpoint? Is the request rate beyond normal or expected traffic patterns for the application? Are there any known legitimate reasons for such a high volume of traffic? Has there been any significant impact on the application or system performance noted? Do these requests align with known techniques or IP addresses related to previous attacks or malicious activity? |
| Decision for Escalation | Escalate to Tier 2 if there is a high volume of repeated requests from distinct or unusual IPs targeting resource-intensive features of the application, resulting in service degradation or denial. Also, escalate if there is a correlation between these requests and suspicious activities noted in other logs. |
| Additional Analysis Steps for L1 | Examine the time frame of the increased traffic and correlate with any scheduled legitimate activities. Verify with application teams if there have been any ongoing tests or deployments. Check for any alerts from security systems regarding those IPs or requests. Gather information on the resource utilization trend in the impacted period. |
| T2 Analyst Actions | Deploy threat intelligence feeds to identify if IPs involved have been flagged in previous attacks. Conduct deeper inspection of traffic patterns using packet analysis tools. Confirm if the traffic is coming from a botnet or an isolated actor. Collaborate with network and application teams to review current defenses and potential vulnerabilities in application endpoints. |
| Containment and Further Analysis | Implement rate limiting or temporary IP blacklisting in WAF to mitigate ongoing attack traffic. Coordinate with the application team to re-route or load balance traffic if possible. Monitor closely for any lateral movement or further exploitation attempts. Post-incident, consider implementing a more robust DDoS mitigation strategy and assess applications for potential optimizations to prevent resource-intensive feature abuse. |
