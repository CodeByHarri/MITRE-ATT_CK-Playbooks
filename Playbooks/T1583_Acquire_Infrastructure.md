# Acquire_Infrastructure - T1583

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1583 |
| MITRE Sub-TTP | T1583 |
| Name | Acquire Infrastructure |
| Log Sources to Investigate | Network traffic logs, DNS query logs, cloud provider activity logs, server access logs, web service utilization logs. Examples include AWS CloudTrail logs for cloud infrastructure acquisition, domain registration and WHOIS records for new domain acquisitions, and VPN/proxy service logs to detect potential use of proxies or suspicious new IP addresses. |
| Key Indicators | Sudden increase in cloud service provisioning, unusual domain registrations from corporate accounts, new IP addresses with no prior history on corporate network, spikes in traffic to external cloud providers, configurations pointing to known abuse proxies or obscure hosting services. |
| Questions for Analysis | Were the new domains or IP addresses registered by authorized personnel? Are there sudden or unexplained new instances or servers appearing in cloud service dashboards? Does the network traffic show patterns consistent with infrastructure procurement operations? Are there any attempts to disguise or hide these activities using anonymity tools? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of unauthorized infrastructure acquisition, if there are associated indicators of compromise (IOCs) with known threat actors, or if the activities appear to be related to other ongoing suspicious or malicious behaviors. |
| Additional Analysis Steps for L1 | Verify recent domain registrations against known and authorized registrations. Cross-check cloud activity against expected usage patterns. Ensure user accounts associated with suspicious actions were not compromised. |
| T2 Analyst Actions | Conduct a deeper inspection of network logs to trace back the origin of suspicious activities. Validate infrastructure setup timelines with expected plans from IT/development teams. Analyze historical data for patterns of similar activities correlating with potential threats. |
| Containment and Further Analysis | If unauthorized infrastructure activity is confirmed, initiate revocation of access to any acquired resources. Notify relevant teams to validate and if necessary, shut down suspicious infrastructure. Strengthen monitoring around unusual domain registration and validate current cloud resource access permissions. |
