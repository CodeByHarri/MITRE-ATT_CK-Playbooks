# System_Network_Configuration_Discovery:_Internet_Connection_Discovery - T1016001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1016.001 |
| MITRE Sub-TTP | T1016.001 |
| Name | System Network Configuration Discovery: Internet Connection Discovery |
| Log Sources to Investigate | Network traffic logs to identify unusual outbound connections or ICMP traffic. Packet capture (PCAP) logs for detailed network activity inspection. Web proxy logs to detect unexpected external website access patterns. DNS logs for unusual domain lookups related to reachability checks. Host-based logs for command executions like 'ping' or 'tracert'. Examples include Cisco NetFlow, Palo Alto Networks Firewall logs, and Windows Event Logs for command line auditing. |
| Key Indicators | Frequent ICMP requests from a single host, indicating potential use of 'ping' for connectivity checks. Repeated GET requests to known external IP addresses or unusual domains that could signal Internet connection checks. Instances of 'tracert' command executions. Sudden spikes in outbound traffic to unfamiliar destinations, especially following system compromise indicators. |
| Questions for Analysis | Is there a legitimate need for this host to perform ICMP requests or outgoing GET requests? Do the domains or IPs contacted match known, regular business operations or trusted services? Is there any correlation with recent suspicious activities or alerts from this host? Are these requests occurring from a newly compromised host or during off-hours? |
| Decision for Escalation | Escalate if there is abnormal, unexplained network activity to external IPs or domains, especially if tied to recent compromise indicators. Escalate if network traffic attempts bypass known network protection measures. Escalate if usual traffic patterns or volume markedly change without explanation. |
| Additional Analysis Steps for L1 | Verify the source host's normal network activity pattern. Review recent changes on the network segment concerning this host. Check for any correlated incidents involving network connectivity tests. Confirm whether security updates or changes might trigger this activity. |
| T2 Analyst Actions | Conduct deep packet inspection to assess the traffic's intent and destination. Query historical data for similar patterns from the same host. Validate if recent patches or configurations could precipitate this behavior. Analyze endpoint security logs for malicious indicators contemporaneous with this network activity. |
| Containment and Further Analysis | Isolate the host if malicious intent is suspected or confirmed, to prevent lateral movement. Apply deeper forensic techniques to determine any dropped or executed payloads. Monitor for later-stage C2 activities using pre-warming rules based on known TTPs of adversaries. Conduct a post-incident review and communicate findings for threat intelligence updates. |
