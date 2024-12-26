# Input_Capture:_Web_Portal_Capture - T1056003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection, Credential Access |
| MITRE TTP | T1056.003 |
| MITRE Sub-TTP | T1056.003 |
| Name | Input Capture: Web Portal Capture |
| Log Sources to Investigate | Web server logs, VPN access logs, and application logs from externally facing portals. Examples include IIS/Apache logs for web services, VPN logs showing unusual login times or IP addresses, and any custom application logging that tracks authentication attempts and page access. |
| Key Indicators | Unexpected changes in web portal files or configurations, unusual sequence of failed login attempts followed by a success, discrepancies between source IPs during logins, elevated or unauthorized access requests, and presence of new or unexpected scripts or binaries in the web server directories. |
| Questions for Analysis | Are there any recent changes to the web portal application code? Are there login anomalies such as logins from unusual geographical locations or at odd times? Are there unexpected attempts to access administrative functions on the web portal? Are there discrepancies in user-agent strings or deviations in typical login patterns? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of unauthorized changes to web portal files, if logs indicate successful logins from suspicious IP addresses following failed attempts, or if suspicious scripts consistent with keylogging capability are detected on the web server. |
| Additional Analysis Steps for L1 | Review recent backups of the web portal to identify any unauthorized changes. Cross-reference VPN or web server logs with user activity to look for anomalies. Check for the presence of unexpected scripts or binaries in server directories. Verify file integrity using checksums or file modification timestamps. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of compromised systems, examining any suspicious scripts in detail to confirm their functionality. Collaborate with IT to review affected systems and validate any changes made to configurations or applications. Work with IAM to verify account ownership and mitigate unauthorized access. |
| Containment and Further Analysis | Isolate the compromised web server or service. Block IP addresses found to be suspicious in the logs. Conduct a detailed malware analysis on detected scripts or binary payloads. Ensure all web and VPN software is updated and patched. Review and enhance MFA and monitoring for all externally facing services. |
