# Pre-OS_Boot:_TFTP_Boot - T1542005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Persistence |
| MITRE TTP | T1542.005 |
| MITRE Sub-TTP | T1542.005 |
| Name | Pre-OS Boot: TFTP Boot |
| Log Sources to Investigate | Network device logs (e.g., boot logs, configuration logs), TFTP server access logs, network traffic captures, syslog from network management systems, and configuration management logs. Examples: Monitor for unauthorized TFTP server IP addresses in device configuration, unusual TFTP activity, and changes to boot settings in device logs. |
| Key Indicators | Unexpected TFTP server addresses configured on network devices, unusual or unauthorized netbooting events, changes in boot sequence settings, logs showing access to TFTP servers not in the authorized list, and any 'Modify System Image' log entries. |
| Questions for Analysis | Has the TFTP server address in the network device configuration changed recently? Is the TFTP server being accessed not part of the known or authorized management infrastructure? Are there recent changes in boot sequence configuration? Are there logs of large data transfers indicating image downloads from TFTP servers? |
| Decision for Escalation | Escalate if unauthorized TFTP server addresses appear in configuration logs, if unexpected netbooting activity is detected, or if changes to boot sequence settings are observed that cannot be immediately explained. Any indication of the use of modified system images should also trigger escalation. |
| Additional Analysis Steps for L1 | Check network device configuration for recent changes, correlate these with known authorized changes or incidents. Review recent network traffic logs for TFTP traffic to and from unknown or suspicious IPs. Verify the integrity of the configuration management database to ensure no unauthorized changes. |
| T2 Analyst Actions | Conduct a deeper analysis of network traffic and behavior patterns around the time of detected anomalies. Analyze historical device configuration changes for pattern detection. Collaborate with IT operations for physical inspection of devices, if necessary, and verification of current device state versus expected state. |
| Containment and Further Analysis | Update device configurations to revert unauthorized changes, including resetting to authorized TFTP server addresses. Patch and update all network devices to prevent exploitation of known vulnerabilities. Monitor any device suspected to be compromised for further anomalous behavior. Isolate the device from the network if malicious activity is detected to prevent further spread. |
