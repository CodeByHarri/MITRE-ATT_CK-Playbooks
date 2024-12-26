# Domain_or_Tenant_Policy_Modification:_Group_Policy_Modification - T1484001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1484.001 |
| MITRE Sub-TTP | T1484.001 |
| Name | Domain or Tenant Policy Modification: Group Policy Modification |
| Log Sources to Investigate | Investigate Active Directory logs, particularly focusing on changes to Group Policy Objects (GPOs). Check for Group Policy Management Console logs and Event Viewer logs under the path 'Applications and Services Logs > Microsoft > Windows > GroupPolicy'. Additionally, look into SysVol share access logs and Windows Security Event Logs (specifically Event ID 5136 for Directory Service Changes or Event ID 4713 for GPO modification). These can provide insights when monitored by a SIEM platform. |
| Key Indicators | Look for unexpected modifications to files within the GPO path '<DOMAIN>\SYSVOL\<DOMAIN>\Policies\'. Be alert to changes in GPO settings such as 'ScheduledTasks.xml' within the GPO folders, changes to SeEnableDelegationPrivilege in 'GptTmpl.inf', and any unauthorized access or modification attempts by non-privileged accounts. Utilize scripts (e.g., 'New-GPOImmediateTask') used frequently for automation of GPO tasks. |
| Questions for Analysis | Did the changes to GPOs originate from known or recently unauthorized accounts? Are there any associated alerts or anomalies involving the same user accounts around the same timeframe? Were the changes made during non-business hours or from unusual IP addresses or hostnames? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized GPO changes are detected, especially when linked to non-admin or compromised accounts. Also escalate if correlated with abnormal activity patterns or if the modified permissions could lead to further security breaches (e.g., privilege escalation to Domain Admins). |
| Additional Analysis Steps for L1 | Verify user account permissions associated with the detected GPO changes. Cross-reference with historical logs for previous occurrences. Check for correlating alerts, investigate potential trigger sources, and review recent activity on associated hosts or accounts for anomalies. |
| T2 Analyst Actions | Conduct a deeper audit of GPO and Active Directory changes using security tools. Engage with security teams to review domain admin activity and gather forensic data from affected systems. Correlate the suspicious activity with network traffic logs to check for exfiltration attempts or lateral movement. |
| Containment and Further Analysis | Isolate affected accounts and review recent access permissions granted to them. Restore GPO settings from backup if unauthorized changes were made. Implement a temporary increase in monitoring of critical AD infrastructure. Perform a root cause analysis to identify the initial vector for GPO modification attempts and remediate vulnerabilities. |
