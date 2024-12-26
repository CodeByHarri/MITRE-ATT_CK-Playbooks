# Indicator_Removal:_Network_Share_Connection_Removal - T1070005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1070.005 |
| MITRE Sub-TTP | T1070.005 |
| Name | Indicator Removal: Network Share Connection Removal |
| Log Sources to Investigate | Review Windows Event Logs, specifically looking for event ID 5140 (A network share object was accessed) and event ID 5142 (A network share object was deleted) in Security Logs. Also inspect object access auditing logs and SMB session logs for any anomalies or unusual patterns related to network share connection removals. |
| Key Indicators | 1. Presence of command patterns like 'net use \\system\share /delete' in command line logs.<br>2. Unexplained or unauthorized network share disconnection entries in event logs or system logs.<br>3. Logs showing deleted or altered security descriptors for network shares may indicate tampering. |
| Questions for Analysis | 1. Was the command executed by a user with known administrative privileges?<br>2. Is there a valid business justification for removing the network share connection?<br>3. Has the user executed similar commands before, and are they within typical usage patterns? 4. Are there other related suspicious activities or alerts around the same timeframe? |
| Decision for Escalation | Escalate to Tier 2 if: 1. The command was executed by an unexpected user, especially outside of business hours.<br>2. There is no business justification available for the share deletion.<br>3. The activity corresponds with other suspicious alerts or activities suggesting possible lateral movement or data exfiltration. |
| Additional Analysis Steps for L1 | 1. Gather logs for the timeframe during which the deletion occurred.<br>2. Confirm the identity and role of the user who executed the command.<br>3. Check for any other network operations or processes initiated by the same user within the same timeframe. |
| T2 Analyst Actions | 1. Perform a deeper analysis of the user's recent activities to detect potential compromise or suspicious behavior.<br>2. Correlate the network share deletion with other logs, such as file access where sensitive or critical data is involved.<br>3. Utilize threat intelligence to assess whether this behavior is linked to known TTPs of specific threat actors. |
| Containment and Further Analysis | 1. If suspicious activity is confirmed, disable the affected user account and shared drives for further investigation.<br>2. Initiate a security incident response process, conducting root cause analysis.<br>3. Implement enhanced monitoring on potential alternate paths the adversary could exploit, and review security policies around share connection activities. |
