# Network_Denial_of_Service - T1498

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1498 |
| MITRE Sub-TTP | T1498 |
| Name | Network Denial of Service |
| Log Sources to Investigate | Network flow data (e.g., NetFlow, sFlow), IDS/IPS logs, firewall logs, web server access logs, DNS logs. Examples include logs showing abnormal outgoing or incoming traffic volumes, repeated connection attempts from a range of IPs, or traffic from known malicious IPs. |
| Key Indicators | Unusually high network traffic volumes, increased connection attempts to a single IP or service, traffic from atypical or unexpected geographic locations, presence of known malicious IPs or domains. Unusual traffic patterns such as a surge in requests for rarely accessed services. |
| Questions for Analysis | Is there an unusual increase in network traffic? Are there repeated connection attempts from a specific range of IPs? Is the traffic sourced from known malicious IP addresses? Is there any indication of reflection or amplification (e.g., small request, large response)? Is a specific service being targeted? |
| Decision for Escalation | If the traffic volume is impacting service availability or appears to originate from a distributed set of systems indicating a DDoS, escalate. If the tactics involve IP spoofing that bypass normal filter mechanisms and the attack is sustained and targeted. |
| Additional Analysis Steps for L1 | Verify if the observed traffic matches normal traffic patterns for the network. Check if similar traffic patterns coincide with common business operations or events. Consult threat intelligence for any current DDoS trends or known campaigns. |
| T2 Analyst Actions | Conduct deeper analysis with packet captures to identify the type of DDoS attack (e.g., volumetric, protocol-based or application-based). Correlate traffic patterns with ongoing global threats. Validate if the attack is part of a larger campaign or specific threat actor tactics. |
| Containment and Further Analysis | Engage with network engineering to implement traffic filtering and rate limiting on affected interfaces or services. Use black holing/null routing for traffic from malicious IPs. Consider utilizing a DDoS protection service. Analyze captured packets for further insights into attack vectors or exploit kits used. |
