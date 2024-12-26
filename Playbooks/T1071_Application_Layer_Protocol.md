# Application_Layer_Protocol - T1071

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1071 |
| MITRE Sub-TTP | T1071 |
| Name | Application Layer Protocol |
| Log Sources to Investigate | Analyze network traffic logs with a focus on application layer protocols. Key sources include web proxy logs for HTTP/HTTPS traffic, email server logs for SMTP/IMAP/POP3, DNS query logs for unusual query patterns, and file transfer logs for protocols like FTP. Security Information and Event Management (SIEM) systems can aggregate these logs. Look for high volumes of outbound connections or unexpected data transfers to external entities. |
| Key Indicators | Unusual spikes in traffic patterns using standard protocols such as HTTP/HTTPS, especially large data uploads or command-like behavior in request parameters. DNS requests to uncommon domains or with unusual frequency. Unusual SMB, SSH, or RDP traffic patterns, such as access attempts from non-standard sources. Look for command execution patterns embedded in legitimate-looking traffic. |
| Questions for Analysis | Are there any recent unusual spikes in traffic using common protocols? Does the destination IP or domain match known malicious indicators? Are there any anomalies in DNS request patterns? Is there any known prior history of communication between the source and destination? |
| Decision for Escalation | Escalate to Tier 2 if: 1) There are confirmed connections to known malicious IPs/domains.<br>2) There is anomalous high data transfer to external locations.<br>3) Any discovered traffic shows signs of command-type structures, especially when embedded in covert forms. |
| Additional Analysis Steps for L1 | 1) Validate if the protocol usage matches legitimate business operations.<br>2) Correlate any detected anomalies with existing threat intelligence for known malicious indicators.<br>3) Look for any repeated patterns or cyclical traffic anomalies that could suggest automated data exfiltration. |
| T2 Analyst Actions | Conduct deeper packet analysis to identify specific commands or data types being transferred. Coordinate with threat intelligence platforms for up-to-date malicious IP/domain correlations. Investigate potential compromise of credentials associated with the unusual traffic. Investigate any lateral movement attempts within the network using internal protocol traffic. |
| Containment and Further Analysis | Isolate affected systems to prevent further communication with malicious entities. Implement network segmentation to monitor and limit lateral movement. Perform system hardening, including patching vulnerabilities used by the adversary. Use endpoint detection and response tools to analyze affected systems for persistence mechanisms and remove identified malware. |
