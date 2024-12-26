# Command_and_Scripting_Interpreter:_Unix_Shell - T1059004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1059.004 |
| MITRE Sub-TTP | T1059.004 |
| Name | Command and Scripting Interpreter: Unix Shell |
| Log Sources to Investigate | Collect and examine logs from Syslog for command executions, especially those initiated through SSH sessions. Check Bash history files (.bash_history) for any unusual or unauthorized command sequences. Audit logs related to user authentication and command execution that can be configured in /etc/audit/audit.rules. Monitor Network flow logs for unusual outbound connections that may originate from scripts. |
| Key Indicators | Unusual command executions or script running by unexpected users, especially those requiring root access. Presence of unauthorized SSH connections. Repeated login attempts followed by successful command executions. Network activity to unknown external IPs showing signs of data exfiltration or command and control communication. |
| Questions for Analysis | Are there any uncommon or complex commands executed by non-admin users? Have there been recent remote connections or unexplained SSH logins preceding the command execution? Are the commands or scripts connecting to suspicious external IP addresses or domains? |
| Decision for Escalation | Escalate to Tier 2 if commands or scripts run by unauthorized users involve sensitive data or privileged access. Escalate if there is evidence of scripts downloading files from or uploading to external hosts. Also escalate if there are indications of lateral movement across hosts. |
| Additional Analysis Steps for L1 | Review corresponding Syslog entries around suspicious command executions. Examine user profiles and access logs of those initiating commands. Capture suspicious commands or scripts for further review. Check for any recent changes to .bashrc, .profile or cronjob configurations. |
| T2 Analyst Actions | Perform a deeper investigation into the source and intent of suspicious scripts. Cross-reference network logs with suspicious IP addresses for any known threat signatures. Conduct a file integrity check to identify any unauthorized changes in key system files. Use endpoint detection and response tools to verify if other systems have been similarly affected. |
| Containment and Further Analysis | Isolate affected hosts to prevent further malicious activity. Disable suspected user credentials and establish two-factor authentication. Filter outbound traffic to suspicious IP addresses and block unknown domains. Conduct a thorough review of affected systems to determine the scope and impact. Schedule regular audits and harden command execution permissions to mitigate future risk. |
