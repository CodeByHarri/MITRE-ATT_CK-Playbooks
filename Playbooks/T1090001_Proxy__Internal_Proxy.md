# Proxy:_Internal_Proxy - T1090001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1090.001 |
| MITRE Sub-TTP | T1090.001 |
| Name | Proxy: Internal Proxy |
| Log Sources to Investigate | Network traffic logs, particularly focusing on anomalous or unusual network patterns, such as repeated connections through internal IPs not typically serving as network intermediaries. Endpoint logs where proxy software may be installed, such as unusual port usage or unexpected software installations. Windows Event Logs, especially relating to SMB traffic and connection events between systems. |
| Key Indicators | Increased internal network traffic between systems not typically communicating directly. Presence of proxy or port redirection tools like HTRAN or ZXProxy. SMB traffic patterns that do not match normal business operations. Changes in network configuration or routing tables indicating redirection. |
| Questions for Analysis | Do the network connections show unexpected internal traffic patterns? Is there new software or changes in existing software related to proxy services on the endpoints in question? Are there known indicators of compromise, such as signatures of tools like HTRAN, present in the network or endpoint logs? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmation of unusual proxy software installation, unexpected network traffic consistent with internal traffic redirection, or concrete indicators that internal systems are acting as intermediaries for other systems. |
| Additional Analysis Steps for L1 | Verify the legitimacy of internal network traffic patterns identified by reviewing baseline data of normal network interactions. Check log data for any known signatures or fingerprints associated with tools like HTRAN or ZXProxy. Correlate anomalous behavior with recent changes or alerts in related systems. |
| T2 Analyst Actions | Conduct deeper packet analysis to confirm the use of proxy software and investigate the configuration and parameters of the software. Verify any external connections initiated by the internal proxy and search for additional compromised systems. Utilize threat intelligence to reinforce detection and identify associated tactics or campaigns. |
| Containment and Further Analysis | Isolate identified systems acting as internal proxies to prevent further lateral movement or external communications. Conduct forensic analysis on the isolated systems to determine entry points and identify all affected systems. Apply patches or configuration changes to mitigate vulnerabilities exploited by the adversary, and ensure logging and monitoring policies are refined to detect similar activities in the future. |
