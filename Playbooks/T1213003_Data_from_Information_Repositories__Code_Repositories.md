# Data_from_Information_Repositories:_Code_Repositories - T1213003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1213.003 |
| MITRE Sub-TTP | T1213.003 |
| Name | Data from Information Repositories: Code Repositories |
| Log Sources to Investigate | Logs from code repository platforms (e.g., GitHub, GitLab) including access logs, commit histories, and repository events. Web application logs showing access to internal code repositories, and authentication logs for command-line utilities like git. |
| Key Indicators | Unusual access times, especially from non-standard IP addresses. Large data exports or cloning of repositories. Access to multiple repositories in a short span of time. Failed login attempts followed by successful login, possibly indicating brute force or credential stuffing. |
| Questions for Analysis | 1. Were the login attempts and repository accesses made from recognized IP addresses?<br>2. Is there evidence of successful logins after failed attempts indicating potential credential compromise?<br>3. Were sensitive or high-value repositories accessed that are not typically accessed by the user in question? |
| Decision for Escalation | Escalate to Tier 2 if anomalous access patterns are identified, such as access from unusual locations, times, or taking large volumes of data. Also, escalate if any unauthorized change or suspicious export activity is detected. |
| Additional Analysis Steps for L1 | Verify the IP addresses and geolocations of the access logs. Check for any anomalies in access patterns concerning user behavior and typical access times. Correlate the logs with other network activity to identify potential lateral movement. |
| T2 Analyst Actions | Conduct a deeper analysis of anomalies found in the access patterns. Review the downloaded or cloned files for any sensitive or proprietary information. Identify if there are related activities indicating further suspicious behavior, such as attempted privilege escalation. |
| Containment and Further Analysis | Initiate actions to lock affected accounts. Reset credentials if necessary. Implement MFA on sensitive repositories. Conduct a security review of the repositories and assess what data may have been exposed. Recommend enhanced monitoring on the network for signs of lateral movement or further compromise. |
