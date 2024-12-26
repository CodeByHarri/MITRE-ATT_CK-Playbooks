# Weaken_Encryption - T1600

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1600 |
| MITRE Sub-TTP | T1600 |
| Name | Weaken Encryption |
| Log Sources to Investigate | ['Network device logs, specifically focusing on any changes to configuration files or system images.', 'Syslog from routers, switches, and firewalls for any unauthorized access or configuration changes.', 'Network traffic logs to detect anomalies or changes in encryption protocols or key length.', 'Intrusion Detection and Prevention Systems (IDPS) logs for alerts related to encryption or cryptographic anomalies.'] |
| Key Indicators | ['Unusual changes in encryption settings or protocols on network devices.', 'Unauthorized access to network devices, especially targeting the sections dealing with cryptographic functions.', 'A decrease in encryption key strength (e.g., shorter key lengths) without official change or documentation.', 'Configuration changes that disable or alter hardware-based cryptographic functions.'] |
| Questions for Analysis | ['Were there any scheduled maintenance activities or updates that correspond with the detected changes?', 'Have there been any unauthorized access attempts or successful logins to the affected devices?', 'Are there logs or alerts indicating a reduction in key space or encryption strength?', 'Is there any evidence of physical tampering or access noted in the security logs or surveillance records?'] |
| Decision for Escalation | ['Escalate if there are unauthorized configuration changes that weaken encryption.', "Escalate if there's evidence of an external actor's access or control over cryptographic modules.", 'Escalate if anomalies persist after initial remediation attempts or if multiple devices are affected.'] |
| Additional Analysis Steps for L1 | ['Verify if any legitimate patches or firmware updates could have triggered the change.', 'Correlate any suspicious activities with user and authentication logs.', 'Review recent access logs for unusual IP addresses, times, or user activities.', 'Examine the audit trail for any discrepancies in network device changes.'] |
| T2 Analyst Actions | ['Perform a deeper review of cryptographic settings before the anomaly and changes that have been made.', 'Engage with network administrators to confirm any sanctioned changes.', 'Conduct a comparative analysis of current configurations against known baselines.', 'Look for related activities across other network segments or devices.'] |
| Containment and Further Analysis | ['Reset affected devices to a secure state, using trusted firmware and configuration backups.', 'Increase monitoring of affected devices and comparable network segments.', 'Audit and enforce access controls to prevent future unauthorized changes to cryptographic settings.', 'Conduct a comprehensive vulnerability assessment to identify potential weaknesses in the current setup.'] |
