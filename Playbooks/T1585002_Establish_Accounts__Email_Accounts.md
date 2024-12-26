# Establish_Accounts:_Email_Accounts - T1585002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1585.002 |
| MITRE Sub-TTP | T1585.002 |
| Name | Establish Accounts: Email Accounts |
| Log Sources to Investigate | Monitor email service logs for suspicious account registrations, focusing on unusual patterns such as the creation of multiple accounts in a short period. Also, consider logs from SIEM systems, IDS/IPS, and firewall logs for traffic related to known disposable email services. Example log sources include Google Workspace activity logs, Microsoft 365 compliance logs, and email endpoint security solution logs. |
| Key Indicators | Look for creation of multiple email accounts in a short timeframe, use of known disposable email domains, unusual IP addresses associated with account creation processes, accounts with minimal or no traceable activity tied to a legitimate user, and unusual patterns of email sending or receiving behaviors. |
| Questions for Analysis | Are there any known malicious IP addresses involved in the email account creation? Are the email addresses using disposable email services? Is there any related activity that suggests phishing or infrastructure acquisition behaviors? Do these accounts have abnormal patterns or high email sending rates shortly after creation? |
| Decision for Escalation | Escalate to Tier 2 if multiple accounts are created in a short period, especially if involving known malicious IPs or disposable email services, or if there is observed suspicious activity like phishing attempts or infrastructure acquisition attempts associated with the account. |
| Additional Analysis Steps for L1 | Verify against threat intelligence feeds or blacklists for known disposable email domains. Correlate the suspicious account activities with other logs like web or network logs for further contextual understanding. Check user behavior analytics for anomaly detection related to the involved user accounts. |
| T2 Analyst Actions | Conduct deeper behavioral analysis on suspicious accounts, possibly linking email usage patterns to known attack chains. Cross-reference collected data with internal historical incidents and external threat intelligence sources. Assess risk and potential damage scope if accounts were leveraged for attack purposes. Investigate C2 communications or potential phishing infrastructure setup. |
| Containment and Further Analysis | Block or suspend suspicious accounts immediately if they are validated as malicious. Further, conduct an investigation to identify other leverage points like phishing sites or malicious domains associated with these email accounts. Reassess email filtering and spam protection solutions to ensure they are updated against identified threats. Implement enhanced monitoring for the affected domains and IPs. |
