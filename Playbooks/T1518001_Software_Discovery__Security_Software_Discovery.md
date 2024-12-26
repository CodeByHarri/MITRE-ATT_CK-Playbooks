# Software_Discovery:_Security_Software_Discovery - T1518001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1518.001 |
| MITRE Sub-TTP | T1518.001 |
| Name | Software Discovery: Security Software Discovery |
| Log Sources to Investigate | Investigate system logs related to process execution, such as Windows Security Event Logs (Event IDs 4688 for process creation), PowerShell logs, Sysmon logs (if installed), and endpoint detection logs. Additionally, for cloud environments, audit logs from AWS CloudTrail, Azure Activity Logs, and Google Cloud Audit Logs should be reviewed for API calls related to service discovery. |
| Key Indicators | Look for command execution patterns involving tools like 'netsh', 'reg query', 'dir', and 'tasklist'. On macOS, check for processes querying LittleSnitch or KnockKnock. In cloud environments, monitor API calls to access metadata or fetch instance resource states (e.g., DescribeInstances in AWS). Unusual or unauthorized script executions performed via command-line interfaces can also be indicators. |
| Questions for Analysis | Is there an anomalous use of 'netsh', 'reg', 'dir', or 'tasklist' that is not part of documented business processes? Are there new users or IPs making API calls in the cloud environment? Is there any deviation in baseline cloud monitoring agent behaviors? |
| Decision for Escalation | If suspicious commands are run by accounts without administrative roles or originating from unauthorized devices or locations, escalate. Additionally, escalate if cloud API calls are made from irregular IP addresses or if there's a sudden spike in service discovery-related actions. |
| Additional Analysis Steps for L1 | Verify the user account and the legitimacy of processes or scripts executed. Cross-check against recent authorized IT changes. Review execution timelines to see if they correspond with known scheduled tasks or maintenance. |
| T2 Analyst Actions | Conduct detailed endpoint forensics on affected machines. Analyze execution and access logs to trace the origin and context of execution. If applicable, use threat intelligence to correlate discovered indicators with known threat actor techniques. |
| Containment and Further Analysis | Isolate affected systems in quarantine network environments to prevent further spread. Implement blocking or alerting rules on security software for detected malicious command patterns. Perform a comprehensive audit of cloud IAM roles and permissions, ensuring least privilege access is maintained. |
