# External_Remote_Services - T1133

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Initial Access, Persistence |
| MITRE TTP | T1133 |
| MITRE Sub-TTP | T1133 |
| Name | External Remote Services |
| Log Sources to Investigate | Monitor VPN logs, Citrix access logs, and other remote service access logs for unusual access patterns or locations. Analyze firewall logs for inbound traffic targeting external remote service ports, and look into authentication logs for failed login attempts or logins from unusual IP addresses. Specific examples include AWS CloudTrail logs for AWS environments and Kubernetes audit logs in containerized setups. |
| Key Indicators | Successful logins from unfamiliar geographic locations or IP addresses, especially if they deviate from the user's typical access patterns. Multiple failed login attempts followed by a successful login may suggest credential phishing. Unexpected or unusual VLAN activity on the corporate network may also indicate unauthorized access. |
| Questions for Analysis | Has the user's IP address been seen previously in legitimate activity? Are there any correlated logs indicating lateral movement or additional suspicious activity following this access? Was multi-factor authentication bypassed or not used during the login session? |
| Decision for Escalation | Escalate if the source IP of access is from a known malicious range or shows anomalies against baseline user behavior patterns. Additionally, escalate if there are signs of lateral movement or elevated privileges post-access that are inconsistent with the user's role. |
| Additional Analysis Steps for L1 | Validate if the VPN or remote access belongs to a legitimate user session and check other access logs associated with the same session. Confirm whether the IP address geolocation matches the user's current known physical location or recent travel history. |
| T2 Analyst Actions | Perform deeper threat hunting using threat intelligence databases to cross-reference IPs against known threat actors or blacklists. Analyze any lateral movement activities associated with the account and correlate with external tools or command execution logs. Identify any related EDR alerts that may coincide with the remote session. |
| Containment and Further Analysis | Block IP addresses identified as malicious or within guilty ranges and quarantine affected user accounts. Terminate any ongoing suspicious sessions and force password resets for affected accounts. Conduct a thorough forensic investigation of PCs or devices linked to the suspicious activity to identify any malware or unauthorized changes. Ensure multi-factor authentication is fully enforced across all remote access services. |
