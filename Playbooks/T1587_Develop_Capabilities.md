# Develop_Capabilities - T1587

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1587 |
| MITRE Sub-TTP | T1587 |
| Name | Develop Capabilities |
| Log Sources to Investigate | Network traffic logs, system logs, development environment logs, and source control logs. Examples include git commit histories, changes to repositories, logs from Integrated Development Environments (IDEs), and network connections from development workstations. |
| Key Indicators | Significant changes in source code repositories not associated with known projects, unusual network activity from hosts typically used for development, creation or presence of newly compiled binaries or executables that are not documented, and the use of unique self-signed digital certificates. |
| Questions for Analysis | Are there unexplained changes in the code repositories? Does the network activity involving development machines seem abnormal considering usual patterns? Are there instances of newly compiled executables or binaries that do not match known projects? Has there been any use of unauthorized digital certificates? |
| Decision for Escalation | Escalate to Tier 2 if you observe substantial unexplained changes in code repositories, detect unique binaries that do not correspond with any known project, or identify abnormal network activity involving development workstations. |
| Additional Analysis Steps for L1 | Review recent commit logs for any unauthorized or undocumented changes. Cross-reference network logs to identify any development machines communicating with unknown or suspicious servers. Check for any unusual file creation events on systems typically used for software development. |
| T2 Analyst Actions | Conduct a deep dive into recent unauthorized changes and validate them with developers. Analyze network traffic to understand whether connections to known C2 servers or other suspicious destinations were made. Verify digital certificates to identify any unusual or unauthorized certificates being employed. |
| Containment and Further Analysis | Isolate affected systems that have been identified with unauthorized development changes or client communications. Conduct forensic analysis on these systems to identify potential creation or use of custom malware or exploits. Develop signatures or detection rules for any new binaries or executables that are not part of approved development processes. |
