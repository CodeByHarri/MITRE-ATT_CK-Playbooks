# System_Time_Discovery - T1124

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1124 |
| MITRE Sub-TTP | T1124 |
| Name | System Time Discovery |
| Log Sources to Investigate | Investigate system logs from Windows Event Logs (specifically Security and System logs), Linux audit logs (/var/log/audit/audit.log), and macOS Unified Logs to detect commands related to time queries. Network device logs from Cisco devices for `show clock detail` and usage patterns. Collect network traffic data to and from NTP servers for unusual patterns. Utilize endpoint detection and response (EDR) solutions to track command line parameters such as 'net time', 'w32tm /tz', 'time()', and 'systemsetup'. |
| Key Indicators | Look for commands like 'net time \\hostname', 'w32tm /tz', 'GetTickCount()', 'systemsetup -gettimezone', 'timeIntervalSinceNow'. Presence of system calls for time functions on Linux, execution of 'show clock detail' command on Cisco devices. Unusual synchronization with non-standard NTP servers, or NTP-related network traffic patterns that deviate from the norm. |
| Questions for Analysis | Is there a legitimate business reason for querying system time in this manner? Is the activity coming from an authorized user or a known process? Does the querying process correspond to known legitimate operations (updates, scripts)? Are other suspicious activities or anomalies detected in conjunction with this query? |
| Decision for Escalation | Escalate to Tier 2 if the system time queries are associated with suspicious IP addresses or processes that typically don't perform such actions. Escalate if there is persistence of activity despite initial investigation outcomes, or if combined with other clear indicators of compromise. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the process/user invoking the time discovery commands. Cross-reference the IP addresses or hostnames with known threats or blacklists. Check if there are multiple instances or unsuccessful attempts to query the time indicating persistence or automated behavior. |
| T2 Analyst Actions | Analyze historical activity of involved users and systems for prior suspicious actions. Investigate network traffic for matching timestamps with known malicious actors. Consider running forensic analysis on affected systems for unauthorized changes or indicators of compromise. Utilize threat intelligence to correlate activity with known TTPs. |
| Containment and Further Analysis | If malicious activity is confirmed, quarantine affected systems to prevent lateral movement. Update firewall and endpoint security policies to block any identified malicious IP addresses or domains used during the attack. Conduct a broader network scan to identify other potentially compromised systems. Perform a thorough review of patch and time synchronization settings across the network to ensure no further vulnerabilities. |
