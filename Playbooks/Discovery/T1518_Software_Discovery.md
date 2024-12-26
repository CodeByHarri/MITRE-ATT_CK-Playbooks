# Software_Discovery - T1518

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1518 |
| MITRE Sub-TTP | T1518 |
| Name | Software Discovery |
| Log Sources to Investigate | Analyze logs related to software inventory and management tools. This includes system logs that record the execution of commands like 'wmic product get name,version', 'dpkg -l' on Linux, or Azure/AWS service logs if cloud environments are involved. Additionally, monitoring logs from software deployment and system management tools such as SCCM (System Center Configuration Manager), Ansible, or Chef can provide insights into unusual activities. |
| Key Indicators | Unusual queries for software listing or enumeration commands being run on endpoints, especially from non-administrative accounts. Elevated privilege use that is not typical for a user or service account, and sudden, automated, or repetitively scheduled tasks that involve software enumeration. |
| Questions for Analysis | 1. Is the software enumeration log timestamp during non-business hours or associated with unusual user behavior?<br>2. Does the querying entity have legitimate reasons or permissions to enumerate installed software?<br>3. Are there any correlated alerts or incidents from associated assets? 4. Is there any historical suspicious behavior recorded for the user or system? |
| Decision for Escalation | Escalate to Tier 2 if the analysis reveals enumeration activities linked to suspicious user accounts, particularly if there is no clear legitimate, business reason. Also escalate if these activities coincide with other suspicious indicators such as logs showing privilege escalation or unusual external connections. |
| Additional Analysis Steps for L1 | Check for any recent changes in user group policies or permissions that could explain the access. Verify if there are any associated security patches or updates that coincide with these activities. Look for conjunction alerts in other areas, such as anomaly detection systems, that might correlate with this behavior. |
| T2 Analyst Actions | Conduct a deeper dive into the user's historical activity and cross-reference with other events to determine the potential scope of compromise. Examine logs for potential lateral movement indicators or failed login attempts. Review network traffic for any outbound connections that may suggest data exfiltration. |
| Containment and Further Analysis | If malicious activity is confirmed, isolate the affected systems to prevent further enumeration or potential lateral movement. Reset affected user credentials and review permissions with a focus on least privilege. Conduct a sweep of the environment to identify other potentially affected devices and review patch management procedures to close vulnerabilities. |
