# Search_Open_Technical_Databases:_WHOIS - T1596002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1596.002 |
| MITRE Sub-TTP | T1596.002 |
| Name | Search Open Technical Databases: WHOIS |
| Log Sources to Investigate | Investigate DNS logs, HTTP/HTTPS logs (looking for WHOIS query services or API calls), network traffic logs, firewall logs, and proxy logs. Examples include DNS query logs from a DNS server, web server logs from HTTP requests checking known WHOIS databases, or firewall logs indicating unusual outbound connections. |
| Key Indicators | Frequent and repetitive queries to WHOIS servers, especially those directly querying victim-associated domains. Presence of unusual or unscheduled access to known WHOIS services or public databases from internal IPs. Network traffic anomalies such as spikes in WHOIS activity. |
| Questions for Analysis | Are WHOIS queries coming from expected administrative or security personnel? Is there an unexplained spike in WHOIS query activity? Do the WHOIS queries correlate with key business operations or external communications? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized source IP addresses are performing WHOIS queries, if there is a pattern of WHOIS queries that might suggest active reconnaissance, or if WHOIS data corresponds with known phishing or reconnaissance IPs/domains. |
| Additional Analysis Steps for L1 | 1. Verify the source of the WHOIS queries and check the legitimacy of these sources.<br>2. Evaluate the frequency and timing of the WHOIS requests to discern any patterns.<br>3. Identify any contextual data linking WHOIS queries with known threat actor TTPs or recent threat intel reports. |
| T2 Analyst Actions | 1. Perform deeper network analysis to identify potential lateral movements following WHOIS queries.<br>2. Cross-reference WHOIS data with other reconnaissance TTPs for correlation and source determination.<br>3. Validate the legitimacy of IP addresses/domains in WHOIS queries by referring to threat intelligence feeds. |
| Containment and Further Analysis | If the queries are confirmed malicious, block unauthorized entities from accessing WHOIS services either via firewall rules or network segmentation. Conduct further network-wide forensics to identify other reconnaissance activities. Update internal security documentation and training to incorporate lessons learned from this incident. |
