# Gather_Victim_Org_Information:_Business_Relationships - T1591002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1591.002 |
| MITRE Sub-TTP | T1591.002 |
| Name | Gather Victim Org Information: Business Relationships |
| Log Sources to Investigate | Monitor logs from web servers, social media platforms, and email services. Watch for unusual patterns in access logs, especially from IP addresses or regions that are not typical for your business. Review traffic involving third-party domains, especially those related to contractors or service providers. Utilize data from security information and event management (SIEM) systems to correlate multiple log sources and generate alerts for suspicious activities linking to business partner interactions. |
| Key Indicators | Unusual or unauthorized access to pages on victim-owned websites, increased data scraping activity, or repeated queries involving business relationships. New user profiles or email accounts being created that impersonate known business associates. Sudden spikes in communication or data movement with third-party contractors not corresponding to known projects. |
| Questions for Analysis | Does the activity come from legitimate or known IPs? Is there evidence of reconnaissance or probing? Are there any impersonated accounts or unusual communication patterns? Does the activity correspond to any recent business operation, such as a new contract with a third party? |
| Decision for Escalation | Escalate if there are signs of data exfiltration, confirmed use of compromised accounts, or if there's evidence of access-related anomalies that could indicate a supply chain compromise. Escalate to Tier 2 if suspicious activities involve sensitive or critical domains. |
| Additional Analysis Steps for L1 | Verify IP addresses against known lists of benign and malicious sources. Check for patterns in login attempts that may indicate brute force attempts or credential stuffing. Ensure the activities correlate with legitimate business transactions or communications. |
| T2 Analyst Actions | Conduct deep-dive analysis into network traffic for signs of Advanced Persistent Threats (APTs). Analyze any malware signatures if detected and investigate further by cross-referencing with known threat intelligence feeds. Validate any anomalies found in system or application logs against historical data. |
| Containment and Further Analysis | If malicious activity is confirmed, disable any affected user accounts and block IP addresses if necessary. Perform a comprehensive risk assessment of affected third-party relationships and initiate incident response protocols. Work with business continuity teams to mitigate any impacts on supply chain operations. |
