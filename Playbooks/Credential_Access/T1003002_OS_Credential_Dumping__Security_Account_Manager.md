# OS_Credential_Dumping:_Security_Account_Manager - T1003002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1003.002 |
| MITRE Sub-TTP | T1003.002 |
| Name | OS Credential Dumping: Security Account Manager |
| Log Sources to Investigate | Investigate Windows Event Logs, particularly Security Logs for event IDs related to privilege escalation or unauthorized registry access (e.g., Event ID 4657 – Registry value change), and System Logs for suspicious account activities. Monitor Data Loss Prevention (DLP) logs for file access or transfer anomalies involving SAM or related files. Further, review any available logs from host-based intrusion detection systems (HIDS) or endpoint detection and response (EDR) systems for indications of known tools like Mimikatz or secretsdump.py being executed. |
| Key Indicators | Unexpected SYSTEM level privilege acquisition, Detection of known credential dumping tools (Mimikatz, pwdumpx.exe, secretsdump.py, or gsecdump), SAM data export activity (e.g., 'reg save HKLM\sam sam'), Unusual access to the SAM or SYSTEM registry hive, Access attempts on high-value accounts such as RID 500 Administrator or suspicion of extracted hash files. |
| Questions for Analysis | Was there unauthorized access to registry or registry keys containing user credentials? Are there any known indicators of credential dumping tools being present? Has there been any unusual access pattern involving high privilege accounts? Is there evidence of SYSTEM-level privileges without a legitimate business reason? |
| Decision for Escalation | Escalate to Tier 2 if there's confirmed evidence of credential dumping tools on systems, unauthorized SYSTEM level access, or detection of anomalies in registry access such as changes to key SAM or SYSTEM hives without a legitimate business purpose. |
| Additional Analysis Steps for L1 | Verify the source of SYSTEM level activities and registry access. Identify any anomalous user accounts accessing system resources logged at odd hours or with high privilege. Cross-reference detected hashes against known good configurations or past incident reports. |
| T2 Analyst Actions | Conduct a deeper analysis of potential malware or tools usage by inspecting memory dumps and file hashes. Validate detections with more advanced behavioral analysis using threat intelligence feeds. Investigate similar incidents on connected endpoints, and review network traffic for further signs of compromised data exfiltration or lateral movement. |
| Containment and Further Analysis | Isolate affected systems to prevent further data extraction or lateral movement. Reset compromised accounts and ensure password policies are enforced to mitigate hash reproduction. Review and revoke any unauthorized changes in system privileges. Conduct a post-incident forensic analysis to identify root cause and entry points, and update detection rules to prevent future occurrences. |
