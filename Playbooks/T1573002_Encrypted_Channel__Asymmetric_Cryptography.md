# Encrypted_Channel:_Asymmetric_Cryptography - T1573002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1573.002 |
| MITRE Sub-TTP | T1573.002 |
| Name | Encrypted Channel: Asymmetric Cryptography |
| Log Sources to Investigate | To investigate this TTP, focus on network traffic logs, specifically looking at unusual asymmetric encryption usages outside of typical protocols like SSL/TLS. Examples of log sources include: Firewall logs to check traffic patterns and endpoints; Intrusion Detection System (IDS) logs for alerts or anomalies in encryption usage; Host-based monitoring solutions for identifying encryption libraries or services being used on endpoints. |
| Key Indicators | Look for network connections that involve initial asymmetric encryption setup that does not transition to expected protocols like SSL/TLS (e.g., RSA handshake detected without subsequent TLS traffic). Monitor for non-standard ports conducting encryption activities. Anomalies in the number or source of encrypted traffic sessions can be a strong indicator. |
| Questions for Analysis | 1. Is there evidence that the detected asymmetric encryption traffic is part of a known or established application/service in the environment?<br>2. Does the traffic originate from or is directed to a known suspicious domain or IP address?<br>3. Is there atypical volume or frequency of encrypted sessions from a single source? |
| Decision for Escalation | Escalate to Tier 2 if: The encryption is associated with traffic to or from known malicious IP addresses or domains. High volume of asymmetric encryption is conducted by hosts not typically associated with such activities. Unexplained asymmetric encryption activities are detected outside standard business applications or hours. |
| Additional Analysis Steps for L1 | Review logs for specific timeframes where asymmetric encryption was active. Identify source and destination IPs for encryption activities. Check whether legitimate applications/services are linked to these IPs or domains. Validate encryption patterns against known application behaviors. |
| T2 Analyst Actions | Conduct deeper packet analysis using captured network traffic for hidden data payloads in encrypted traffic. Correlate findings with threat intelligence to determine if IP addresses or domains are associated with known threat actors. Perform a risk assessment on the affected systems, considering the scope and potential impact. |
| Containment and Further Analysis | If malicious activity is confirmed, isolate the involved systems preventing further encrypted communication. Change encryption keys if asymmetric keys were involved to prevent misuse. Enhance monitoring on similar traffic to identify additional compromises. Conduct a forensic investigation on impacted systems to determine compromise severity. |
