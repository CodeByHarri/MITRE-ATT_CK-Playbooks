# Gather_Victim_Identity_Information - T1589

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1589 |
| MITRE Sub-TTP | T1589 |
| Name | Gather Victim Identity Information |
| Log Sources to Investigate | Review logs from email servers for unusual instances of email scraping attempts or high volumes of outgoing emails, which may signify phishing activities. Inspect web server logs for abnormal access patterns that could indicate web scraping. Examine authentication logs on access management systems for signs of unauthorized attempts to probe user identities, such as failed login attempts or the use of multiple username variations. |
| Key Indicators | Unexpected probing of user identity or authentication services, especially outside normal business hours. Unusual patterns of failed login attempts from specific IP addresses. Anomalous data access or extraction from directory services. Unexpected creation of directories or unusually high data requests targeting identity information endpoints. |
| Questions for Analysis | Are there repeated failed login attempts associated with specific usernames? Is there a pattern of accessing user identity services from non-corporate IP ranges? Has there been abnormal access to public-facing directories or user data endpoints? Are there any recent changes in user behavioral patterns that might indicate compromised accounts? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of persisted or automated attempts at gathering user identity data, or if there are successful attempts at accessing sensitive identity information. Escalate if suspicious activities coincide with alerts from threat intelligence regarding known adversary techniques. |
| Additional Analysis Steps for L1 | Correlate failed login attempts with geo-location data to assess if the source is suspected. Check for any prior security warnings or alerts linked to the identified IP addresses or related to the user accounts targeted. Review recent configuration changes in identity management systems for unauthorized modifications. Validate whether the unusual activity aligns with reported phishing incidents in the organization. |
| T2 Analyst Actions | Perform deeper inspection of network traffic to and from suspect IP addresses for data exfiltration attempts. Utilize threat intelligence tools to match the tactics or patterns with known adversary groups. Conduct a thorough review of any harvested data patterns compared to usual access to these resources. Examine endpoint activity logs for signs of malware that could facilitate identity data extraction. |
| Containment and Further Analysis | Isolate affected systems hosting or interacting with the compromised identity data resources. Consider implementing blocks on suspect IP ranges and parameters in WAF settings to prevent further probing attempts. Require a forced password reset for affected or targeted user accounts. Engage with incident response teams to conduct a full forensic analysis of compromised assets and determine if any identity data has been exfiltrated. Conduct phishing awareness training if a phishing vector was used to gather identity information. |