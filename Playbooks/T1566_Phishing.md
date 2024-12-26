# Phishing - T1566

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Initial Access |
| MITRE TTP | T1566 |
| MITRE Sub-TTP | T1566 |
| Name | Phishing |
| Log Sources to Investigate | Email logs for evidence of delivery of phishing emails (e.g., emails with attachments or links from unknown/suspicious sources), web proxy logs for URLs visited post-email interaction, DNS logs indicating resolution of domains linked in potential phishing mails, endpoint detection and response (EDR) logs for any execution of suspicious processes following email receipt, and authentication logs for any anomalies in user login patterns or locations after potential phishing messages are interacted with. |
| Key Indicators | Emails with spoofed sender addresses, URLs known to be associated with phishing campaigns, unusual attachment types (e.g., .exe, .scr, .vbs), sudden increase in emails marked as junk or phishing, abnormally timed email logins or access attempts, and user-reported incidents of suspicious communications. |
| Questions for Analysis | Did the email originate from a known malicious domain? Does the URL or attachment match indicators from known phishing databases or threat intelligence feeds? Is there evidence of user interaction with the phishing email or link (e.g., click-throughs, downloads, abnormal executions)? Are there multiple similar reports from other users? |
| Decision for Escalation | Escalate to Tier 2 when there is verified interaction with a potentially malicious attachment or URL, identification of phishing attempts involving executive/sensitive accounts, or when there is corroboration between multiple log sources indicating a probable compromise. |
| Additional Analysis Steps for L1 | Correlate email details with threat intelligence feeds for known phishing campaigns. Examine web proxy and DNS logs for domain resolution patterns. Check for spikes in email failures or unusual attachment interactions. Cross-reference incoming email headers for possible spoofing anomalies. |
| T2 Analyst Actions | Conduct deeper packet inspection on suspicious traffic or payloads. Analyze endpoint telemetry for post-execution signs of compromise. Utilize sandbox environments to test suspect email attachments/links. Verify any lateral movements or additional unauthorized access detected post-phishing attempt. Evaluate network-wide for potential spread or additional vectors. |
| Containment and Further Analysis | Quarantine affected machines and disable user accounts involved in potential breaches. Ensure malicious domains and email addresses are blocked across the network. Implement multi-factor authentication if not already in place. Collaborate with IT teams to monitor further communications/residuals from the phishing attack. Prepare incident reports and refine detection algorithms based on insights gathered. |
