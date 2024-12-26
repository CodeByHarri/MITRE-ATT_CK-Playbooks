# Phishing_for_Information - T1598

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1598 |
| MITRE Sub-TTP | T1598 |
| Name | Phishing for Information |
| Log Sources to Investigate | Examine email server logs for unusual patterns of incoming or outgoing emails that may indicate phishing attempts targeting sensitive information. Analyze firewall logs to identify any suspicious outbound connections that align with phishing indicators. Review DLP (Data Loss Prevention) logs to detect potential data exfiltration attempts tied to phishing. Inspect SIEM alerts for abnormal communication patterns or authentication anomalies. Consider monitoring social media activity alerts if phishing is suspected through these channels. |
| Key Indicators | Look for mass emails with unusual sender addresses, unexpected email attachments, or links pointing to suspicious domains. Identify emails with spoofed sender addresses, often mimicking legitimate ones. Phishing attempts may use urgent or alarming language to prompt quick action from the recipient. Note the presence of unexpected or altered email header information, which can be indicative of spoofing. Be aware of repeated interactions from unknown sources seeking sensitive information via email or phone calls. |
| Questions for Analysis | Does the email contain signs of being a phishing attempt, such as misspellings or odd language inconsistencies? Are there any suspicious links or attachments within the emails? Is the sender address verified, or does it appear spoofed or unusual? Have there been similar phishing attempts reported by other users or systems recently? Has the user reported unexpected account access or credential requests? |
| Decision for Escalation | Escalate to Tier 2 if the phishing attempt involves a high-profile target or could lead to significant data exposure. Elevate if analysis indicates that the alleged phishing emails bypassed current security measures. Escalation is warranted if multiple users report similar phishing attempts suggesting a widespread campaign. Attach a priority tag if there are indications of successful data breach attempts. |
| Additional Analysis Steps for L1 | Confirm sender legitimacy through email header analysis. Utilize sandboxing to safely evaluate suspicious attachments or URLs without exposing user systems. Cross-reference known phishing indicators with the content of suspicious emails. Check username and password change logs for targeted users or unusual patterns. Validate whether similar emails have been reported as phishing by other users. |
| T2 Analyst Actions | Perform deeper packet inspection focusing on email traffic suspected of phishing. Analyze metadata and content in intercepted emails to identify any embedded code or encoded instructions. Investigate historical data for patterns linking various reported phishing attempts. Reverse engineer any suspicious URLs or attachments found within emails. Collaborate with threat intelligence teams to assess if this phish links to known threat actors or campaigns. |
| Containment and Further Analysis | Quarantine affected emails to prevent user access and potential data leakage. Update email filters and security policies to block similar phishing attempts. Reset credentials for compromised accounts and inform affected users immediately. Analyze network traffic for any data exfiltration and take measures to block transfers. Plan for user education sessions emphasizing phishing awareness and best practices. |