# Use_Alternate_Authentication_Material:_Pass_the_Ticket - T1550003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Lateral Movement |
| MITRE TTP | T1550.003 |
| MITRE Sub-TTP | T1550.003 |
| Name | Use Alternate Authentication Material: Pass the Ticket |
| Log Sources to Investigate | Focus on Windows Security Event Logs, specifically events related to Kerberos authentication such as Event ID 4768 (TGT Request), 4769 (Service Ticket Request), 4770 (TGT Renewal), and 4771 (Pre-authentication Failed). Additionally, review logs from Domain Controllers for unusual ticket requests, especially those from unexpected or non-existent accounts. Monitoring tools that provide Kerberos authentication details, such as SIEM solutions with Kerberos modules, can be crucial.<br><br>Review logs from Credential Dumping detection, as initial credential capture often precedes Pass the Ticket attacks. Network monitoring logs should also be examined for anomalous lateral movement activity. |
| Key Indicators | Look for abnormal patterns in Kerberos ticket requests, including:<br>- Large numbers of TGTs being issued or renewed in a short period.<br>- TGTs or service tickets created for legitimate accounts from unusual hosts.<br>- Failed authentication events followed by successful ones from the same IP address without password resets.<br>- Use of service accounts or admin accounts on unusual systems or times. |
| Questions for Analysis | 1. Are there any repeated TGT requests from a single source?<br>2. Is there evidence of Kerberos tickets being used from unexpected machines or IP addresses?<br>3. Are there multiple authentication attempts with older or non-existent accounts?<br>4. Can the account activity be correlated with expected user behavior or business operations? |
| Decision for Escalation | Escalate to Tier 2 if:<br>- There are significant anomalies in Kerberos ticket requests concerning volume, timing, and source.<br>- Evidence correlates with known account misuse, when compared to historical or baseline behaviors.<br>- Initial analysis suggests ticket creation from hashes or observations indicate potential Golden or Silver Ticket activities. |
| Additional Analysis Steps for L1 | Validate the timestamp and source of Kerberos ticket activities against user logs and known operations.<br>Review any associated events such as login/logoff times, suspicious processes, or network connections originating from the affected hosts.<br>Check for any corresponding alerts related to credential dumping or suspicious use of administrative credentials. |
| T2 Analyst Actions | Perform a deeper forensic analysis of affected systems, including memory dumps to identify ticket artifacts.<br>Investigate the originating IP addresses and path of lateral movement attempts using Kerberos tickets.<br>Correlate with threat intelligence sources to determine if similar TTPs have been reported in relation to known threat actors.<br>Assess and verify if stolen NTLM hashes or other credential material have been used in ticket creation. |
| Containment and Further Analysis | Reinitialize affected accounts by changing passwords and ensuring full resets of TGTs and service tickets to invalidate potential unauthorized accesses.<br>Enhance monitoring around Kerberos authentication activities to prevent recurrence and identify any missed spread.<br>Consider implementing MFA for privileged account actions and ensure patches and security controls align with best practices against credential theft and misuse.<br>Conduct a post-incident analysis to amend gaps in detection capabilities and streamline response. |