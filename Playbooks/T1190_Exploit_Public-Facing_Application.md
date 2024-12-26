# Exploit_Public-Facing_Application - T1190

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Initial Access |
| MITRE TTP | T1190 |
| MITRE Sub-TTP | T1190 |
| Name | Exploit Public-Facing Application |
| Log Sources to Investigate | Web server logs, Network intrusion detection system (NIDS) alerts, Firewall logs, Cloud provider logs, Container orchestration logs (e.g., Kubernetes), Application logs, Vulnerability management system alerts. Examples include Apache or Nginx access logs, Azure/AWS console logs, SNMP request logs, and any API access logs related to cloud or container services. |
| Key Indicators | Unusual access patterns or geolocations in web server logs, Failed login attempts followed by successful access, Sudden spikes in traffic or access at odd times, Known vulnerability signature patterns in NIDS logs, Unusual API access or privilege escalation indications, Off-hours or unexpected IP addresses trying to access management portals. |
| Questions for Analysis | Does the network traffic show any signs of abnormality or unusual patterns? Are there any entries in the logs indicating exploitation attempts on known vulnerabilities? Can the access requests be correlated with any legitimate user actions or operations? Are there signs of unauthorized privilege escalation? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed evidence of exploitation attempts or if the vulnerability exploited matches any CVE with known high severity. Also escalate if there are repeated unusual access attempts from suspicious IPs or consistent patterns of unsuccessful log in followed by a successful one. |
| Additional Analysis Steps for L1 | Correlate events from various logs to identify if there is a pattern or coordinated exploitation attempt. Review recent vulnerability scan reports to check if relevant vulnerabilities were identified. Verify if the exploit attempts correlate with any known public exploits or POCs. |
| T2 Analyst Actions | Conduct a deeper investigation into the specific logs identified by Tier 1, especially focusing on any correlation with known vulnerabilities. Check for any indicators of lateral movement or further compromise within the network. Confirm if the exploited application is patched or not and map it with the timelines of suspicious activities. |
| Containment and Further Analysis | Immediately apply patches for known vulnerabilities and reinforce perimeter defenses. Temporarily block suspicious IPs identified during the analysis. Implement additional monitoring on affected applications and examine related systems for signs of lateral movement or secondary infections. Collaborate with development and operations teams to address and verify any misconfigurations identified. Conduct a thorough review of the security configurations for cloud/container environments and apply the principle of least privilege to IAM configurations. |
