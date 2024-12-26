# Lateral_Tool_Transfer - T1570

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Lateral Movement |
| MITRE TTP | T1570 |
| MITRE Sub-TTP | T1570 |
| Name | Lateral Tool Transfer |
| Log Sources to Investigate | Monitor logs from file transfer services and protocols, such as SMB logs, RDP usage logs, and logs from tools like scp, rsync, or ftp. Network traffic logs can help identify unusual file transfer activities. Security logs from cloud applications like Dropbox or OneDrive should also be reviewed to detect synchronization of unusual files. |
| Key Indicators | Unusual increase in file transfer activities over SMB or RDP, unexpected connections from non-standard devices to network shares, transfers using less common commands like scp or rsync on Windows, detection of large data uploads to cloud services, or syncing of malicious files. |
| Questions for Analysis | Are the file transfers originating from known and trusted sources within the network? Do the file sizes or types align with normal business operations? Are there any patterns of failed login attempts or unauthorized access attempts associated with these transfers? |
| Decision for Escalation | Escalate if file transfer activities involve sensitive or critical files, are initiated from newly detected or suspicious IP addresses, involve tools not normally used by users, or are outside normal business hours without a clear business justification. |
| Additional Analysis Steps for L1 | Verify the user and device context of the file transfer events. Check for any associated alerts such as failed login attempts or privilege escalation events. Review past transfer activities of the user or device involved for any abnormal patterns. |
| T2 Analyst Actions | Conduct a deeper investigation into the intent and potential impact of the file transfers. Correlate with other suspicious activities in the environment. Check endpoint protection logs for any malicious indicators on the involved devices. Collaborate with IT to verify the legitimacy of the tools used for transfer. |
| Containment and Further Analysis | Temporarily isolate affected systems to prevent further unauthorized transfers. Collect and analyze file transfer logs for detailed paths and files involved. Work with relevant teams to patch vulnerabilities that may have been exploited. Review and tighten access controls on file transfer protocols and services. |
