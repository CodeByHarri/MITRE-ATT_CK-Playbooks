# Proxy:_External_Proxy - T1090002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1090.002 |
| MITRE Sub-TTP | T1090.002 |
| Name | Proxy: External Proxy |
| Log Sources to Investigate | Network traffic logs, web proxy logs, VPN logs, firewall logs, IDS/IPS logs, and endpoint detection logs. Examples include netflow data reporting unexpected outbound connections, logs showing connections to unusual or unknown external IP addresses, proxy logs detailing requests to suspicious domains, and IDS/IPS alerts on unusual tunneling activity. |
| Key Indicators | Network connections to IP addresses or domains not typically accessed by the organization, such as those linked to cloud-based resources or virtual private servers. Unexplained outbound traffic patterns or port redirection to destinations that are not part of standard business operations. Repetitive or systematic connections to the same external IP address over non-standard ports. |
| Questions for Analysis | Has the identified IP or domain been accessed by multiple endpoints? Is the target IP/domain known or categorized as potentially malicious according to threat intelligence? Are there signs of tunneling or port redirection in the traffic? Are there multiple instances of systems attempting to communicate with the same external entity? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of consistent communication with external proxies that are not part of normal business requirements, especially if linked to known malicious activities, or if the identified communications involve multiple endpoints within the organization's network. |
| Additional Analysis Steps for L1 | Verify whether the impacted endpoints are approved to use external proxies through relevant configuration and policy checks. Cross-reference the external IP and domains with threat intelligence databases to assess reputation. Identify if any legitimate services or business justifications exist for this traffic pattern. |
| T2 Analyst Actions | Conduct deeper packet analysis to identify payloads and characteristics of the suspected traffic. Review historical traffic patterns for baseline deviations. Check compromised endpoint activity for signs of secondary C2 channels or additional malicious behavior. |
| Containment and Further Analysis | Isolate affected systems to prevent further C2 communication. Block the identified external proxies at the network level. Engage threat hunting teams to search for evidence of similar tactics across the enterprise environment. Conduct a forensic investigation on compromised systems to uncover any residual artifacts or tools. |
