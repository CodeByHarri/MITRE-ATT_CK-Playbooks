# Create_or_Modify_System_Process:_Launch_Daemon - T1543004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1543.004 |
| MITRE Sub-TTP | T1543.004 |
| Name | Create or Modify System Process: Launch Daemon |
| Log Sources to Investigate | Investigate system logs and security logs related to Launch Daemons on macOS devices. Examples: /var/log/system.log for detailed system events, Unified logs via Console app or 'log show' command for kernel and system-level events, and filesystem audit logs for unauthorized write access to /Library/LaunchDaemons or an unexpected creation/modification of plist files. |
| Key Indicators | 1. Suspicious plist files in /Library/LaunchDaemons with unexpected or obfuscated names.<br>2. Plist files with the 'RunAtLoad' parameter set to true, pointing to unknown or unexpected binary paths.<br>3. Unusual or new daemons that match known masqueraded service names or those that parallel legitimate macOS services but show anomalies in their execution paths. |
| Questions for Analysis | 1. Does the identified Launch Daemon match any known applications that are normally installed on the system?<br>2. Is the executable path pointed by the Launch Daemon plist file consistent with an expected software installation?<br>3. Are there multiple occurrences of the same suspicious behavior across different endpoints in the network? |
| Decision for Escalation | Escalate to Tier 2 if the Launch Daemon points to an unknown executable that cannot be associated with a legitimate application, shows a deviating path from standard application directories, or if there is evidence of persistent or replicated incidents across multiple systems. |
| Additional Analysis Steps for L1 | 1. Cross-reference the suspicious plist file names and paths against a whitelist of known good files and directories.<br>2. Use a file integrity monitoring tool to check for recent modifications to Launch Daemon directories.<br>3. Analyze external IP connections associated with the daemon's executable if the daemon is running. |
| T2 Analyst Actions | 1. Conduct a deeper inspection of the executable file hashed or identified in the Launch Daemon with a malware analysis tool.<br>2. Review correlated system event data during the period surrounding the Daemon file creation/modification.<br>3. Check other systems in the network for signs of similar unauthorized daemons to determine the scope of potential compromise. |
| Containment and Further Analysis | 1. Quarantine the system to isolate it from the network if a malicious Launch Daemon is confirmed.<br>2. Remove or disable the suspicious Launch Daemon by deleting the plist file or changing the 'RunAtLoad' setting.<br>3. Conduct a forensic analysis on the quarantined system to identify any further compromise or threat persistence mechanisms. 4. Update detection signatures based on findings to avert future exploitation. |
