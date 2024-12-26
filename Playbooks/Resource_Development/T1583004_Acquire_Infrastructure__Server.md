# Acquire_Infrastructure:_Server - T1583004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1583.004 |
| MITRE Sub-TTP | T1583.004 |
| Name | Acquire Infrastructure: Server |
| Log Sources to Investigate | Cloud service provider logs, especially logs that record server provisioning and teardown events. Payment records and billing anomalies related to purchasing or using server infrastructure. Network traffic logs focusing on unusual outbound traffic patterns to newly provisioned IP addresses. Domain registration logs if new domains are owned or resolved. Examples: AWS CloudTrail, Google Cloud Logging, Azure Activity Logs. |
| Key Indicators | Recent provisioning of new servers or IP allocations. Unusual or anomalous billing charges indicating server rentals or extensive usage of trial cloud services. Rapid provisioning and deprovisioning of servers. Network traffic to external IPs that were recently provisioned by the organization. |
| Questions for Analysis | Has there been any recent server acquisition or infrastructure provisioning activity? Are the servers in question associated with legitimate business use? Is there heightened or unexpected billing activity related to compute services? Do the IP addresses or domains associated with the servers have prior associations with known malicious activities? |
| Decision for Escalation | Escalate to Tier 2 if there are unexplained server acquisitions, if the server is associated with high volumes of network traffic exhibiting atypical patterns, or if related domains/IP addresses are flagged by security threat intelligence feeds. |
| Additional Analysis Steps for L1 | Review recent server provisioning logs for anomalies. Check network logs for traffic patterns associated with newly provisioned servers. Validate whether server usage aligns with documented business needs. Cross-reference IP addresses and domains against threat intelligence databases. |
| T2 Analyst Actions | Investigate the purpose and origin of server acquisitions. Determine if these servers are used for illicit activities such as phishing or command and control. Utilize threat intelligence to assess the risk associated with IPs/domains. Correlate findings with broader network activity and signs of compromise. |
| Containment and Further Analysis | Initiate containment measures if servers are confirmed as part of malicious infrastructure. This includes blocking associated IPs/domains and collaborating with cloud service providers to suspend fraudulent accounts. Perform forensic analysis to trace the workflow and identify potential data exfiltration or unauthorized access to resources. Reassess billing records and usage patterns for future detection optimizations. |
