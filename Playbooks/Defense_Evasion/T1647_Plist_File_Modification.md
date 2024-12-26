# Plist_File_Modification - T1647

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1647 |
| MITRE Sub-TTP | T1647 |
| Name | Plist File Modification |
| Log Sources to Investigate | Monitor logs from macOS file system activities, specifically targeting modifications to plist files within user and system directories. Use tools like endpoint detection and response (EDR) solutions that track file changes, and employ macOS unified logs for any plist file change events. Examples include logs from 'fs_usage' or 'audit' that can capture file modification events. |
| Key Indicators | Unusual modifications to plist files outside of software update windows, such as changes to `~/Library/Preferences/com.apple.dock.plist` or `info.plist` files. Presence of non-standard applications or paths in `info.plist` entries. Addition or modification of keys such as `LSUIElement` or `LSEnvironment` in plist files. |
| Questions for Analysis | Is the plist file modification corroborated by other unusual system events? Does the modified plist file correspond to a known or suspicious application? Are there other indications of persistence mechanisms, such as scheduled tasks or unusual startup items? |
| Decision for Escalation | Escalate to Tier 2 if the plist modifications are not associated with legitimate update activities or known applications. Escalate if there is evidence of additional persistent artifacts or suspect processes running in conjunction with the plist modification. |
| Additional Analysis Steps for L1 | Verify the last user or process that modified the plist file using system logs. Check for associated file paths and processes linked to the modification. Gather user activity logs around the time of the plist file change to identify potential unauthorized access. |
| T2 Analyst Actions | Conduct a deeper analysis of the modified plist file contents. Assess the associated application or service for potential exploitation or evidence of malice. Look for patterns of similar modifications across other systems in the network. |
| Containment and Further Analysis | Isolate systems showing persistent malicious plist modifications from the network. Restore modified plist files from backups if applicable and verify the integrity of the related applications. Engage in a full system malware scan and review network traffic for potential C2 communications linked to the compromised machine. |
