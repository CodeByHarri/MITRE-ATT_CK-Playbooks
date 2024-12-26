# Data_from_Configuration_Repository - T1602

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1602 |
| MITRE Sub-TTP | T1602 |
| Name | Data from Configuration Repository |
| Log Sources to Investigate | Configuration management system logs, network flow data, SNMP trap logs, system administrator access logs, and VPN logs. Examples include SNMP server logs, Cisco router configuration logs, or logs from management platforms like Ansible, Puppet, or Chef. |
| Key Indicators | Unusual access to configuration repositories at odd hours, large data transfers from configuration management systems, access attempts from unfamiliar IP addresses, unauthorized SNMP requests, and repeated failed login attempts to management interfaces. |
| Questions for Analysis | Was the access to the configuration repository during or outside of usual business hours? Does the source IP of access match known locations for system administrators? Was there significant data transferred that is not typical for regular configurations? Are there repeated access attempts from an unknown or foreign IP address? |
| Decision for Escalation | Escalate to Tier 2 if abnormal behavior is identified, such as access during non-business hours by unknown entities or significant amounts of data accessed unexpectedly. Also, escalate if there are multiple indicators suggesting a coordinated effort or if initial analysis shows high potential for a breach. |
| Additional Analysis Steps for L1 | Verify the IP addresses accessing the configuration repositories against a whitelist of known administrator IPs. Check for any correlating alerts from intrusion detection systems. Cross-reference network packet captures for unusual traffic patterns. |
| T2 Analyst Actions | Conduct deeper traffic analysis to pinpoint anomalies, involve the security information and event management (SIEM) platform for correlating events, and verify user activity logs to confirm whether the access was legitimate or not. Engage with system owners to validate if the access was part of a scheduled task. |
| Containment and Further Analysis | Isolate the potentially compromised systems immediately from the network. Secure or change credentials for access to configuration management systems. Implement stricter access controls through multi-factor authentication. Conduct a full audit on logs to ascertain the extent of access and determine if data exfiltration occurred. Consider restoring systems from a secure backup if compromise is confirmed. |
