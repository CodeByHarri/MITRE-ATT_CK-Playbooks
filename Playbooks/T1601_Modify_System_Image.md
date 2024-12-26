# Modify_System_Image - T1601

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1601 |
| MITRE Sub-TTP | T1601 |
| Name | Modify System Image |
| Log Sources to Investigate | Investigate logs from network device management systems and monitoring tools that track firmware updates or modifications. Examples include configuration management logs, SNMP traps, syslogs, and device-specific logs. Pay careful attention to logs showing firmware version changes, unexpected reboots, or configuration changes that may indicate malicious modifications. |
| Key Indicators | Suspicious modification or replacement of firmware files on network devices, unexpected changes in device configuration, unexplained reboots or system resets, and unauthorized access to device management interfaces. Additionally, look for discrepancies between the reported running version and what's expected or previously documented. |
| Questions for Analysis | Has there been any authorized change management activity that could explain these changes? Are there any accompanying anomalies, such as unauthorized access attempts or logins from unfamiliar IP addresses? Do the firmware modifications align with known IoCs or documented threats? Was there any alert from antivirus or intrusion detection systems coinciding with the observed changes? |
| Decision for Escalation | Escalate to Tier 2 if no authorized change requests can account for the modifications, if there are signs of unauthorized access, if there are alerts that suggest a compromise, or if there are indications of persistence mechanisms being installed. |
| Additional Analysis Steps for L1 | Review the change management records to confirm expected updates. Verify if there has been any unusual access to the device management interfaces and cross-reference with recent logins. Contact the device owner or admin for immediate verification if the changes were not part of a scheduled update. |
| T2 Analyst Actions | Conduct a deeper investigation into the unauthorized changes by analyzing network traffic for indications of tampering or data exfiltration. Correlate with threat intelligence to identify known attack patterns, and perform a thorough review of access logs and device configuration histories. Examine any associated network devices or systems for signs of compromise. |
| Containment and Further Analysis | Isolate affected devices from the network to prevent further malicious activity. Restore affected systems to a known good state using verified firmware images. Conduct a follow-up investigation to identify potential entry points or vulnerabilities exploited by the adversary. Implement mitigating controls, such as tighter access controls, to prevent recurrence. Engage with incident response teams to conduct post-mortem analysis and update organizational security measures accordingly. |
