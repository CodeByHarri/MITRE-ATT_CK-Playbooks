# Forced_Authentication - T1187

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1187 |
| MITRE Sub-TTP | T1187 |
| Name | Forced Authentication |
| Log Sources to Investigate | Windows Security Event Logs, SMB server logs, Web Proxy logs, IDS/IPS alerts, Network traffic capture (specifically TCP/UDP on ports 445 for SMB, and 80/443 for WebDAV). Example: Event ID 4625 for failed logins, indicating repeated forced authentication attempts. |
| Key Indicators | SMB traffic initiated from internal systems to unexpected or external IP addresses, especially those not standard within the organization's normal traffic patterns. Unusual access attempts to files or shares that contain authentication responses. Sudden spikes in failed authentication attempts in logs. Presence of unexpected .LNK or .SCF files with external references within user directories. |
| Questions for Analysis | Is the suspicious traffic originating from a valid internal IP? Are there any legitimate reasons or business processes that would justify this communication? Do the detected files (.LNK, .SCF) have legitimate creation metadata, such as known or expected applications creating them? Are there correlated indicators from IDS/IPS for similar IP traffic alerts? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed SMB traffic to unapproved external servers, unauthorized file access attempts, or if hash extraction attempts are detected. Also, if suspicious .SCF or .LNK files seem to be proliferating throughout multiple systems, indicating potential spread. |
| Additional Analysis Steps for L1 | Verify IP addresses involved against corporate whitelist. Check for recent file activity or changes in potentially compromised user accounts. Look for corresponding failed login attempts around same timestamps. Cross-reference with DLP solutions for any data exfiltration signs. |
| T2 Analyst Actions | Conduct deeper inspection into network traffic for anomalous behavior not sufficiently explained by Tier 1 findings. Use threat intelligence feeds to corroborate whether involved IPs are linked to known threat actors. Perform hash analysis to identify possible brute force indication. Engage with users to determine any legitimate business process anomalies. |
| Containment and Further Analysis | Block identified IPs or domains associated with threats at network perimeter or proxy. Quarantine affected machines and disable accounts involved in suspicious activity. Initiate password reset procedure with heightened security measures for affected accounts. Analyze extracted hashes for brute force attempts and correlate with recent successful authentications. |
