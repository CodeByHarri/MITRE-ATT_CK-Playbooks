# Search_Open_Technical_Databases - T1596

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1596 |
| MITRE Sub-TTP | T1596 |
| Name | Search Open Technical Databases |
| Log Sources to Investigate | Network intrusion detection systems (NIDS) logs, web proxy logs, DNS query logs, certificate transparency logs, and external threat intelligence feeds. Examples include monitoring for unusual queries to public technical databases such as WHOIS, Shodan, or SSLShopper. |
| Key Indicators | Repeated queries or searches for organization domains or IP ranges in known technical databases, unusual patterns of certificate transparency log access, or DNS queries that match external threat indicators pointing to reconnaissance activities. |
| Questions for Analysis | Are the detected searches targeting our specific domains or IP addresses? Are the queries originating from known or trusted sources? Is there an unusual volume of queries over a short time frame suggesting automated scraping? Do the searches correlate with known threat actor TTPs? |
| Decision for Escalation | Escalate if there is a significant volume of targeted queries or if the searches are from suspected malicious IPs or locations. Escalate if patterns match known reconnaissance methods linked with adversarial behavior. Consider escalation if there's corroborating intelligence suggesting a targeted campaign. |
| Additional Analysis Steps for L1 | Verify the volume and frequency of suspicious queries. Check if the activity coincides with any internal IT changes or legitimate testing. Correlate data with threat intelligence to verify if the sources are linked to known adversaries. |
| T2 Analyst Actions | Conduct a deeper analysis of the source, intent, and toolset used for reconnaissance. Utilize advanced threat intelligence platforms to cross-reference suspicious activity. Assess if there is a connection to ongoing campaigns affecting similar organizations or industry verticals. |
| Containment and Further Analysis | Block or filter traffic from identified malicious IP addresses at the firewall or proxy level. Further monitor and analyze network traffic for additional signs of targeted reconnaissance. Engage with third-party threat intelligence providers for enhanced monitoring. Conduct a thorough review of network security posture and ensure monitoring systems are optimized to detect similar activities in the future. |
