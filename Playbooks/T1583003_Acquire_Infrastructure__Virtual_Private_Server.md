# Acquire_Infrastructure:_Virtual_Private_Server - T1583003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1583.003 |
| MITRE Sub-TTP | T1583.003 |
| Name | Acquire Infrastructure: Virtual Private Server |
| Log Sources to Investigate | Network traffic logs showing outgoing connections to IP ranges associated with popular cloud service providers (e.g., AWS, Azure, Google Cloud). Payment and registration logs to identify transactions related to VPS services. Firewall logs and DNS query logs for unusual patterns or connections. Cloud management console access logs to track provisioning activities. |
| Key Indicators | Unexplained or persistent outbound connections to known VPS provider IP ranges. Payment transactions to VPS providers from unexpected accounts or repeated small transactions. Sudden increase in cloud resource deployment or DNS queries resolving to cloud-hosted IPs, especially those not previously common in network traffic. |
| Questions for Analysis | Are there unexpected or persistent outbound traffic patterns to known VPS provider IPs? Have there been any unusual payment transactions or account activities linked to VPS acquisitions? Was there a sudden spike in cloud resource provisions that were not aligned with business operations? |
| Decision for Escalation | Escalate to Tier 2 if there are confirmed outbound connections to VPS providers combined with unusual or unauthorized payment transactions. Also, escalate if there's unexplained high-volume provisioning of cloud resources or connections to IPs previously unassociated with organization activities. |
| Additional Analysis Steps for L1 | Verify the legitimacy of payment transactions linked to VPS providers. Cross-check IP addresses with the known list of cloud service provider ranges. Check user accounts for any recent creation or modification of cloud resources that are not documented or justified. |
| T2 Analyst Actions | Perform deep packet inspection of the traffic to and from identified VPS IPs. Correlate the identified VPS activities with potential indicators of compromise across the network. Review user account access logs for anomalies in cloud management interfaces. Seek further intelligence on the identified IPs to assess reputational risk. |
| Containment and Further Analysis | If malicious activity is confirmed, block IPs associated with unapproved VPS on firewalls. Quarantine systems exhibiting suspicious traffic patterns. Conduct a thorough investigation into the extent of VPS use, including potential backdoors or compromised credentials. Collaborate with legal or law enforcement if necessary to understand the full scope of the breach and any data exfiltration activities. |
