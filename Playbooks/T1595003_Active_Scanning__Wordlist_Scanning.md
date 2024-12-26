# Active_Scanning:_Wordlist_Scanning - T1595003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1595.003 |
| MITRE Sub-TTP | T1595.003 |
| Name | Active Scanning: Wordlist Scanning |
| Log Sources to Investigate | Web server logs (e.g., Apache, Nginx logs), Cloud service provider logs (AWS CloudTrail, Azure Activity Log), Network traffic logs, Firewall logs, Intrusion detection/prevention system logs, Proxy server logs, Cloud storage access logs (e.g., AWS S3 access logs). |
| Key Indicators | Spike in 404 (Not Found) HTTP responses indicative of directory or file enumeration, Unusual patterns of access to multiple web directories or pages in quick succession, Sequential or incremental probing of URLs with minimal time gaps, Access to non-public endpoints or old versions of web pages, Multiple failed access attempts logged in cloud storage services, Usage of known web content discovery tools (e.g., Dirb, GoBuster) in user-agent strings or request headers. |
| Questions for Analysis | What IP addresses are predominantly associated with the observed scanning activity? Are there any patterns in the URLs or file extensions being probed? Has there been a recent surge in 404 errors or unusual access patterns to sensitive or non-existent resources? Is the detected activity originating from known or suspicious geographical locations? |
| Decision for Escalation | Escalate to Tier 2 if scanning activity is persistent and specifically targets sensitive endpoints, involves a significant number of IP addresses, or if there is evidence of follow-up attacks such as attempted exploitation of vulnerable pages. |
| Additional Analysis Steps for L1 | Verify whether the scanning IPs are listed in threat intelligence feeds or blacklists. Check for any previously reported suspicious activity from the same IP ranges. Correlate indicators with recent changes or deployments to the target infrastructure. |
| T2 Analyst Actions | Conduct deeper analysis on the IP addresses and geographic origin of the scanning activity. Determine if the detected scans correlate with known attack patterns or APT activity. Investigate historical logs for similar scanning patterns to establish if this is part of a larger campaign. |
| Containment and Further Analysis | Block identified malicious IPs or IP ranges using firewall rules. Implement rate limiting on web servers to mitigate the impact of enumeration activities. If specific URLs were targeted, review and potentially enhance security around those endpoints (e.g., apply authentication/authorization controls). Monitor for any further suspicious activities and follow up with a security posture evaluation to ensure controls are adequate. |
