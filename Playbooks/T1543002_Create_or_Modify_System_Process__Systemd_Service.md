# Create_or_Modify_System_Process:_Systemd_Service - T1543002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1543.002 |
| MITRE Sub-TTP | T1543.002 |
| Name | Create or Modify System Process: Systemd Service |
| Log Sources to Investigate | Monitor systemd logs typically located in /var/log/syslog, /var/log/messages, or /var/log/systemd. Look for unusual .service files or modifications in the /systemd/system or /systemd/user directories. Monitor for the creation of new .service files or changes in existing .service files using file integrity monitoring tools. Investigate authentication logs, such as /var/log/auth.log, for suspicious privilege escalation attempts. |
| Key Indicators | Creation or modification of .service files in unexpected directories. Presence of new symbolic links pointing to malicious payload locations. Unusual entries in the ExecStart, ExecStartPre, ExecStartPost, or User fields of .service files. Systemctl commands executed by non-privileged users or outside normal administrative processes. |
| Questions for Analysis | Is there a legitimate reason for the creation or modification of the .service file? Are there corresponding logs that align with known administrative actions? Does the User directive in the .service file imply unexpected privilege levels? Are there anomalous activities surrounding the time the .service change was observed? |
| Decision for Escalation | Escalate to Tier 2 if .service files are modified by non-administrators or outside regular change windows. Escalate if suspicious payloads or links are identified in .service files. Escalate when privilege escalation is implicated by analysis. |
| Additional Analysis Steps for L1 | Verify recent administrative activities or change requests that could justify service modifications. Compare .service files against known good configurations. Check for any associated suspicious network activity or outbound connections related to the time of modification. |
| T2 Analyst Actions | Perform a deeper analysis of the modified .service file and related system binaries. Investigate any associated processes running under unusual users or privileges. Correlate changes with threat intelligence to identify known malicious tactics. Review historical logs for preceding actions or indicators of compromise. |
| Containment and Further Analysis | Isolate the affected system to prevent further spread of potential malware. Replace compromised unit files with backups or known good versions. Consider disabling or removing malicious services. Conduct a full system scan using enhanced heuristics to discover other potential backdoors or persistence mechanisms. Collaborate with incident response teams to assess potential data exfiltration risks. |
