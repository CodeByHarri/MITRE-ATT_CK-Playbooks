# Gather_Victim_Host_Information:_Hardware - T1592001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1592.001 |
| MITRE Sub-TTP | T1592.001 |
| Name | Gather Victim Host Information: Hardware |
| Log Sources to Investigate | Network traffic logs, including DNS logs and HTTP/HTTPS logs to identify unusual outbound connections. Endpoint logs to gather evidence of attempts to access hardware information, such as system configuration files or API queries. Security information and event management (SIEM) alerts triggered by unusual application behavior or fingerprinting attempts. |
| Key Indicators | Unusual queries to system management tools or APIs related to hardware information. Unexpected outbound connections to IPs/domains with no apparent relation to business processes. Suspicious HTTP headers or user-agent strings that indicate attempts to gather system-specific information. Alerts from security solutions on anomalous processes performing network scans or direct access to system files. |
| Questions for Analysis | Is there a legitimate business process that might require the gathering of host hardware information? Do connection attempts align with known IPs/domains related to the company's operations? Are there other logs (like email or endpoint) showing related suspicious activities that could aggregate into a larger context of compromise? |
| Decision for Escalation | Escalate if evidence of unauthorized access to hardware information or consistent and unexplained scanning activities is present. If there are confirmed interactions with known malicious IPs/domains or detection tools have flagged certain activities as high-risk, escalate the findings. |
| Additional Analysis Steps for L1 | Correlate timestamps of suspected hardware information gathering attempts with other suspicious activities such as phishing emails received. Use threat intelligence platforms to identify if IPs/domains involved have previous crime-ware or malware ties. Cross-reference with recent alerts for anomalies in user behavior analysis. |
| T2 Analyst Actions | Conduct a deeper forensic analysis on endpoints suspected of being used for hardware information gathering. Review network data to trace the path and destination of the suspected data exfiltration. Utilize more detailed threat intelligence and sandboxed environments to analyze unusual traffic patterns or payloads. |
| Containment and Further Analysis | Block identified malicious IPs or domains at the firewall level to prevent further data exfiltration. Quarantine compromised systems and run AV/malware scans to clean and verify system integrity. Conduct a review of security controls and incident response policies to ensure comprehensive protection and response to adversaries gathering host information. |
