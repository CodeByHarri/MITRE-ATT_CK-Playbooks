# Phishing_for_Information:_Spearphishing_Attachment - T1598002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1598.002 |
| MITRE Sub-TTP | T1598.002 |
| Name | Phishing for Information: Spearphishing Attachment |
| Log Sources to Investigate | Email gateway logs to identify incoming emails with attachments from unknown or suspicious senders. Endpoint security logs to monitor file downloads and execution attempts. Network traffic logs to detect any anomalous outbound connections when attachments are opened. User activity and authentication logs to verify if there were unauthorized access attempts following the email receipt. |
| Key Indicators | Emails containing attachments from unrecognized senders with a sense of urgency or request for sensitive information. Unusual file types or names in email attachments. Multiple, similar emails sent to various recipients within the organization. Outbound network connections initiated shortly after opening the attachment. |
| Questions for Analysis | Is the sender email address recognized or part of any known domains? Does the email convey a sense of urgency or request unusual information? Are there any known malicious indicators (e.g., file hash) associated with the attachment? Have similar incidents been reported by other recipients? |
| Decision for Escalation | Escalate to Tier 2 if the email appears to be a targeted spearphishing attempt with a malicious attachment, if any malicious activity is detected from the recipient's account, or if there is a match with known threat intelligence indicators. |
| Additional Analysis Steps for L1 | Verify the authenticity of the sender by cross-checking the email domain and headers. Analyze the attachment in a sandbox environment for malicious behavior. Check if the user reported any suspicious activity or communication. |
| T2 Analyst Actions | Perform a deeper analysis of the attachment using advanced tools like static and dynamic malware analysis. Cross-reference any identified indicators with threat intelligence feeds. Review the user's account activity and any affected systems for signs of compromise. |
| Containment and Further Analysis | Isolate the affected endpoint and block any identified malicious domains on the network. Reset credentials for accounts at risk. Conduct a full forensic analysis of the incident to determine the scope of the attack, and provide recommendations for improving cybersecurity awareness to prevent future spearphishing attempts. |
