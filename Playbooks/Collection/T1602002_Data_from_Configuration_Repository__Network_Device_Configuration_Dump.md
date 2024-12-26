# Data_from_Configuration_Repository:_Network_Device_Configuration_Dump - T1602002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1602.002 |
| MITRE Sub-TTP | T1602.002 |
| Name | Data from Configuration Repository: Network Device Configuration Dump |
| Log Sources to Investigate | Network device logs, SNMP logs, SMI logs, Configuration management system logs, NetFlow or sFlow data. Examples include: Cisco IOS log files, SNMP query logs from network monitoring tools, SMI access logs, and change logs from network configuration management systems. |
| Key Indicators | Unusual SNMP queries to network devices, unexpected configuration exports, repeated access to network device configuration storage locations, abnormal spikes in NetFlow or sFlow data indicative of large data transfers, accessing configuration files outside of normal maintenance schedules. |
| Questions for Analysis | Is there a legitimate reason for accessing or exporting the network device configuration? Were the SNMP queries or configuration exports conducted during normal operation hours? Do the IP addresses accessing the configuration match authorized admin sources? Is there any deviation from the established change management procedure? |
| Decision for Escalation | Escalate if unauthorized access to configuration files is confirmed, if there are signs of data exfiltration, or if configuration exports were made from an unusual source. Also, escalate if there's unexpected or repeated attempts to access configuration in a short timeframe. |
| Additional Analysis Steps for L1 | Verify access logs for the identified devices during the time of configuration access. Check the identity and authorization level of users initiating the access. Compare access patterns against normal baseline behaviors. Confirm whether the accessed data aligns with scheduled maintenance activities. |
| T2 Analyst Actions | Perform deeper investigation into the identified IP addresses and accounts accessing the configuration files. Correlate this activity with other alerts or suspicious behaviors in the logs. Review device configurations for signs of tampering or unauthorized changes. Work with IT to verify network paths for potential lateral movement. |
| Containment and Further Analysis | Immediately restrict access from suspicious IPs or users. Reset passwords and SNMP community strings if necessary. Ensure all network device firmware or software is up-to-date. Conduct a full audit of device configurations and revert any unauthorized changes. Analyze historical access logs to scope potential exposure, and reinforce network segmentation to limit unauthorized access. |
