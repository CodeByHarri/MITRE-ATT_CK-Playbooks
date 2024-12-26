# Data_from_Information_Repositories:_Confluence - T1213001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1213.001 |
| MITRE Sub-TTP | T1213.001 |
| Name | Data from Information Repositories: Confluence |
| Log Sources to Investigate | Monitor Confluence access logs, including successful and failed login attempts. Track changes to access permissions and document retrieval activities. Check for unusual access patterns, such as access from non-corporate IPs or at unusual hours. Review network traffic logs for data exfiltration signs. Examples include access logs, audit logs, and network flow logs. |
| Key Indicators | Unusual access patterns to Confluence pages/documents, especially those containing sensitive data. Repeated failed or new successful login attempts from unknown or suspect IP addresses. Massive data retrieval within a short span or during non-business hours. Changes in user roles or permissions by unauthorized users. |
| Questions for Analysis | Does the user accessing the information have legitimate needs as per their role? Is there a historical pattern of access that aligns with current activities? Are the source IP addresses used for access known and authorized? Are there any recent changes in user roles or permissions that could have led to unauthorized access? |
| Decision for Escalation | Escalate if there are multiple indicators such as volume data access, unusual access times, and suspect IP addresses. Additionally, escalate if changes in user permissions appear unauthorized. Document any corroborating user-reported issues or security incidents. |
| Additional Analysis Steps for L1 | Verify IP addresses accessing sensitive documents against whitelist of authorized sources. Correlate current activity with previous logs to identify anomalies or patterns. Cross-reference user access with HR records to confirm employment status and role. |
| T2 Analyst Actions | Conduct deeper log analysis for pattern recognition. Utilize threat intelligence resources to match IPs with known malicious activity. Interview involved parties to ascertain legitimate access needs. Integrate findings with incident response protocols. |
| Containment and Further Analysis | Restrict affected user access pending investigation. Implement stricter access controls or multi-factor authentication. Monitor network traffic for signs of further exfiltration attempts. Work with IT to patch vulnerabilities in Confluence configurations. Engage with legal and compliance for potential breach notification requirements. |
