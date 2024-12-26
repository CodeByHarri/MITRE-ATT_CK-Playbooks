# Gather_Victim_Org_Information:_Identify_Roles - T1591004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1591.004 |
| MITRE Sub-TTP | T1591.004 |
| Name | Gather Victim Org Information: Identify Roles |
| Log Sources to Investigate | Investigate logs from web proxy servers, DNS requests, firewall logs, email gateways, and employee access logs. Specifically, look for unusual patterns such as repeated access to organizational structure charts, access to internal directories listing employee roles, or external searches that resolve to employee social media or networking sites. Examples include logs showing searches for key personnel on company websites or social media platforms, and DNS queries indicating possible reconnaissance activity. |
| Key Indicators | Indicators include repeated or unusual access to pages containing personnel or organizational role information, sudden surges in these accesses, external searches correlating known employee names or roles with sensitive data access points, and phishing attempts directed towards roles with elevated access privileges. |
| Questions for Analysis | 1) Are there repeated access attempts to sensitive internal directories?<br>2) Are the access attempts outside the typical scope of the user's role?<br>3) Has there been any phishing attempt or suspicious communication targeting key personnel or sensitive roles? 4) Are external sources accessing information correlated with known employee roles indicating possible targeting? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of external IP addresses querying internal role data, if queries correspond with known phishing campaigns, or if attempts are tied to key personnel with elevated access privileges, suggesting potential compromise or espionage. |
| Additional Analysis Steps for L1 | 1) Confirm the legitimacy of the source IP addresses accessing role information.<br>2) Corroborate the activities with user's typical behavior and role within the organization.<br>3) Verify if accessed employee information correlates with larger reconnaissance evidence or known phishing attempt indicators. |
| T2 Analyst Actions | Conduct deeper packet analysis on suspect transactions, engage with threat intelligence to identify potential linked campaigns or actors, verify links to known adversary TTPs, and assess potential impacts by simulating what access such gathered roles might grant. |
| Containment and Further Analysis | Isolate systems showing suspicious access patterns to credentialed data, enforce stricter access controls temporarily, and extend monitoring of key personnel activities. Consider mandatory password changes and MFA enrollment for impacted users. Analyze potential exfiltration paths, and coordinate with HR to verify and secure impacted role directories or sensitive business processes exposed during reconnaissance. |
