# Obfuscated_Files_or_Information:_Binary_Padding - T1027001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1027.001 |
| MITRE Sub-TTP | T1027.001 |
| Name | Obfuscated Files or Information: Binary Padding |
| Log Sources to Investigate | Security logs from Endpoint Detection and Response (EDR) systems to catch unexpected binary size increases. Network traffic logs for large file transfers, which may indicate padded binaries moving across the network. File integrity monitoring systems to detect changes in binary file checksums. Anti-virus and threat intelligence platform logs for missed detections or alerts that correlate with known TTP patterns. |
| Key Indicators | Presence of unusually large binary files on disk, especially if file growth aligns with known executable files. Detection of non-functional junk data within binaries. Changes in file checksums that do not correspond with version updates or legitimate modifications. Significant gaps between the file size and known legitimate software versions. |
| Questions for Analysis | Is there a legitimate reason for the observed file size increase of the binary? Are checksum changes aligning with verifiable software updates? Does the affected file have a history of changes that could indicate tampering? Are there any correlated alerts or historical patterns from this system/user that could support malicious intent? |
| Decision for Escalation | Escalate if the binary file has variations in size not explained by vendor updates. Escalate if multiple systems exhibit similar unexplained increases in binary file sizes. Consider the absence of valid justifications, unusual file transmission activities, or alignment with other known attack indicators as criteria for escalation. |
| Additional Analysis Steps for L1 | Check the file's creation and modification timestamps for inconsistencies. Validate file origin and authenticity against trusted sources. Cross-reference with recent software updates or patch notes. Search for similar anomalies across different endpoints in the network. |
| T2 Analyst Actions | Conduct deeper malware analysis on the binary to determine the nature and purpose of the padding. Use forensic tools to identify the origins of unexpected file changes. Monitor network for further propagation activity. Engage with threat intelligence to match observed indicators with known campaigns or malware families. |
| Containment and Further Analysis | Isolate affected endpoints to prevent potential spread. Preserve binary samples for future analysis. Engage with incident response teams to determine if quarantining additional systems is necessary. Update detection mechanisms to flag further occurrences of similar padding patterns. Conduct a retrospective hunt across historical data for any related missed detections. |
