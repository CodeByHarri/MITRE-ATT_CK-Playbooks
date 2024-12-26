# Ingress_Tool_Transfer - T1105

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1105 |
| MITRE Sub-TTP | T1105 |
| Name | Ingress Tool Transfer |
| Log Sources to Investigate | Network traffic logs to look for unusual or unauthorized data transfers. Review logs from web proxies, firewalls, and intrusion detection/prevention systems (IDS/IPS) for signs of tool transfer. Endpoint detection and response (EDR) logs to identify execution of suspicious utilities like certutil, PowerShell, curl, scp, etc. Cloud service logs to identify unusual access patterns or unauthorized file sync, especially for services like Dropbox or OneDrive. |
| Key Indicators | Unusual network traffic involving known administrative tools or protocols such as FTP, SCP, TFTP. Execution of download commands (e.g., certutil, PowerShell wget). Unexpected use of service syncing (like Dropbox or OneDrive) for file delivery. File transfers involving large or unusual amounts of data. Access to web services that were not previously used by the host or user. |
| Questions for Analysis | Was the tool transfer performed outside of normal working hours? Does the source of the tool transfer match known trusted domains/IPs? Were high-volume data transfers observed? Is the user associated with unusual cloud service access known for regular use of the service? |
| Decision for Escalation | Escalate to Tier 2 when unauthorized data transfer is confirmed or if any admin or tool transfer coincides with other indicators of compromise (IoCs). If the file transfer is associated with suspicious domains/IPs or large data exfiltration is detected, escalate immediately. |
| Additional Analysis Steps for L1 | Review EDR logs for detailed process activities around the time of the detected transfer. Verify if similar data transfers occurred on other hosts. Check any recent alerts or incidents related to the involved users or devices. |
| T2 Analyst Actions | Conduct deep analysis of command execution logs to confirm unauthorized use. Correlate findings with other suspicious activities, such as phishing attempts or unexpected user behavior. Investigate the external IP/DNS involved in the transfer for known malicious activity. Determine if the tools are part of a larger toolset being leveraged by an advanced persistent threat (APT). |
| Containment and Further Analysis | Block incoming and outgoing communication to the involved IP/DNS if malicious. Quarantine affected systems to prevent further spread within the network. Search for additional signs of compromise and lateral movement. Conduct forensic analysis on impacted devices, including memory and disk analysis, to determine further actions and identify exact tools/methods used in the infiltration. |
