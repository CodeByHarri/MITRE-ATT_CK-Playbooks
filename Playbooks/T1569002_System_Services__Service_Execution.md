# System_Services:_Service_Execution - T1569002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1569.002 |
| MITRE Sub-TTP | T1569.002 |
| Name | System Services: Service Execution |
| Log Sources to Investigate | Windows Event Logs (specifically Security and System logs), Sysmon logs for service creation and execution, Firewall logs to check for remote connections, Endpoint Detection and Response (EDR) alerts, and any logs from service management utilities like sc.exe or PsExec. For example, Event ID 7045 could indicate a new service installation, and Event ID 4688 could indicate a new process has been created. |
| Key Indicators | Unexpected creation or modification of Windows services; Event ID 7045 indicating a service was installed; Unusual use of sc.exe or PsExec with switches that suggest execution or service manipulation; Connections from unusual external IPs to ports associated with SMB (TCP 445) or RPC (TCP 135); Absence of Digital Signature in new service executables. |
| Questions for Analysis | Is there any legitimate business justification for the service creation or modification? Are the source IP addresses, users, or systems initiating these actions known and authorized? Do the binaries or scripts associated with these actions have valid digital signatures from trusted entities? Are there concurrent alerts or anomalies associated with these actions? |
| Decision for Escalation | Escalate to Tier 2 if the service creation or modification is unauthorized, if the involved systems are critical to operations, if the activity is associated with known IOCs or TTPs of active threats, or if it is executed from external or untrusted IP addresses. |
| Additional Analysis Steps for L1 | Review the context of the service creation or modification, including timings, associated user accounts, and purpose. Validate whether recent security patches have been applied that might affect service configurations. Check for correlated alerts or suspicious activities in other domains, such as network, web, or email logs. |
| T2 Analyst Actions | Conduct a deeper investigation into the associated binaries, including hash analysis and behavioral analysis using a sandbox environment. Query the environment for other hosts that have shown similar activity. Use threat intelligence feeds to match the activity against known IOCs. Assess the potential impacts on systems or data if the execution was malicious. |
| Containment and Further Analysis | If malicious activity is confirmed, isolate the affected systems to prevent lateral movement. Utilize system backups to restore any impacted services or configurations. Perform a comprehensive system scan to identify additional malware artifacts or modifications. Initiate password resets for affected user accounts and monitor for subsequent reauthorization attempts. Recommend network segmentation to reduce risk of similar tactics succeeding in the future. |
