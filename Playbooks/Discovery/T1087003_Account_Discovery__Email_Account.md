# Account_Discovery:_Email_Account - T1087003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1087.003 |
| MITRE Sub-TTP | T1087.003 |
| Name | Account Discovery: Email Account |
| Log Sources to Investigate | Review PowerShell logs for execution of cmdlets like Get-GlobalAddressList, including details such as who executed the cmdlet and the time of execution. Investigate Exchange Server logs for patterns of accessing the Global Address List. For Google Workspace, check admin audit logs for unusual access or downloads of the Google Workspace Directory. |
| Key Indicators | Unusual or unauthorized execution of Get-GlobalAddressList command in PowerShell audit logs. Sudden spikes in directory information access or exports within Exchange or Google Workspace logs. Unexpected or failed login attempts or script executions accessing GAL or directory services. |
| Questions for Analysis | Was the Get-GlobalAddressList command executed during unusual hours? Was it performed by a user account not typically involved in IT or administrative tasks? Is there any record of the potentially compromised account performing other unexpected activities? Is there evidence of multiple failed login attempts prior to successful access? |
| Decision for Escalation | Escalate to Tier 2 if the PowerShell cmdlet was executed from an unknown, unauthorized, or suspicious IP address, by a user who does not typically require this access, or during unusual hours. Also escalate if there's evidence of correlated suspicious activities like data exfiltration attempts following the access. |
| Additional Analysis Steps for L1 | Confirm the identity of the user account involved in the activity and validate with asset inventory records. Review recent changes in user permissions or configurations. Check for recent security alerts related to the account or system involved. |
| T2 Analyst Actions | Conduct a deeper analysis of network traffic logs for any data transfers from Exchange or Google Workspace correlating with the PowerShell activity. Perform a forensic review of the host from which the activity originated for malware or unauthorized software usage. Cross-reference other logs like DNS or web traffic for related anomaly patterns. |
| Containment and Further Analysis | If unauthorized activity is confirmed, temporarily disable the compromised account and enhance monitoring for associated entities. Reset credentials and enforce multi-factor authentication. Collect and preserve forensic evidence from affected systems for a comprehensive investigation. Conduct a thorough security review of email and directory access permissions across the organization. |
