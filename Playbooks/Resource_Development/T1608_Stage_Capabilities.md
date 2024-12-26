# Stage_Capabilities - T1608

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1608 |
| MITRE Sub-TTP | T1608 |
| Name | Stage Capabilities |
| Log Sources to Investigate | Network traffic logs (e.g., firewall, proxies) to identify unusual communication patterns or unexpected data transfers; web server logs for unexpected uploads or changes in hosted resources; cloud service logs (e.g., Azure, AWS, Google Cloud) to check for unauthorized provisioning or uploads; endpoint detection and response (EDR) logs for signs of tool/malware staging; application logs like GitHub or PaaS offerings for unexpected files or services set up. |
| Key Indicators | Unusual or unexpected network traffic to/from external IPs often associated with known threat actors or suspicious activity; new or modified files on web servers or cloud platforms, particularly if they are executable files or scripts; unauthorized access attempts or new provisioning of resources in cloud environments; presence of known malicious files or hash values in uploaded content; new SSL/TLS certificates, especially those installed outside normal operational procedures. |
| Questions for Analysis | Is the staged content or infrastructure change aligned with legitimate business operations? Are there any known threat actor IPs or domains associated with these activities? Was the involved cloud or web service account compromised or accessed from unfamiliar locations? Is there any correlation with earlier alerts or incidents? |
| Decision for Escalation | Escalate to Tier 2 if the staged content includes known malware hashes or signatures; there are signs of compromise on critical infrastructure; suspicious external IPs involved with known associations with threat actors; anomalies cannot be explained by routine business operations. |
| Additional Analysis Steps for L1 | Review network and application logs for timeline and origin of changes; correlate with any user activity or access patterns; check for recent patches or updates that could correlate with staged activities; verify configuration and security posture of involved infrastructure or services. |
| T2 Analyst Actions | Conduct deeper analysis of identified indicators, including sandboxing suspicious files or URLs; cross-reference known threat intelligence data for matches; assess broader organizational impact by mapping potential lateral movement from staged resources; verify account activity for legitimate and unauthorized actions. |
| Containment and Further Analysis | Disable access or isolate affected infrastructure/services; remove or quarantine malicious files or tools; conduct a full security assessment and audit of permissions and access rights; implement monitoring to detect similar future activities; communicate findings and advisory to relevant stakeholders for awareness and further action. |
