# Command_and_Scripting_Interpreter:_AppleScript - T1059002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1059.002 |
| MITRE Sub-TTP | T1059.002 |
| Name | Command and Scripting Interpreter: AppleScript |
| Log Sources to Investigate | Investigate macOS System Logs with a focus on the command-line history (e.g., zsh_history, bash_history) to identify 'osascript' usage. Examine process monitoring and execution logs for abnormal usage of AppleScript. Check application logs for unexpected AppleEvent messages or unfamiliar processes initiated via AppleScript. Network traffic logs should be analyzed for unusual remote connections potentially initiated by scripts. |
| Key Indicators | Look for 'osascript' execution patterns, especially from non-standard directories or with unusual payloads. Identify AppleScripts that interact with applications or SSH connections unexpectedly. Monitor for frequent or irregular invocations of 'NSAppleScript' or 'OSAScript' within mach-O binaries. Check for scripts sent as plain text shell scripts with '#!/usr/bin/osascript'. |
| Questions for Analysis | Did 'osascript' execute from an unusual location or with unexpected parameters? Is there a legitimate business justification for the macOS user to execute AppleScript in this manner? Are there any signs of automated or scripted interactions with open applications or SSH connections during the observed activity? |
| Decision for Escalation | Escalate to Tier 2 if the investigation uncovers osascript executions that are not aligned with typical user behavior or if there's evidence of crafted scripts that interact with critical applications or sensitive sessions, such as SSH. Escalate if 'NSAppleScript' or 'OSAScript' invocations appear in conjunction with suspicious application behavior or remote connections. |
| Additional Analysis Steps for L1 | Verify the source of the AppleScript execution by checking user credentials and confirming their activity. Review recent system changes or application installations that could explain abnormal AppleScript use. Correlate with any other related alerts or indicators from security tools. |
| T2 Analyst Actions | Perform a deeper forensic analysis of the system and captured scripts to determine intent and impact. Validate the integrity of affected applications and OS components by checking for unauthorized modifications or persistence mechanisms. Coordinate with IT or security teams to verify the legitimacy of network connections and command origin. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent further unauthorized activities. Remove or quarantine malicious scripts and associated files. Conduct a comprehensive review of all recent AppleScript activities across endpoints. If applicable, reset credentials and tighten user permissions where unauthorized actions were detected. Summarize findings and update detection rules to prevent recurrence. |
