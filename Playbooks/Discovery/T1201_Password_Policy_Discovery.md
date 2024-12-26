# Password_Policy_Discovery - T1201

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1201 |
| MITRE Sub-TTP | T1201 |
| Name | Password Policy Discovery |
| Log Sources to Investigate | Monitor logs from command-line utilities, system event logs, and API calls. Examples include:<br>- Windows Security and System Logs: Check for execution of 'net accounts' or 'Get-ADDefaultDomainPasswordPolicy'.<br>- Linux Auth Logs: Investigate logs for commands like 'chage -l <username>' or 'cat /etc/pam.d/common-password'.<br>- macOS Unified Logs: Look for instances of 'pwpolicy getaccountpolicies'.<br>- Cloud Service Logs: AWS CloudTrail logs for 'GetAccountPasswordPolicy' API calls.<br>- Network Device Logs: Logs from device CLI commands such as 'show aaa'. |
| Key Indicators | Key indicators include:<br>- Execution of commands accessing password policy settings (e.g., 'net accounts' on Windows, 'chage -l' on Linux).<br>- High frequency or unusual API calls related to password policy discovery in cloud environments.<br>- Access to network devices with commands to dump password policy information (e.g., 'show aaa'). |
| Questions for Analysis | Questions include:<br>- Was the action initiated by a known admin account at a typical time?<br>- Is this behavior aligned with known maintenance activities or an active IT project?<br>- Are there other correlated indicators of compromise (e.g., lateral movement, privilege escalation attempts)? |
| Decision for Escalation | Escalate to Tier 2 if:<br>- Unusual patterns or usage of these commands do not align with regular administrative activities.<br>- The originating user or IP is unknown or does not match legitimate activities.<br>- Other suspicious activities accompany the password policy discovery attempts. |
| Additional Analysis Steps for L1 | Steps include:<br>- Verify the user account and IP address against known and trusted admin resources.<br>- Check the pattern of access: Is this a singular event or part of a sequence?<br>- Review user activity logs for abnormal login attempts or new software installations. |
| T2 Analyst Actions | Tier 2 actions include:<br>- Conduct deeper investigation into the timeline of events, including prior and subsequent actions surrounding the discovery attempt.<br>- Analyze network traffic for any data exfiltration or outbound connections following the policy inquiry.<br>- Review the endpoints involved for potential indicators of compromise or unauthorized tools. |
| Containment and Further Analysis | Steps to take:<br>- If unauthorized access is confirmed, isolate the affected systems to prevent further compromise.<br>- Change credentials for potentially impacted accounts and review authorization settings.<br>- Perform a full malware scan and forensic analysis on affected devices to identify any persistence mechanisms or lateral movement tactics. |
