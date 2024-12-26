# Scheduled_Task_Job:_Cron - T1053003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution, Persistence, Privilege Escalation |
| MITRE TTP | T1053.003 |
| MITRE Sub-TTP | T1053.003 |
| Name | Scheduled Task/Job: Cron |
| Log Sources to Investigate | Investigate relevant log sources such as '/var/log/syslog' and '/var/log/cron.log' for Unix-like systems, which record cron job execution details. Also, review the crontab file paths specifically '/etc/crontab' and user-specific crontabs located in '/var/spool/cron/crontabs/'. Use audit logs and monitoring for 'crontab' command execution and mechanisms that change cron job configurations. |
| Key Indicators | Look for unexpected or unauthorized modifications to the crontab file. Detect 'crontab' command executions by non-administrative users. Sudden changes in predefined cron schedules or addition of new cron jobs that deviate from established patterns. Scripts or binaries being executed by cron jobs originating from uncommon directories. |
| Questions for Analysis | Is the cron job schedule change documented and approved as per change management processes? Does the script or binary being executed by the cron job exist within a suspicious or non-standard directory? Who executed the recent changes to the crontab file or executed the 'crontab' command? |
| Decision for Escalation | Escalate to Tier 2 if crontab entries are added or modified without appropriate change management documentation. Escalate if execution of scripts from suspicious directories is detected. Escalate if cron job changes are made by accounts not authorized for such changes. |
| Additional Analysis Steps for L1 | Verify the timestamp of crontab changes and correlate them with logon activities to determine the user context. Review any associated file transfers, downloads, or system updates around the cron job creation or modification time. Identify if the cron jobs run suspicious commands or reference known malicious script names or binaries. |
| T2 Analyst Actions | Analyze the content of any newly added or modified cron job scripts for malicious code. Determine the legitimacy of user accounts that made the changes by reviewing their activity history. Investigate any suspicious networks communications or connections initiated by processes executed via cron jobs. |
| Containment and Further Analysis | Disable suspicious cron jobs and block the execution of unexpected scripts or binaries. Reset credentials and privileges if access abuse is identified. Conduct a system-wide investigation to identify other signs of compromise. Educate users involved in unauthorized changes about relevant security policies and procedures. |
