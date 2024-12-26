# Modify_Authentication_Process:_Reversible_Encryption - T1556005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access, Defense Evasion, Persistence |
| MITRE TTP | T1556.005 |
| MITRE Sub-TTP | T1556.005 |
| Name | Modify Authentication Process: Reversible Encryption |
| Log Sources to Investigate | Investigate Security Event logs from Domain Controllers for changes to account properties, especially logs related to Group Policy changes and user account modifications. Monitor PowerShell logs for execution of commands such as Set-ADUser with suspicious parameters. Analyze Active Directory replication logs and monitor for unexpected modifications to user objects, including userParameters field. Review audit logs for policy or GPO changes that enable reversible encryption. |
| Key Indicators | Commands executed with Set-ADUser -AllowReversiblePasswordEncryption set to $true. Changes to the userParameters attribute in Active Directory for a large number of users or specific high-value targets. Creation or modification of Fine-Grained Password Policies. Enablement of reversible encryption in security policy logs. |
| Questions for Analysis | Have there been recent modifications to Group Policy settings related to password management? Are there any suspicious accounts for which the AllowReversiblePasswordEncryption property has been enabled recently? Has there been a burst of PowerShell activity involving user property modifications? Are the changes authorized and do they correspond to legitimate software requirements? |
| Decision for Escalation | Escalate if unauthorized or unexpected changes to reversible password encryption settings are identified, if PowerShell commands altering user settings are found without proper justification, or if userParameters values have been altered unexpectedly for multiple accounts, especially administrative or sensitive accounts. |
| Additional Analysis Steps for L1 | Correlate account modifications with user activity logs to verify legitimacy. Cross-reference change logs with known patching or update windows to discount legitimate changes. Look for unusual patterns or frequency in the change of the AllowReversiblePasswordEncryption property. |
| T2 Analyst Actions | Perform deeper analysis on the origin of the PowerShell commands or scripts that made changes to account properties. Validate the integrity of the RASSFM.DLL to ensure it hasn't been tampered with. Cross-check user changes with access logs to detect possible unauthorized access. Interview relevant personnel for context on any policy changes. |
| Containment and Further Analysis | Disable reversible password encryption on any accounts where it was inappropriately enabled. Conduct a password reset for affected users as needed. Apply tighter monitoring on PowerShell and account modification logs for further suspicious activity. Consider implementing alerts for unauthorized changes to sensitive user properties or policies. |
