# System_Information_Discovery - T1082

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1082 |
| MITRE Sub-TTP | T1082 |
| Name | System Information Discovery |
| Log Sources to Investigate | Potential log sources to investigate include system logs to look for command execution related to 'systeminfo' or 'systemsetup' on macOS. Also, network device logs, API logs from cloud providers like AWS CloudTrail, Azure Monitor, and GCP Cloud Logging to identify unusual API calls related to system information gathering. Check command-line activity logs for commands such as 'systeminfo', 'df -aH', and 'show version'. |
| Key Indicators | Look for process creation events concerning 'systeminfo', 'df -aH', 'systemsetup', and instances of CLI command execution on network devices. In cloud environments, API calls retrieving system data or querying metadata services beyond regular usage. Monitor unexpected or unscheduled user activities involving system information gathering. |
| Questions for Analysis | Is there a legitimate need for accessing detailed system information at the time it was requested? Was the activity executed by a known and authorized user or process? Does the frequency or pattern of the command usage deviate from the norm for the environment or user? Was the system information retrieval linked with other suspicious activities? |
| Decision for Escalation | Escalate to Tier 2 if the access was made by an unauthorized account, if associated with other suspect activities such as lateral movement, privilege escalation, and if originating from uncommon sources or IPs. Also, escalate if information was accessed using abnormal tools or techniques indicating compromise. |
| Additional Analysis Steps for L1 | Validate the identified system information discovery actions against baseline behavior. Review related user access logs and session information. Correlate with other system events and alerts to determine if there's an anomaly. Verify if there is any prior history or context to the activity that explains it as legitimate. |
| T2 Analyst Actions | Conduct a detailed investigation of the account and host involved in the system information discovery. Examine any surrounding activity such as additional reconnaissance or data exfiltration attempts. Perform timeline analysis to identify any other potential TTPs involved. |
| Containment and Further Analysis | If deemed malicious, contain the activity by isolating the affected host. Investigate user accounts involved for compromised credentials and reset passwords if necessary. Review and tighten access controls. Implement monitoring for similar commands in the future. Initiate incident response procedures including a full forensic analysis of the endpoint and potentially impacted systems. |
