# Email_Collection:_Email_Forwarding_Rule - T1114003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1114.003 |
| MITRE Sub-TTP | T1114.003 |
| Name | Email Collection: Email Forwarding Rule |
| Log Sources to Investigate | Investigate email server logs, specifically focusing on Microsoft Exchange transport logs and rule change logs. Check for any logs relating to the creation or modification of email forwarding rules. Audit logs from Microsoft 365 (M365) could provide insights into user or administrator actions regarding email rule settings. Outlook Web Access (OWA) logging may also capture changes. Email gateway logs could reveal unexpected forwarding activities. |
| Key Indicators | Creation or modification of email forwarding rules, particularly those forwarding to external domains. Large volumes of emails being forwarded outside of typical organizational patterns. Hidden rules created using MAPI or other APIs that do not appear in the Exchange Admin Center. Transport rules set up organization-wide by non-administrative users. |
| Questions for Analysis | Who created or modified the email rule? Was the rule creation/modification intentional and by an authorized user? Does the target domain or recipient of forwarded emails appear suspicious or unauthorized? Is there any pattern of rule creation/modification that coincides with known compromise indicators or past incidents? |
| Decision for Escalation | Escalate if: the email rule forwards emails to an external address not recognized by the organization, the creation or modification was done by an unauthorized or unknown account, or if hidden rules are detected that cannot be easily accounted for by legitimate changes. |
| Additional Analysis Steps for L1 | Identify the user account(s) associated with the rule creation/modification. Verify any unusual patterns of email forwarding, such as high volume or anomalous sender addresses. Check user activity logs for unusual login times or IP addresses. Communicate with the user or respective department to confirm the legitimacy of the rule. |
| T2 Analyst Actions | Conduct a deeper investigation into the user account's activities surrounding the time of rule creation/modification. Correlate with other potentially suspicious activities, such as login anomalies or access to sensitive data. Validate if the email forwarding addresses are linked to known threat actors or past incidents. Determine if similar rules have been recently created across other accounts. |
| Containment and Further Analysis | If malicious activity is confirmed, disable the suspicious rule immediately. Reset passwords for affected accounts and enforce MFA if not already active. Notify security and IT teams for further infrastructure review. Review organization-wide email security settings and consider tightening control of who can create or modify email forwarding rules. Educate users on recognizing unauthorized email rule changes. |
