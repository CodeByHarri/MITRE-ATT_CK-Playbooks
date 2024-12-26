# Defacement:_External_Defacement - T1491002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1491.002 |
| MITRE Sub-TTP | T1491.002 |
| Name | Defacement: External Defacement |
| Log Sources to Investigate | Web server logs, CMS change logs, DNS records, CDN access logs, WAF alerts, security information and event management (SIEM) alerts. Examples include Apache access logs, WordPress modification logs, CDN activity from providers like Cloudflare, and alerts from a WAF like AWS WAF. |
| Key Indicators | Unexpected changes to webpages, unauthorized user access or account changes, large deviations in website traffic, abnormal DNS queries, WAF triggering alerts such as SQL injection or cross-site scripting attempts, and differences in webpage hash values. |
| Questions for Analysis | Was there an unauthorized change recorded in CMS or web server logs? Are there unexpected accounts or privileges recently created or altered? Have there been recent spikes in traffic or anomalies in DNS queries? Are there any alerts from website security tools (e.g., WAF)? |
| Decision for Escalation | Escalate if unauthorized changes to webpage content are confirmed, if there are undetermined user accesses with elevated privileges, or if anomalies are coupled with alerts indicating malicious activity (e.g., SQL injection attempts). |
| Additional Analysis Steps for L1 | Review web server and CMS logs for unauthorized access or content modifications. Check user accounts for recent changes in privileges. Analyze recent WAF alerts. Compare webpage hashes for integrity check. |
| T2 Analyst Actions | Perform deeper analysis on confirmed unauthorized access points. Correlate findings across different log sources (e.g., cross-reference CMS logs, and DNS records with SIEM alerts). Check for patterns indicative of broader attack campaigns. Validate defacement source and assess potential persistence mechanisms. |
| Containment and Further Analysis | Revert any unauthorized webpage modifications and restore from backups. Change credentials and lock out unauthorized accounts. Apply security patches and harden web server configurations. Conduct a thorough security posture review of externally facing systems and initiate a broader threat hunt to ensure no further compromise has occurred. |
