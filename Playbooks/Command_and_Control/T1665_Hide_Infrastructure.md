# Hide_Infrastructure - T1665

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1665 |
| MITRE Sub-TTP | T1665 |
| Name | Hide Infrastructure |
| Log Sources to Investigate | Network traffic logs, proxy server logs, VPN usage reports, DNS query logs, web server logs, firewall logs, secure web gateway logs. Investigate any anomalies in IP addresses (e.g., sudden changes in geolocation, unusual IP ranges), URLs (such as those using popular URL shortening services), and user-agent strings indicative of defensive tools being blocked or redirected. |
| Key Indicators | Anomalous IP address usage that mimics victim IP ranges or frequently changes geolocation, use of proxies or VPNs that are not part of normal operating procedures. DNS queries for known malicious domains or those using trusted providers with suspicious redirected traffic. HTTP headers showing blocked or redirected defensive tool user-agent strings. |
| Questions for Analysis | Is the IP address traffic consistent with expected geolocation? Are known proxies or VPNs being used contrary to policy? Are there proxy server logs showing user-agent blocking/redirection? Are there DNS requests for domains previously associated with obfuscation techniques? Does web traffic exhibit patterns of redirection through trusted services? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of IP address manipulation mimicking victim ranges, if trusted infrastructure is redirecting traffic to suspicious destinations, or if there are signs of user-agent filtering specifically targeting defensive tools. |
| Additional Analysis Steps for L1 | Perform an initial assessment of network traffic logs for patterns of redirection through unauthorized proxies or VPNs. Check the geolocation consistency of recent IP addresses. Review DNS logs for suspicious domain queries. Examine user-agent strings for indicators of filtering or blocking attempts. |
| T2 Analyst Actions | Conduct a deeper analysis of the C2 traffic patterns to determine the persistence and evasion methods employed. Investigate the scope and identify all malicious C2 infrastructure components involved. Validate if the infrastructure has compromised or leveraged trusted services. Correlate findings with threat intelligence to assess TTPs. |
| Containment and Further Analysis | Immediately quarantine affected network segments to prevent further malicious traffic. Block identified malicious IP addresses, domains, and proxies at the firewall and secure web gateway level. Perform a full forensic analysis of systems communications with C2 infrastructure. Initiate incident response protocols including the removal of any discovered backdoors or persistence mechanisms. |
