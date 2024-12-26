# Weaken_Encryption:_Disable_Crypto_Hardware - T1600002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1600.002 |
| MITRE Sub-TTP | T1600.002 |
| Name | Weaken Encryption: Disable Crypto Hardware |
| Log Sources to Investigate | Monitor logs from network devices such as routers, switches, and firewalls. Specifically, look for logs related to system configuration changes, especially those involving encryption settings. Examples include syslog from network devices, SNMP traps showing configuration changes, and logs from network management systems indicating any modifications of hardware settings. |
| Key Indicators | Unusual alterations in the encryption settings of network devices. Sudden switch from hardware-based encryption to software-based encryption without authorized configuration change. Log entries indicating alterations to encryption parameters or device reboots coinciding with configuration modifications without scheduled maintenance. |
| Questions for Analysis | Was there a scheduled maintenance window that could explain these configuration changes? Are there any corresponding log entries that show a history of authorized access to the device? Have there been any reports of related network performance or security issues? Is the device broadcasting any alerts or error messages related to encryption functions? |
| Decision for Escalation | Escalate to Tier 2 if there is no record of authorized configuration change during the suspected time window. Also escalate if the device logs indicate unauthorized access or if there are multiple alerts from different devices showing similar patterns of encryption configuration changes. |
| Additional Analysis Steps for L1 | Verify the change management records for any authorized changes to encryption settings. Correlate timestamps of the observed changes with operator access logs. Validate current device configuration against known baselines, check network performance metrics post-configuration change for anomalies. |
| T2 Analyst Actions | Conduct a thorough review of the access logs for any unauthorized access attempts. Compare the current device configuration against a backup or previously validated configuration. Check for any malware or unauthorized scripts on the device that may have been used to alter encryption settings. Utilize vulnerability scanning tools to detect potential exploit paths used. |
| Containment and Further Analysis | If unauthorized changes are confirmed, isolate the affected device from the network to prevent further compromise. Restore encryption settings using a known good configuration. Increase monitoring of similar devices within the network to detect any propagation of the threat. Conduct a forensic analysis on the device to determine the entry point and methods used by the adversary. |
