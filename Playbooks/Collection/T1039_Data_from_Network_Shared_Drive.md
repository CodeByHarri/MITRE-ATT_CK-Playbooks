# Data_from_Network_Shared_Drive - T1039

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1039 |
| MITRE Sub-TTP | T1039 |
| Name | Data from Network Shared Drive |
| Log Sources to Investigate | Investigate logs from network file servers, Windows Security Event Logs, file access logs, and network traffic logs. Examples include logs capturing file access events (Event ID 4663 for Windows), SMB/CIFS traffic logs from network monitoring solutions, and VPC flow logs in cloud environments where applicable. |
| Key Indicators | Unusual file access patterns from non-standard user accounts, especially those not typically accessing network shares. Access attempts from external IP addresses or off-hours access. High volume of read operations or data transfers over SMB. Execution of command-line utilities like 'cmd' or script engines for automated access and enumeration. |
| Questions for Analysis | Does the accessing account typically interact with these network shares? Are there signs of brute force or credential stuffing prior to access? Are files accessed unusual or sensitive based on historical access patterns? Did the access originate from an unexpected geographic location or IP address? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of anomalous access behavior, such as access by unusual user accounts, high data transfer volume, or if linked to a known or suspected compromised account. |
| Additional Analysis Steps for L1 | Cross-reference access logs with user activity, check for any recent account changes or password resets, and verify if additional suspicious login attempts occurred around the time of network share access. Look for any associated alerts of similar suspicious behavior preceding or following the access events. |
| T2 Analyst Actions | Perform deep packet analysis on suspicious traffic patterns, correlate with threat intelligence feeds for matching TTPs, and review user account history for other anomalous behavior. Examine any script executions or administrative tool use by the user. Investigate any related security incidents in the same timeframe. |
| Containment and Further Analysis | Isolate affected systems or user accounts exhibiting suspicious behavior. Reset credentials and enforce multi-factor authentication for impacted accounts. Conduct a thorough investigation of accessed files to determine if sensitive data was potentially exfiltrated. Implement enhanced monitoring on affected network shares and communicate findings with relevant stakeholders. |
