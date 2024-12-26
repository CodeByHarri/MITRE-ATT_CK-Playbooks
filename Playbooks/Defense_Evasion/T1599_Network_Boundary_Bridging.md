# Network_Boundary_Bridging - T1599

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1599 |
| MITRE Sub-TTP | T1599 |
| Name | Network Boundary Bridging |
| Log Sources to Investigate | Investigate logs from network devices such as routers, switches, and firewalls. Ensure to check the configuration change logs, syslog data, and SNMP traps. NetFlow data should be analyzed for unusual traffic patterns across network boundaries. Log sources should include relevant IDS/IPS alerts and VPN logs if applicable. |
| Key Indicators | Unusual configuration changes on network devices, such as modifications in access control lists (ACLs) or firewall rules that were not approved. Unauthorized remote access to network devices. Uncharacteristic cross-boundary traffic patterns potentially indicating bypass attempts. Anomalies in NetFlow or traffic logs, such as unexpected IP addresses or ports being accessed or increased traffic volumes. |
| Questions for Analysis | Were there any recent configuration changes on the affected network devices? Is there unauthorized access detected within the logs? Are there consistent patterns of cross-boundary traffic that deviate from the norm? Can the source IP addresses be associated with legitimate user activity? |
| Decision for Escalation | Escalate to Tier 2 if there are confirmed unauthorized configuration changes or accesses detected in the logs. If suspicious traffic patterns across network boundaries are observed without legitimate explanation, escalate. Detection of known IOCs related to this TTP from threat intelligence sources should trigger escalation. |
| Additional Analysis Steps for L1 | Verify the timestamps of the detected activities to correlate with known operational changes. Check if there are any open tickets regarding legitimate configuration changes. Contact the network administration team to cross-confirm if changes were authorized. |
| T2 Analyst Actions | Conduct a deeper investigation into the specific logs related to suspicion configuration changes. Utilize threat intelligence platforms to identify if any known TTP or IOCs are associated with the unusual activities detected. Coordinate with IT for a closer examination of the potentially compromised network boundary devices. |
| Containment and Further Analysis | Isolate the affected network devices by applying access restrictions to prevent further adversarial access. Back up current configurations and reset to known good states. Implement enhanced monitoring for further unauthorized access attempts. Conduct a full network traffic analysis to identify any additional affected systems. Document all findings and report to management for strategic remediation. |
