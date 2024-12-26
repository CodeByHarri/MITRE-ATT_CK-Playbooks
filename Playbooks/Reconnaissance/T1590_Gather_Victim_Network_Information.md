# Gather_Victim_Network_Information - T1590

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1590 |
| MITRE Sub-TTP | T1590 |
| Name | Gather Victim Network Information |
| Log Sources to Investigate | Network traffic logs, DNS query logs, firewall logs, web server access logs. Examples include: reviewing DNS queries for WHOIS lookups, unusual DNS requests, or repeated access to internal IP ranges from external sources; examining firewall logs for unusual access attempts or scans targeting network ranges; and checking web server logs for non-standard access patterns indicating network enumeration. |
| Key Indicators | Unusual volume of WHOIS lookups, unexpected DNS query patterns, repeated access to internal network ranges from external IPs, presence of tools or scripts typically used for network scanning such as nmap, and increased DNS activity involving suspicious or unexpected domains. |
| Questions for Analysis | Are there any external IPs or unknown domains showing frequent network probing or scanning activity? Is there unusual or high-frequency DNS query activity toward your organization's domain? Are there attempts to access non-public URLs or internal network resources? |
| Decision for Escalation | Escalate to Tier 2 if there is consistent pattern or volume of network enumeration detected from a single external entity, signs of targeted reconnaissance activities correlating with known tactics, or if sensitive internal network information appears to have been accessed or attempted to be accessed. |
| Additional Analysis Steps for L1 | Examine network traffic logs for repeated requests or anomalies. Verify if any suspicious domain or IP has been associated with previous reconnaissance activities. Check for any accompanying phishing attempts or related alerts in recent timeframes. |
| T2 Analyst Actions | Conduct deeper analysis on any identified IP addresses or domains, leveraging threat intelligence sources. Correlate activity with current threat actor TTPs to determine if it's part of a larger campaign. Engage with internal teams to verify any legitimate inquiries or authorized activities related to identified network enumeration. |
| Containment and Further Analysis | Block or isolate identified malicious IPs or domains at the firewall or DNS level. Assess the impact by determining if any sensitive data was exposed. Enhance monitoring and review firewall/IDS/IPS rules to detect and prevent similar future reconnaissance activities. Conduct a session with network admins to review and adjust network segmentation and access control policies. |
