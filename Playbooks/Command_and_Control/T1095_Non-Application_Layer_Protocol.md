# Non-Application_Layer_Protocol - T1095

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1095 |
| MITRE Sub-TTP | T1095 |
| Name | Non-Application Layer Protocol |
| Log Sources to Investigate | Network traffic logs, especially those capturing ICMP data (e.g., from tools like Wireshark or Zeek). Firewalls and intrusion detection/prevention systems (IDS/IPS) logs for unexpected ICMP traffic patterns. System logs where unusual socket connections might be logged. Utilization of SIEM tools to identify anomalies in ICMP traffic. Examples include Splunk with ICMP-related queries or examining specific devices for unsanctioned ICMP destinations. |
| Key Indicators | Unusual spikes in ICMP traffic volume. ICMP traffic to/from known critical internal servers or external IPs that don't commonly interact with the host. Repeated instances of ICMP communication to singular or multiple foreign IP addresses that diverge from normal patterns. Lengthy ICMP packet messages that could indicate data exfiltration attempt. |
| Questions for Analysis | Is the source or destination of the ICMP traffic expected to interact with this network segment? Are there any anomalies in the frequency or payload size of the ICMP packets? Do the packet payloads contain any encoded or encrypted data that deviates from standard ICMP usage? Are there historical instances of this behavior, and have they been previously investigated? |
| Decision for Escalation | Escalate to Tier 2 if identified ICMP traffic involves sensitive data-bearing systems, if initial analysis suggests data exfiltration attempts, if payloads are non-trivial or encrypted, or if the source/destination IPs are associated with known threat actors or past incidents. |
| Additional Analysis Steps for L1 | Verify if there is a legitimate need for the identified ICMP traffic by consulting with the network team. Perform a basic pattern analysis on ICMP packet data to identify potential embedded or non-standard data. Cross-reference the source and destination IP against threat intelligence feeds to spot any known bad actors. |
| T2 Analyst Actions | Conduct deeper packet inspection using tools like Bro/Zeek or Wireshark to uncover potentially hidden communications. Correlate the ICMP traffic with other indicators of compromise, such as unusual login attempts or file changes. Engage with system owners to verify if the traffic aligns with operational baselines. Implement more specific monitoring rules to capture detailed ICMP traffic activity. |
| Containment and Further Analysis | If deemed malicious, block suspicious IP addresses at the firewall to prevent further communication. Isolate infected systems from the network to mitigate ongoing C2 communication. Perform a full forensic analysis on affected hosts to discern the broader scope of the compromise. Review and strengthen network monitoring policies to detect similar activities moving forward. |
