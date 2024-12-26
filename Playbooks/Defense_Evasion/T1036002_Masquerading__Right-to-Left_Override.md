# Masquerading:_Right-to-Left_Override - T1036002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1036.002 |
| MITRE Sub-TTP | T1036.002 |
| Name | Masquerading: Right-to-Left Override |
| Log Sources to Investigate | Monitor file system logs, particularly for name alterations involving non-printing characters like the RTLO (U+202E), which can be identified in filename anomalies. Security Information and Event Management (SIEM) solutions should be configured to detect suspicious file names. Windows Event Logs, particularly Security and Application logs, and Registry monitoring for filenames or paths containing RTLO characters should also be examined. |
| Key Indicators | Presence of RTLO (U+202E) within file names altering their appearance. Files with extensions like .scr, .exe disguised as .docx, .png, etc. Unusual registry key names displaying file type disguises. Deposition of unexpected file types in typically standard directories such as user downloads or temporary folders. |
| Questions for Analysis | Is the RTLO character present in any recently modified or created file names? Are there any reports from users receiving suspicious attachments or files? Do the apparent file types correspond with their actual file types upon inspection? Is the purported sender of files or attachments verified and trusted? |
| Decision for Escalation | Escalate to Tier 2 if any files are found to be using RTLO characters to disguise their true nature, especially if they are sourced externally or from unverified senders. Also escalate if there is evidence of user interaction with such files. |
| Additional Analysis Steps for L1 | Identify and list any files or registry entries that include the RTLO character. Cross-reference detected filenames with file hashes against threat intelligence feeds to check for known malicious indicators. Initiate open investigation alerts for potential phishing scenarios utilizing the RTLO character. |
| T2 Analyst Actions | Perform deeper analysis on identified RTLO files to confirm their suspicious nature, including static and dynamic analysis of involved files. Check historical logs for similar patterns or previous occurrences that match the RTLO usage. Corroborate findings with additional threat intelligence sources to validate the nature of the threat. |
| Containment and Further Analysis | Implement isolation protocols for affected systems if a malicious file is confirmed. Remove or quarantine suspicious files, and correct registry keys where necessary. Retrieve a copy of any confirmed malicious RTLO file, and perform a thorough malware analysis to understand scope and potential impact. Recommend user awareness training on identifying disguised file types and establishing email filters that detect non-printable character abuse. |
