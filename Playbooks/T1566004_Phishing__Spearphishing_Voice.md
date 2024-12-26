# Phishing:_Spearphishing_Voice - T1566004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Initial Access |
| MITRE TTP | T1566.004 |
| MITRE Sub-TTP | T1566.004 |
| Name | Phishing: Spearphishing Voice |
| Log Sources to Investigate | Telephone or voice communication logs, call recordings if available, VoIP logs, employee reports of suspicious calls, logs from Interactive Voice Response (IVR) systems, logs from multi-factor authentication servers indicating unexpected authentication requests, web proxy logs showing access to newly potential malicious URLs pointed out during spearphishing vishing attempts. |
| Key Indicators | Unusual and suspicious outbound call patterns, reports of calls asking for security credentials, instances of urgency or alarm in voice communications, callbacks to numbers mentioned in vishing attacks, employees reporting confusion over unexpected requests for access or authentication, unexplained MFA prompt approvals, increased web traffic to URLs linked to vishing scams. |
| Questions for Analysis | Did the employee receive a call asking for sensitive information? Was the caller pretending to be from a trusted source such as internal IT or financial institutions? Is there any abnormal activity or logins following the reported call? Have there been multiple reports of similar calls from other employees? Are there unexpected MFA prompts or approvals around the time of the call? |
| Decision for Escalation | Escalate to Tier 2 if there is verified engagement with the malicious call, such as the victim providing sensitive information or accessing a URL during the call. Also, escalate if there are multiple reports of similar suspicious calls or if there is corroborating evidence of MFA bypass attempts or anomalous account activity linked to the incident. |
| Additional Analysis Steps for L1 | Collect detailed incident reports from affected users. Review call logs and identify commonalities, such as repeat phone numbers or similar caller IDs. Check for correlated MFA alerts or login anomalies in conjunction with reported time of call. Verify if accessed URLs are malicious. |
| T2 Analyst Actions | Perform deeper investigation into call logs and potential spoofed numbers for patterns. Scrutinize affected users' recent activity for any data exfiltration or policy violations. Collaborate with IT to determine if there were unauthorized changes or system accesses. Analyzing IP traffic associated with accessed URLs for potential threats. |
| Containment and Further Analysis | Instruct affected users to change compromised credentials. Implement phone number blocking for known malicious numbers. Strengthen user education on identifying vishing attempts. Monitor for unauthorized access attempts or abnormal behavior post-incident. Analyze any downloaded content for malware, and deploy additional security measures such as enhancing MFA robustness. |
