# Develop_Capabilities:_Malware - T1587001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1587.001 |
| MITRE Sub-TTP | T1587.001 |
| Name | Develop Capabilities: Malware |
| Log Sources to Investigate | Monitor developer environment logs, including version control systems (e.g., Git), build and CI/CD logs for evidence of unauthorized or suspicious modifications. Review application server logs for anomalous requests or behavior indicative of malicious payload deployment. Network traffic logs should be analyzed for unusual patterns or connections, especially related to command and control (C2) infrastructure. Endpoint detection and response (EDR) solutions should be checked for signs of file manipulation or unusual command executions. |
| Key Indicators | Presence of new or modified files associated with known malware projects in repository logs. Anomalous code commits that contain obfuscated code segments or unusual dependencies. Network traffic involving IP addresses or domains associated with known C2 infrastructure, especially use of web services like Twitter for C2 communication. Unrecognized binaries or script executions on production systems. |
| Questions for Analysis | Are there unauthorized changes or additions in the repository that resemble known malware components? Does the network traffic include communication to suspicious domains or IP addresses known for C2 activities? Are there undocumented binaries or scripts being executed trying to conduct unnecessary outbound network connections? |
| Decision for Escalation | Escalate to Tier 2 if analysis reveals unauthorized code changes in high-risk environments, any communication to known malicious infrastructure, or unexpected execution of binaries/scripts on critical systems. |
| Additional Analysis Steps for L1 | Verify the legitimacy of code changes by cross-referencing with project requirements. Check the origin of suspicious network traffic and validate if any external parties were authorized for development. Use sandbox environments to safely execute and analyze suspicious binaries or scripts. |
| T2 Analyst Actions | Perform a deep dive into code changes to identify potential stealthy malware functionalities. Correlate the IP and domain indicators with threat intelligence sources to ascertain intent. Leverage forensic analysis on the systems suspected of being compromised to identify any backdoors or unauthorized persistent mechanisms. |
| Containment and Further Analysis | Isolate affected systems from the network immediately to prevent further malicious activity. Conduct a thorough review of all code and infrastructure affected or potentially compromised. Enhance monitoring on systems for any newly identified IOCs. Plan for eradication through comprehensive incident response involving patching and remediation of exploited vectors. |
