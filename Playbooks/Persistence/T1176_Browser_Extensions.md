# Browser_Extensions - T1176

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1176 |
| MITRE Sub-TTP | T1176 |
| Name | Browser Extensions |
| Log Sources to Investigate | Browser logs (e.g., Chrome logs for extension installations), System logs (especially for macOS, logs related to <code>profiles</code> tool usage), Network traffic logs showcasing unusual browser behavior, Access logs from browser app stores, Endpoint Detection and Response (EDR) alerts related to browser extension installations. |
| Key Indicators | Unusual browser extensions not vetted or known, Browser extension installations without user interaction, Extensions communicating with known malicious or suspicious domains, Network packets from browsers to unexpected IPs/URLs, Evidence of manipulated extension update URLs, <code>.mobileconfig</code> files planted on macOS devices, Extensions requesting elevated permissions unnecessarily. |
| Questions for Analysis | Is the browser extension known and vetted through internal or external confidence lists? Was the extension installed without clear user action or consent? Is the extension communicating with known malicious or command and control servers? Are there any elevation in permissions requested by the browser extension that are unusual or unexplained? |
| Decision for Escalation | Escalate to Tier 2 if the extension is communicating with suspicious domains or IPs, if unexpected <code>.mobileconfig</code> files are found, or if brass abnormalities are detected in extensions permissions or behavior. A lack of legitimate justification for the presence or behavior of the extension also necessitates escalation. |
| Additional Analysis Steps for L1 | Verify the source of the extension installation via user confirmation or log investigations. Cross-reference extension hashes with threat intelligence sources. Monitor for any further suspicious network traffic originating from the browser. Run a check on potentially related security alerts on the endpoint in question |
| T2 Analyst Actions | Conduct a deeper threat intelligence analysis on the suspicious extension's behavior, Execute manual checks on the browser history and relevant endpoint activities. Investigate related network traffic patterns and inspect potential traffic captures if available. Correlate with any potential indicator of compromise or threats from intelligence databases. |
| Containment and Further Analysis | Disable or remove the suspicious extension from the affected systems or browsers immediately. Initiate a full security scan of the affected system using trusted AV/AM solutions. Using network analysis tools, determine if further systems are affected by similar browser anomalies. Update security policies and conduct an awareness campaign to prevent similar instances. |
