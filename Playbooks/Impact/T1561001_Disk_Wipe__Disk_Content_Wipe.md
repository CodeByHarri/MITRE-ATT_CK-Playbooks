# Disk_Wipe:_Disk_Content_Wipe - T1561001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1561.001 |
| MITRE Sub-TTP | T1561.001 |
| Name | Disk Wipe: Disk Content Wipe |
| Log Sources to Investigate | Investigate system logs such as Windows Event Logs, especially for unusual write operations to disk. Review Endpoint Detection and Response (EDR) logs for file overwrites and unusual use of disk-writing utilities. Monitor file access logs and examine network logs for suspicious propagation activities, particularly from known malware behaviors. Example log sources include Sysmon for detailed process write activities, and disk usage logs for rapid changes in free space on disk drives. |
| Key Indicators | Detection of sudden and large write activities to disk not correlated with legitimate system operations. Utilization of third-party drivers like RawDisk for unauthorized disk access. Anomalous high-frequency disk writing patterns. Propagation attempts over the network using known protocols like SMB with potentially stolen credentials. |
| Questions for Analysis | Are there recorded instances of unusual large-scale disk writing operations? Has there been unfamiliar driver installation like RawDisk on affected systems? Are other signs of worm-like behaviors observable across the network (e.g., rapid credential usage spikes or access attempts on multiple hosts)? |
| Decision for Escalation | Escalate to Tier 2 if large-scale overwriting patterns are confirmed, especially in conjunction with unusual driver installation or network propagation activities. Escalate if multiple systems in critical segments show signs of data wiping or if risk to business continuity is identified. |
| Additional Analysis Steps for L1 | Verify the authenticity and origin of any detected disk-writing utilities or drivers. Correlate the detected activities with known threat intelligence data for similar behaviors. Check integrity of critical system files and logs to assess any tampering or data anomalies. |
| T2 Analyst Actions | Identify and isolate the source of the unauthorized disk writes. Conduct deeper investigation into the potentially malicious files or drivers found, utilizing sandbox analysis if necessary. Perform comprehensive network scanning to identify potentially affected systems and propagation paths. Review user account logs for anomalies in access patterns or privilege escalations. |
| Containment and Further Analysis | Initiate network segmentation to contain further spread of the malware. Disable affected accounts and credentials that might be abused for further propagation. Implement recovery procedures to restore affected data from secure backups. Conduct in-depth forensic analysis on affected machines to determine root cause and create indicators of compromise (IOCs) to enhance future detection capabilities. |
