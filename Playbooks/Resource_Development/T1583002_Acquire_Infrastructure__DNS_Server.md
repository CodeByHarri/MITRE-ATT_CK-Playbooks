# Acquire_Infrastructure:_DNS_Server - T1583002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1583.002 |
| MITRE Sub-TTP | T1583.002 |
| Name | Acquire Infrastructure: DNS Server |
| Log Sources to Investigate | Investigate DNS server logs, network traffic capturing tools such as NetFlow or packet captures, and firewall logs. Examine logs from SIEM systems for unusual DNS queries, and monitor any changes in DNS configurations. Key examples include Microsoft DNS server logs, Bind DNS server logs, and intermediary DNS servers. |
| Key Indicators | Indicators include the setup of non-standard or unauthorized DNS servers, unusual DNS query patterns such as high-frequency requests to atypical domains, and DNS queries with abnormal indicators like non-standard port usage. Look for established C2 infrastructure such as domains with low reputation scores or those that are recently registered. |
| Questions for Analysis | Are there any unauthorized DNS servers operating in the network? Are there DNS logs indicating communication with known malicious command and control domains? Do the DNS patterns or queried domains deviate from normal organizational traffic? Have these DNS servers appeared in threat intelligence feeds as potentially malicious? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized DNS servers are identified, communications to known C2 domains are detected, or there are signs of DNS misconfigurations that facilitate C2 activities. Patterns of unusual or anomalous traffic warrant further scrutiny by a Tier 2 analyst. |
| Additional Analysis Steps for L1 | Correlate DNS query logs with known threat intelligence indicators of compromise (IOCs). Check for newly registered domains queried by the DNS server. Validate any change requests and check for evidence of DNS tunneling. Flag any anomalies for deeper investigation. |
| T2 Analyst Actions | Perform a deep dive into network and DNS logs to determine the scope of potential DNS infrastructure misuse. Use threat intelligence tools to cross-reference reported domains and IPs with known bad actors. If possible, reconstruct C2 traffic for further inspection and correlation with other incidents. |
| Containment and Further Analysis | Isolate identified threatening DNS servers from the network to block further C2 operations. Investigate affected systems for signs of compromise and verify if malicious software is utilizing DNS for communication. Implement DNS filtering and alerting on suspicious activity. Coordinate with IT to review and restore safe DNS configurations across the network. Conduct a post-incident review to enhance detection mechanisms for future threats. |
