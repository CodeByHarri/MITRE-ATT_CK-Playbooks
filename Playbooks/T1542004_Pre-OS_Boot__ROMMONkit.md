# Pre-OS_Boot:_ROMMONkit - T1542004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Persistence |
| MITRE TTP | T1542.004 |
| MITRE Sub-TTP | T1542.004 |
| Name | Pre-OS Boot: ROMMONkit |
| Log Sources to Investigate | Network device logs focusing on firmware updates, system boot events, and remote management sessions. Examples include Syslog messages, TFTP transfer logs, and change logs from network management systems. Monitor for unauthorized or unusual ROMMON versions and configurations. |
| Key Indicators | Unexpected or unauthorized ROMMON firmware version updates, unusual reboot events, TFTP transfers related to ROMMON updates, unauthorized changes in device settings during non-maintenance windows. |
| Questions for Analysis | Was there a scheduled maintenance during the time of the ROMMON update? Are the firmware versions consistent with approved updates? Were any unauthorized IP addresses involved in remote access or firmware transfer? |
| Decision for Escalation | Escalate if there is no scheduled maintenance, if firmware updates occur outside planned periods, involve unauthorized IPs, or if ROMMON versions do not match approved lists. |
| Additional Analysis Steps for L1 | Verify the change management records for any logged ROMMON updates. Correlate network logs to identify unexpected access times. Confirm if known IP addresses interacted with the network device during the event. |
| T2 Analyst Actions | Perform a deep dive into logs around the time of the update to look for any correlated suspicious activities. Analyze network traffic for signs of data exfiltration or lateral movement. Verify the integrity and source of the ROMMON image being used. |
| Containment and Further Analysis | Isolate the affected network device to prevent potential spread or further unauthorized access. Revert to a known good state by reloading authorized firmware versions. Implement additional monitoring for related devices to detect lateral movement or repeated access attempts. |
