# Boot_or_Logon_Initialization_Scripts:_Login_Hook - T1037002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1037.002 |
| MITRE Sub-TTP | T1037.002 |
| Name | Boot or Logon Initialization Scripts: Login Hook |
| Log Sources to Investigate | Investigate system logs, specifically looking for changes to the /Library/Preferences/com.apple.loginwindow.plist file. Check Apple System Logs (ASL) for entries related to plist modifications. Review the command-line history (if possible) for unexpected use of the 'defaults' command utility. Monitor for any unusual logins that coincide with the times the plist is modified. |
| Key Indicators | Key indicators include the presence of unexpected entries in the /Library/Preferences/com.apple.loginwindow.plist file, especially under the LoginHook or LogoutHook keys. Watch for suspicious script paths that do not match typical administrative or IT operations. Look for unusual access or modification times for the plist file. |
| Questions for Analysis | 1. Has the /Library/Preferences/com.apple.loginwindow.plist file been modified recently?<br>2. Is there a legitimate purpose for the script execution via LoginHook or LogoutHook?<br>3. Are there unfamiliar or non-standard scripts referenced in the plist? 4. Were there any corresponding unusual login events around the same time the plist was changed? |
| Decision for Escalation | Escalate if there are unauthorized or suspicious modifications to the plist, especially if the scripts are not recognized or there is no documented, legitimate reason for their presence. Escalate if there are corresponding suspicious login events or command-line usage around the time of the modification. |
| Additional Analysis Steps for L1 | Verify the owner of the scripts found in the plist file and check their properties for anomalies. Review recent logs for unexpected login activities and cross-reference with the times scripts were added or modified. Search for any known malware patterns or flagged files/scripts using security tools. |
| T2 Analyst Actions | Conduct a deeper analysis of the scripts for malicious content or connections to known threat actor tactics. Check for other persistence mechanisms in place on the affected machine. Investigate any remote connections or external IP addresses the script may try to connect to. Consult threat intelligence for any similar techniques used in ongoing campaigns. |
| Containment and Further Analysis | Remove or neutralize the login hook entries if deemed malicious, and restore the plist file from a trusted backup. Disable execution of suspicious scripts and conduct a full malware scan on impacted systems. Monitor the network for any additional signs of compromise and ensure all systems are up to date on security patches. |
