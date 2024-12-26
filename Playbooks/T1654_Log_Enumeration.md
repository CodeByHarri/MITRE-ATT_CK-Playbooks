# Log_Enumeration - T1654

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1654 |
| MITRE Sub-TTP | T1654 |
| Name | Log Enumeration |
| Log Sources to Investigate | Investigate Windows Event Logs particularly Security and System logs accessed via wevtutil.exe or PowerShell. Review PowerShell logs for unusual or unauthorized script executions. Analyze audit logs from Azure or cloud infrastructure for the use of utilities like CollectGuestLogs.exe. In centralized logging environments, monitor SIEM alerts for anomalies in log access or export activities. |
| Key Indicators | Execution of wevtutil.exe or suspicious PowerShell commands related to log access. Use of the Azure VM Agent's `CollectGuestLogs.exe`. High-volume log file access or export activities. Unexpected access to SIEM or centralized log repositories. Log entries indicative of reconnaissance activities such as account enumeration, software discovery, or remote system discovery. |
| Questions for Analysis | Did the suspicious activity involve tools commonly used for log enumeration? Was the access to logs or their export authorized by a legitimate user or system process? Are there patterns of behavior consistent with reconnaissance activities? Is there evidence of bulk log export to an external destination? |
| Decision for Escalation | Escalate to Tier 2 if log enumeration activities are conducted by unauthorized users, tools, or processes, if there's evidence of bulk log export, or if the activity corresponds with potential reconnaissance patterns towards critical systems. |
| Additional Analysis Steps for L1 | Cross-reference the user or process executing log enumeration with known entities and roles. Check for recent changes in user roles/permissions that could justify log access. Verify if similar activities were conducted at other endpoints in the network. |
| T2 Analyst Actions | Conduct deeper investigation on affected systems to confirm whether tools used for log enumeration align with known adversary tactics. Review organizational policies around log access and verify adherence. Perform threat hunting to identify any lateral movement or other indicators of compromise. |
| Containment and Further Analysis | Isolate affected systems if unauthorized enumeration or data exfiltration is confirmed. Review and tighten log access controls, ensuring principle of least privilege is applied. Analyze network traffic to identify data exfiltration avenues and monitor for further adversarial movements. Coordinate with incident response team to remediate identified vulnerabilities. |
