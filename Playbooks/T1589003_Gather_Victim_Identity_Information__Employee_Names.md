# Gather_Victim_Identity_Information:_Employee_Names - T1589003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1589.003 |
| MITRE Sub-TTP | T1589.003 |
| Name | Gather Victim Identity Information: Employee Names |
| Log Sources to Investigate | Monitor social media platforms, corporate directories, and any online databases for unusual requests or access patterns. Collect logs from web servers, focusing on requests to employee directories or 'about us' pages. Examine DNS logs for domains closely resembling the legitimate corporate domain (typosquatting). Additionally, monitor the usage of corporate credentials on third-party platforms or services, which may indicate credential stuffing attempts. |
| Key Indicators | Unusual amounts of requests to employee directories or 'about us' sections on corporate websites. Discovery of employee-related information in unauthorized public locations or forums. Access attempts from IP addresses not normally associated with legitimate business operations, possibly indicative of scraping or brute force behaviors. |
| Questions for Analysis | Have there been any recent spikes in access to web pages with employee data? Are there any instances of failed attempts from unknown IP addresses trying to access employee information? Have employees reported suspicious emails or social media connection requests recently? |
| Decision for Escalation | Escalate if there are patterns of repeated access attempts from known threat actor IP addresses or if employee names are found being discussed or sold on forums linked to cybercrime activities. Also, escalate if there's any evidence of successful phishing attempts leading to data exposure. |
| Additional Analysis Steps for L1 | Perform reputation checks on IP addresses identified in the logs. Correlate access attempts with user behavior analytics to discern anomalies. Check for recorded phishing attempts or any reports of suspicious communication targeting employees. |
| T2 Analyst Actions | Conduct a deeper dive into network traffic patterns to identify any C2 communication linked with data exfiltration. Utilize threat intelligence sources to determine if compromised employee lists are circulating on the dark web. Review any endpoint protection logs for suspicious behaviors linked to data extraction. |
| Containment and Further Analysis | Implement geofencing or IP blocking for suspicious requests. Update and enforce security policies regarding data access, especially for pages containing sensitive employee information. Consider strengthening two-factor authentication methods for accessing employee databases. Run a full audit on affected systems to ensure no further unauthorized access or data extraction has occurred. |
