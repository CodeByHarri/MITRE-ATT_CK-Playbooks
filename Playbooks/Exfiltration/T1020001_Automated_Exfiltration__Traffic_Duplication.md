# Automated_Exfiltration:_Traffic_Duplication - T1020001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Exfiltration |
| MITRE TTP | T1020.001 |
| MITRE Sub-TTP | T1020.001 |
| Name | Automated Exfiltration: Traffic Duplication |
| Log Sources to Investigate | Network flow logs (e.g., NetFlow, VPC Flow Logs for AWS), device configuration logs (e.g., network device syslogs), cloud-based traffic mirroring logs (e.g., AWS Traffic Mirroring logs, GCP Packet Mirroring logs), IDS/IPS logs, firewall logs. |
| Key Indicators | Unusual or unauthorized traffic mirroring configurations, sudden changes in network traffic patterns, traffic logs showing mirrored traffic to external destinations, changes in cloud configurations related to packet mirroring without corresponding change management logs. |
| Questions for Analysis | Are there any unauthorized configurations made to traffic mirroring on network or cloud devices? Is there a pattern of unexpected traffic duplication, especially towards external or unknown IPs? Are there any recent changes in network device configurations traceable to unexpected sources or users? |
| Decision for Escalation | Escalate if unauthorized or suspicious traffic duplication is detected, especially if it involves external addresses. Escalate if there are changes in network or cloud configurations that cannot be correlated with authorized changes or if the changes align with known malicious TTPs. |
| Additional Analysis Steps for L1 | Review recent network device and cloud configuration changes for abnormalities. Check for any recent alerts or logs related to unauthorized access or configuration changes on network and cloud resources. Verify if legitimate business processes or maintenance activities could justify the traffic mirroring. |
| T2 Analyst Actions | Perform a deep dive into network traffic analysis to identify the final destination(s) of the duplicated traffic. Validate changes with responsible teams or change management records. Review historical access logs for suspicious or outlier activities leading up to the mirroring configuration. |
| Containment and Further Analysis | Disable any unauthorized traffic mirroring configurations and block associated IP addresses if external. Conduct a forensic analysis of compromised devices to assess further compromise. Review and enhance monitoring and security configurations of network and cloud infrastructure. Prepare detailed reports on findings and remediation actions for security leadership. |
