# Data_Encoding:_Non-Standard_Encoding - T1132002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1132.002 |
| MITRE Sub-TTP | T1132.002 |
| Name | Data Encoding: Non-Standard Encoding |
| Log Sources to Investigate | Network traffic logs, especially focusing on HTTP/S traffic (e.g., using tools like NetFlow or packet captures from Wireshark), Proxy logs for anomalies, Web server logs for unusual encoding patterns, Intrusion Detection System (IDS) alerts for encoding anomalies, EDR logs for evidence of non-standard data encoding operations on endpoints. |
| Key Indicators | Presence of non-standard Base64 or similarly encoded strings in HTTP headers, URL parameters, or POST body in network traffic, Inconsistent or abnormally large data payloads compared to typical traffic patterns, Uncommon or malformed data structures within outbound communications, Repetitive or cyclic encoded patterns used as placeholders in communications. |
| Questions for Analysis | Does the encoding scheme deviate from known standards within the context used? Is there a persistent connection or repeated data exfiltration attempt over HTTP/S or other protocols? Are there patterns of communication at unusual times indicative of C2 activity? Has the source or destination of the traffic been involved in previous suspicious activities? |
| Decision for Escalation | Escalate to Tier 2 if non-standard encoding patterns are repeatedly observed in communications involving sensitive networks or if initial analysis suggests the encoding could be related to known C2 frameworks. Also, escalate if the analysis shows correlation with threat intelligence indicators of compromise linked to non-standard encoding. |
| Additional Analysis Steps for L1 | Conduct a pattern analysis on suspected encoded data to determine potential encoding methods. Compare observed encoded traffic with known malicious encoding schemes (e.g., modified Base64 patterns). Check against recent threat intelligence for any mentions of similar encoding schemes being used in attacks. |
| T2 Analyst Actions | Perform a deep packet inspection on identified traffic to extract complete encoded strings for analysis. Decode the suspected non-standard encoded data to check for any cleartext C2 instructions or data exfiltration. Correlate findings with known threat actor TTPs using the database of recent threat actor activity and MITRE ATT&CK references. |
| Containment and Further Analysis | Isolate the host from which the suspect traffic originated to prevent further data leakage. Implement network segmentation to contain potential threat spread. Utilize a sandbox environment to test decoded data for potential threats. Conduct a forensic analysis on endpoints to search for signs of encoding tools or scripts. Continue to monitor traffic for recurring patterns and adapt detection alerts and thresholds accordingly. |
