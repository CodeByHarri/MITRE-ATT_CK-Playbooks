# Modify_Authentication_Process:_Pluggable_Authentication_Modules - T1556003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access, Defense Evasion, Persistence |
| MITRE TTP | T1556.003 |
| MITRE Sub-TTP | T1556.003 |
| Name | Modify Authentication Process: Pluggable Authentication Modules |
| Log Sources to Investigate | Monitor PAM-related logs including auth logs (e.g., /var/log/auth.log, /var/log/secure on Linux systems) for suspicious activity such as unexpected modifications or access patterns. Additionally, examine file integrity monitoring solutions to detect unauthorized changes to PAM configuration files and modules like /etc/pam.d/* or libraries such as pam_unix.so. |
| Key Indicators | Unusual modifications to PAM configuration files or binaries (e.g., checksum changes in pam_unix.so), the creation or modification of files in /etc/pam.d/, log entries that show authentication events with non-standard parameters or backdoor access, and suspicious user account activity during off-hours. |
| Questions for Analysis | Have there been recent updates or patches to PAM-related files, and are the changes expected? Are there any unusual account activities that correlate with known PAM modifications? Do log entries indicate abnormal access attempts or patterns that could imply tampering? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized changes to PAM files or configurations are detected, or if analysis reveals abnormal behavior or indicators suggest tampered authentication processes. Particularly prioritize if there's evidence of credential harvesting or login bypass attempts. |
| Additional Analysis Steps for L1 | Verify the integrity of PAM modules using checksums or hashes against known-good versions. Review recent changes and authorizations in PAM configuration files. Correlate any anomalies with recent user or system activity logs. |
| T2 Analyst Actions | Perform deeper forensics on compromised hosts, including examining historical logs and system snapshots to trace modifications. Isolate affected endpoints and verify backup integrity for affected PAM modules. Identify any further signs of lateral movement or data exfiltration. |
| Containment and Further Analysis | Revert any unauthorized PAM configuration or module changes to known-good states and apply patches where necessary. Conduct a comprehensive review of affected systems and users for potential further compromises. Implement enhanced monitoring and alerting for PAM-related activities moving forward. |
