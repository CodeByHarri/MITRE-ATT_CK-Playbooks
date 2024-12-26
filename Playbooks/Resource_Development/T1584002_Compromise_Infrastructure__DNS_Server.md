# Compromise_Infrastructure:_DNS_Server - T1584002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1584.002 |
| MITRE Sub-TTP | T1584.002 |
| Name | Compromise Infrastructure: DNS Server |
| Log Sources to Investigate | Focus on DNS logs, firewall logs, and web server access logs. Monitor DNS changes, particularly unauthorized modifications to DNS records. Review network traffic for unusual DNS requests or patterns. Examples include logs from DNS management tools, anomaly detection systems like IDS/IPS logs, and DNS query logs from SIEM solutions. |
| Key Indicators | Unexpected changes in DNS records pointing to suspicious or unfamiliar IPs. Increased DNS queries from unusual external sources. Creation of new subdomains that divert normal traffic routes. In specific DNS logs, look for entries that represent changes not initiated by legitimate administrators. |
| Questions for Analysis | Are there unauthorized alterations in DNS records? Is there an unusual spike in DNS queries or traffic to specific domains? Are there new DNS records or subdomains pointing to external, unknown IPs? Have any domains been flagged by security feeds as potentially compromised or malicious? |
| Decision for Escalation | Escalate if any unauthorized DNS modifications are detected, especially those redirecting traffic or creating new subdomains. Also, escalate if security feeds confirm IPs or domains involved in DNS changes as part of known threat actor activities. |
| Additional Analysis Steps for L1 | Verify DNS record changes with authorized personnel to confirm legitimacy. Check if domains or subdomains flagged appear on threat intelligence feeds. Use network flow analysis tools to ascertain if there's anomalous DNS traffic routing to suspicious destinations. |
| T2 Analyst Actions | Perform deeper investigation on the impacted DNS records and source IPs. Review historical DNS changes for signs of a pattern. Validate suspicious IPs/domains against broader threat intelligence databases. Engage with infrastructure team to ensure no further unauthorized access is possible. |
| Containment and Further Analysis | Revert any unauthorized DNS changes immediately. Implement network segmentation or additional firewalls to block suspicious IPs. Conduct a thorough review of the DNS server logs over an extended period for signs of prolonged activity or earlier breaches. Engage with ISPs if domain shadowing is suspected to contain adversary-controlled pathways. Consider deploying more robust DNS security solutions, such as DNSSEC, if not already in place. |
