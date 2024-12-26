# Search_Open_Websites_Domains:_Search_Engines - T1593002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1593.002 |
| MITRE Sub-TTP | T1593.002 |
| Name | Search Open Websites/Domains: Search Engines |
| Log Sources to Investigate | Investigate DNS logs to check for unusual queries that might resemble targeted searches; HTTP proxy logs to identify outbound traffic to search engines with suspicious query patterns; Firewall logs for outbound traffic to known search engine IP addresses, to assess the volume and frequency of requests. |
| Key Indicators | High volume of search queries to search engines within a short timeframe; search queries containing filetype operators or keywords related to sensitive information (e.g., passwords, confidential); unusual search patterns performed by a non-approved user or service account. |
| Questions for Analysis | Is there a user account making frequent requests to search engines? Are there query patterns that match known information-gathering or data leakage techniques? Is the observed behavior consistent with any recent phishing or credential compromise alerts? |
| Decision for Escalation | Escalate if search patterns show leakage of sensitive information or if queries suggest active information gathering against internal resources. Also, escalate if queries are followed by attempts to access unusual internal or external resources. |
| Additional Analysis Steps for L1 | Review historical logs for patterns or trends in search behaviors by the implicated user; correlate with authentication logs to check for anomalous login attempts surrounding the timeframe of the searches. |
| T2 Analyst Actions | Perform a detailed review of endpoint data to ensure no malware is causing automated queries; verify network traffic for data exfiltration attempts; perform threat intelligence checks for any matched queries against known adversarial TTPs. |
| Containment and Further Analysis | If malicious activity is confirmed, isolate the involved systems from the network to prevent further data exfiltration; reset credentials for affected accounts and perform full forensic analysis to determine the extent of data accessed or exfiltrated. Consider implementing further employee training or security awareness measures. |
