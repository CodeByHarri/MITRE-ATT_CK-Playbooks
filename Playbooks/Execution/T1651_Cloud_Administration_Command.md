# Cloud_Administration_Command - T1651

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1651 |
| MITRE Sub-TTP | T1651 |
| Name | Cloud Administration Command |
| Log Sources to Investigate | Examine cloud service provider logs such as AWS CloudTrail or Azure Activity Logs to identify any command execution events in virtual machines. Also, review logs from AWS Systems Manager Run Command or Azure RunCommand for traces of abnormal usage. Look into IAM logs for any unauthorized access or privilege escalation attempts. |
| Key Indicators | Sudden or unusual commands executed within virtual machines, especially those not corresponding to normal operations. Anomalies in IAM roles or users initiating cloud management commands, particularly if they emerge from unknown IP addresses or geo-locations. A spike in the usage of cloud management services like AWS Systems Manager or Azure RunCommand. |
| Questions for Analysis | Has there been any recent account takeover or suspicious IAM activity? Are the command executions associated with known, trusted users or processes? Are there any geo-location anomalies in command executions? Is there any correlation with recent security advisories or threat intelligence information? |
| Decision for Escalation | Escalate to Tier 2 if there are indicators of an account compromise, such as unusual IAM activity, if the commands executed do not align with regular business operations, or if they're associated with known threat actor TTPs. Also, escalate if you find multiple failed attempts followed by a successful execution. |
| Additional Analysis Steps for L1 | Correlate IAM activity logs with command executions to identify any unauthorized access. Validate whether the IP addresses associated with the commands are known and approved. Check for any alerts or critical notifications in place around these services. |
| T2 Analyst Actions | Conduct a deeper forensic review of the compromised accounts or sessions. Validate if any unauthorized applications or backdoors have been installed. Perform threat intelligence correlation to determine if there is a larger campaign targeting the organization. |
| Containment and Further Analysis | Immediately disable any suspicious IAM accounts or services. Reset credentials for potentially compromised accounts. Conduct a full audit of configurations and permissions associated with cloud management services. Initiate a clean-up of any unauthorized scripts or processes on affected virtual machines. Monitor the environment for reattempts or further suspicious activity. |
