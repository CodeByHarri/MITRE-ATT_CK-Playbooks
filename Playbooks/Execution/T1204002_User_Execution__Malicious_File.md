# User_Execution:_Malicious_File - T1204002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1204.002 |
| MITRE Sub-TTP | T1204.002 |
| Name | User Execution: Malicious File |
| Log Sources to Investigate | Investigate email gateways for attachments sent to users, review endpoint detection and response (EDR) logs for execution of suspicious files, analyze file integrity monitoring (FIM) logs for unexpected file creation or modification events, and check web proxy logs if the file could have been downloaded from an external source. |
| Key Indicators | Discovery of unusual file types being executed such as .doc, .exe, or .scr; presence of newly created or modified files in user-accessible locations; unusual process creations linked to user interaction, such as Microsoft Word spawning command-line execution; filenames containing common masquerading tactics indicating legitimate documents (e.g., invoice.pdf.exe); alerts from security tools on file execution that match known malicious hash values. |
| Questions for Analysis | Was the suspicious file received through a known communication channel like email or file share? Did the user report any unexpected behavior or file executions? Have there been multiple instances of similar events from the same source IP or email address? Does the file exhibit characteristics of masquerading, such as suspicious extensions or misleading icons? |
| Decision for Escalation | Escalate if the file has been executed and resulted in known malicious behaviors, such as network connections to command and control servers, or if the file origin is linked to known threat actors or previously identified spearphishing campaigns. |
| Additional Analysis Steps for L1 | Verify the user's recent activity around the time of the suspicious file execution. Check email headers to trace the origin of any file attachments. Cross-reference file hashes with threat intelligence databases to identify known malware. Ask users if they recall specific instructions to open password-protected files that match the observed timeline. |
| T2 Analyst Actions | Perform in-depth analysis of executed files using sandbox environments. Reverse engineer the file if necessary to understand its behavior and purpose. Correlate findings with threat intelligence to identify if it's part of a larger campaign. Conduct a thorough search to identify lateral movement or persistence mechanisms introduced by the file. |
| Containment and Further Analysis | Implement endpoint isolation if active malicious activity is detected. Remove the malicious file and quarantine affected systems. Apply security patches and update endpoint protection configurations to mitigate vulnerabilities. Conduct a comprehensive review of firewall and network logs to block malicious IPs and domains associated with the file. |
