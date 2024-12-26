# Impair_Defenses:_Spoof_Security_Alerting - T1562011

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1562.011 |
| MITRE Sub-TTP | T1562.011 |
| Name | Impair Defenses: Spoof Security Alerting |
| Log Sources to Investigate | Investigate security tool logs from endpoints and servers, such as Windows Event Logs, Antivirus/Endpoint Detection and Response (EDR) logs, and logging from Security Information and Event Management (SIEM) systems. Look for discrepancies between tool logs and what is visually presented on the user interface, especially logs from Windows Defender or other security software services that may have been compromised or show unexpected start/stop events. |
| Key Indicators | Unusual or unexpected entries in security tool logs indicating services have been stopped or altered unexpectedly, discrepancies between log entries and GUI status, logs indicating attempts to disable or tamper security services, presence of known adversarial tools associated with impersonating security alerts. |
| Questions for Analysis | 1. Is there a mismatch between tool logs and the UI status of security tools?<br>2. Have there been recent changes to security tools or configurations that are unexpected?<br>3. Are there any known exploits or tools used in the environment to achieve similar tactics? 4. Are there alerts indicating unusual user behavior or access patterns prior to tool manipulation? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed manipulation or tampering of security tools without legitimate change requests, if you identify synchronous suspicious activities alongside manipulated alerts, or if there is corroborative evidence of lateral movement or privilege escalation potentially enabled by spoofed alert status. |
| Additional Analysis Steps for L1 | Review endpoint security and system logs to confirm the last known proper functioning of security tools. Cross-reference timestamps of log entries with system changes or user activity logs. Check for corroborating evidence of intrusion or tampering in correlated threat intelligence resources. |
| T2 Analyst Actions | Conduct in-depth analysis of affected systems, focusing on any artifacts left by the adversary. Validate findings through secondary log sources such as network traffic logs or centralized logging infrastructure. If findings suggest broader compromise, initiate threat hunts focused on lateral movement paths and privilege escalations. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent further intervention by adversaries. Engage incident response procedures to restore and verify the integrity of endpoint security tools. Conduct forensic analysis to identify persistence mechanisms or additional compromised hosts. Apply patches and security updates, and consider implementing additional monitoring solutions to detect future similar activities. |
