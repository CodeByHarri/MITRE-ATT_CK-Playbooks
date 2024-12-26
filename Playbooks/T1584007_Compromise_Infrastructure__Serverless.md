# Compromise_Infrastructure:_Serverless - T1584007

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1584.007 |
| MITRE Sub-TTP | T1584.007 |
| Name | Compromise Infrastructure: Serverless |
| Log Sources to Investigate | Investigate logs related to cloud-based environments, specifically those that include serverless cloud infrastructure logs such as AWS CloudTrail, Google Cloud Audit logs, and Cloudflare Workers logs. Focus on logs that indicate the creation, modification, or unusual invocation of serverless functions. Network traffic logs from IDS/IPS systems should be reviewed for unusual patterns or connections involving cloud provider subdomains. Additionally, examine identity and access management (IAM) logs for changes or excessive access to serverless functions. |
| Key Indicators | Look for unusual or unauthorized changes or deployments in serverless environments. Additionally, monitor for unexpected network patterns involving known subdomains of cloud providers used for serverless functions. Keep an eye out for high-frequency invocation of serverless functions without a legitimate business process associated, especially if directly responding to IP addresses associated with malicious activities. Also, monitor for IAM roles or users becoming overly permissive unexpectedly. |
| Questions for Analysis | 1. Is there a legitimate reason for the serverless function deployment or change in configuration?<br>2. Do the IAM roles and permissions associated with serverless invocations align with typical usage patterns?<br>3. Are there any known security alerts or incidents currently involving the IP addresses linked to this serverless activity? 4. Is the traffic pattern observed typical for normal operations or does it reflect anomalous behavior? |
| Decision for Escalation | Escalate to T2 if there are indications of unauthorized changes or invocations in serverless functions, especially if coupled with anomalous network patterns or unapproved IAM permission modifications. Escalation is also necessary if communication with known malicious IPs or domains is detected. |
| Additional Analysis Steps for L1 | Review serverless function activity and IAM role logins for legitimacy based on employee roles and current projects. Validate the creation or modification of serverless functions against change management records. Cross-reference network connections with threat intelligence feeds to verify if they lead to known malicious IPs. |
| T2 Analyst Actions | Conduct deeper forensic analysis of the serverless runtime environment operations. Evaluate detailed serverless execution logs to identify potential injected code or scripts. Consult cross-team stakeholders to verify if the cloud infrastructure changes were authorized. Leverage threat hunting tools to identify similar patterns within other segments of the network. |
| Containment and Further Analysis | Revoke access or roll back unauthorized serverless function changes immediately. Isolate affected areas by changing IAM roles or temporarily suspending risky serverless functions. Coordinate with cloud providers for detailed analysis and remediation steps. Implement enhanced monitoring for further suspicious activities and reinforce alerting thresholds especially around serverless environments. |