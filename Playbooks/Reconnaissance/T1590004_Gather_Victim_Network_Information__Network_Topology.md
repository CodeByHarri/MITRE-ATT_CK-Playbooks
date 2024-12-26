# Gather_Victim_Network_Information:_Network_Topology - T1590004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1590.004 |
| MITRE Sub-TTP | T1590.004 |
| Name | Gather Victim Network Information: Network Topology |
| Log Sources to Investigate | Investigate network logs such as firewall logs, IDS/IPS logs, router logs, and DNS query logs. Examples include unusual outbound connections revealed in firewall logs, excessive or repeated DNS queries to internal network segments, and unexpected access logs from external IP addresses to internal devices. |
| Key Indicators | Unusual patterns in network traffic such as scanning behavior, access attempts to network devices, discovery of unexpected TCP/UDP ports open on devices, an increase in DNS resolution requests for internal domain assets, or the use of network scanning tools like Nmap. |
| Questions for Analysis | Are there patterns of network traffic that resemble scanning or mapping activities? Is there an unexpected volume of DNS queries to specific internal servers? Are there signs of external IP addresses repeatedly querying internal network devices? Are benign internal service accesses observed from external network sources? |
| Decision for Escalation | Escalate to Tier 2 if: network scanning activities originate from a known external threat vector; connections are made to critical internal devices not typically accessed externally; there are multiple failed access attempts across varied network segments. |
| Additional Analysis Steps for L1 | Verify the IP addresses involved in suspicious activity against a threat intelligence feed for known malicious actors. Cross-check the timestamps of suspicious logs to identify any concurrent anomalous activities. Review the trends over time to determine if behavior is abnormal. |
| T2 Analyst Actions | Conduct deeper network analysis by examining full packet captures, if available, to verify the intent behind the suspicious connections. Correlate activity with endpoint logs to identify potential compromised devices. Validate against available internal and external threat intelligence for alignment with known TTPs. |
| Containment and Further Analysis | Isolate identified suspicious devices from the network to prevent further reconnaissance. Block IP addresses associated with detected scanning activities at the firewall. Conduct a more thorough assessment of network devices, including firmware and software integrity checks, to ascertain any unauthorized changes. Document findings and enhance network monitoring rules to prevent future occurrences. |
