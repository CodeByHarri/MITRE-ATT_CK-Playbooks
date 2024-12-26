# Compromise_Infrastructure:_Virtual_Private_Server - T1584003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1584.003 |
| MITRE Sub-TTP | T1584.003 |
| Name | Compromise Infrastructure: Virtual Private Server |
| Log Sources to Investigate | Monitor firewall logs for unusual access patterns to and from VPS IP addresses. Check cloud service provider logs for account access anomalies and billing discrepancies, as attackers may use compromised accounts to deploy servers. Network traffic logs should be examined for data flows to and from known VPS providers, which could indicate communication with potential C2 infrastructure. Investigate application logs for behavior indicative of typical adversary activity, such as abnormal command-line operations or spawning of suspicious processes. |
| Key Indicators | Unrecognized IP addresses linked to VPS services appearing in connection logs. Abrupt increases in outbound traffic, especially to known VPS IP address ranges. Unusual user activity logs such as account creation or modifications in cloud service administration panels. Anomalous billing activity that could indicate unauthorized server deployment. Detection of uncommon ports being used or new protocols on standard ports in network logs, associated with communication patterns typical of VPS or C2 operations. |
| Questions for Analysis | Is the source and destination IP address located within a known set of VPS provider ranges? Does the account accessing the VPS have a history of abnormal activity alerts or recent password changes? Are there any associated alerts or deviations from the baseline user behavior in activities such as spike in data transfer rates? Have any recent changes been detected in account permissions or access logs that were not expected or unusual? |
| Decision for Escalation | Escalate to Tier 2 if evidence suggests that a VPS server in use is displaying anomalous network traffic patterns suggestive of C2 communication. Escalate if there are verified logs indicating the compromise of cloud service provider accounts (e.g., multiple failed login attempts followed by a successful one from an unusual location). Advancement is also warranted if an internal resource is communicating with these VPS addresses without any documented business purpose. |
| Additional Analysis Steps for L1 | Validate the IP addresses against threat intelligence sources to assess known malicious activity. Correlate user access logs with central authentication and login history to identify supply chain warnings or patterns of compromise. Generate alerts for subsequent connections to new or unscheduled VPS instances to advise future monitoring actions. |
| T2 Analyst Actions | Conduct a deeper investigation into account activity within cloud service providers. Examine network traffic for advanced indicators of C2 behavior, such as long-duration connections, encrypted tunnels, or unusual data packet sizes. Coordinate with IT to restrict or monitor outbound connections to the known VPS ranges or IPs. Engage threat intelligence to determine if the VPS is part of wider-known malicious infrastructure, perhaps related to current threat campaigns. |
| Containment and Further Analysis | Implement network isolation for any systems communicating with the suspicious VPS to prevent further data exfiltration. Notify cloud service providers to suspend or review suspected compromised accounts and newly deployed servers. Carry out in-depth forensic analysis on systems suspected to interact with the compromised VPS, looking particularly for malware signatures or indicators of distributed operations. Finally, conduct post-incident reviews to strengthen policies and detection capabilities related to unauthorized cloud resource usage. |