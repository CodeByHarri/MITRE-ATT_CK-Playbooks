# Peripheral_Device_Discovery - T1120

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1120 |
| MITRE Sub-TTP | T1120 |
| Name | Peripheral Device Discovery |
| Log Sources to Investigate | Monitor system logs for unusual processes querying peripheral devices. Look into command history logs to identify commands often used to enumerate peripherals, such as 'lsusb', 'lspci', and 'system_profiler SPUSBDataType' on macOS and Linux. Device management and event logs, particularly in Windows (Event ID 2000-2001), can provide clues on peripheral enumeration and connections. |
| Key Indicators | Frequent or unusual execution of system queries (e.g., 'lsusb', 'lspci'); Access to device management utilities; Unexplained or unauthorized script activity; Logging peripheral device changes or access out of business hours. |
| Questions for Analysis | Was the query executed by a known administrative script, tool, or process? Is there a legitimate business need for this peripheral information access? Is the activity occurring from an unexpected source or at an unexpected time? Are there any known vulnerabilities in the peripherals queried? |
| Decision for Escalation | Escalate if peripheral queries originate from an unauthorized or rare source; if command execution is consistent with known malware or attack patterns; or if queries are part of a sequence of other reconnaissance or suspicious activities. |
| Additional Analysis Steps for L1 | Verify if peripheral discovery commands match any scripts or scheduled tasks. Check the system's user and group policies to ensure they're aligned with this type of behavior. Look at the system's history to see if this is a one-off event or part of a pattern. |
| T2 Analyst Actions | Conduct a deeper investigation into user activity and login history around the time of the event. Use threat intelligence feeds to match identified commands against known TTPs. Consider correlating events across multiple systems to determine if this is part of a coordinated effort. |
| Containment and Further Analysis | If deemed malicious, block associated IPs and user accounts to prevent further access. Isolate affected systems and conduct a forensic analysis for root cause identification. Update and apply security policies to prohibit unauthorized peripheral device queries. Consider deploying alerts for further suspicious peripheral device discovery activities. |
