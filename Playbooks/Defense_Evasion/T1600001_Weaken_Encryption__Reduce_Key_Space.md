# Weaken_Encryption:_Reduce_Key_Space - T1600001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1600.001 |
| MITRE Sub-TTP | T1600.001 |
| Name | Weaken Encryption: Reduce Key Space |
| Log Sources to Investigate | Monitor network device logs, particularly focusing on configuration changes which might be stored in logs like syslogs, SNMP traps, and NetFlow data. Firewall logs should also be reviewed for any unauthorized access or use of specific administrative commands. An example could be syslog entries showing configuration changes or CLI command executions that are related to encryption settings. |
| Key Indicators | Unusual or unauthorized changes to encryption settings such as reduction in key size in network devices. Access logs showing connection from unknown or unexpected IP addresses, or the use of specialized commands focused on encryption parameters. Repeated failed or successful login attempts to network administration interfaces followed by configuration changes. |
| Questions for Analysis | Is the change in encryption settings authorized and documented by network operations? Were the configuration changes logged at an unusual time or accessed from an unknown IP address? Is there a pattern of unauthorized access attempts around the time of these changes? |
| Decision for Escalation | Escalate if there are unauthorized changes to the key size/settings, especially if this correlates with suspicious access logs. If there is no record of authorized personnel conducting these activities and any network access appears suspicious or compromised. |
| Additional Analysis Steps for L1 | Verify the authentication logs to correlate with known administrators' activity. Check for concurrent login attempts and any geographical anomalies related to network access. Confirm any pending or recent patches or updates that could coincide with these changes. |
| T2 Analyst Actions | Conduct deeper analysis of unauthorized access patterns. Work with network management to trace the origin of suspicious commands or access. Use threat intelligence to identify if any similar TTPs have been observed in related systems or organizations recently. |
| Containment and Further Analysis | Revert any unauthorized changes to encryption settings immediately. Isolate affected devices from the network to prevent further compromise. Conduct a full security assessment of affected devices and network segments for additional compromises. Implement additional monitoring for further suspicious activities and update security policies accordingly. |
