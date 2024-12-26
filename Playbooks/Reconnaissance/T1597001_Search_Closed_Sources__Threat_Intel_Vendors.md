# Search_Closed_Sources:_Threat_Intel_Vendors - T1597001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1597.001 |
| MITRE Sub-TTP | T1597.001 |
| Name | Search Closed Sources: Threat Intel Vendors |
| Log Sources to Investigate | Monitor logs from threat intelligence platforms and vendor portal access logs. This includes authentication logs, access timestamps, and any download activity. Examples: SIEM data tracking user authentication to threat intel portals, firewall logs for web-based accesses, and potentially any alerting systems for access to newly published datasets. |
| Key Indicators | Unusual access patterns to threat intelligence portals, such as accesses from new IP addresses, volumes of data downloads exceeding normal activity, unexpected attempts to access specific intelligence report sections. Also, notable increase in user accounts querying threat intelligence platforms. |
| Questions for Analysis | Is there a spike in access attempts to the threat intel portal from atypical IP addresses or geographical locations? Are there any new user accounts accessing the intel that hadn't previously? Are there signs of credential misuse or sudden changes in account behavior? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed unauthorized access to valuable threat intelligence data, a high volume of data transfer/downloads is observed from unusual sources, or if there are repeated access attempts resulting in account lockouts. |
| Additional Analysis Steps for L1 | Check for any recent changes in user account permissions or password resets related to threat intel access. Review firewall and proxy logs to assess the volume and IP addresses of outbound connections related to threat intelligence vendors. |
| T2 Analyst Actions | Validate any anomalies identified by Tier 1. Correlate the suspicious access patterns with recent threat researcher publications and assess the impacted data, if any. Conduct a deep dive into user activity logs and establish the authenticity and necessity of the accesses. |
| Containment and Further Analysis | If unauthorized access is confirmed, immediately revoke access for the compromised accounts and reset credentials. Notify leadership and potentially impacted partners regarding the data exposure. Conduct a forensic analysis on the host systems involved to trace back any malware or scripts used in the unauthorized access attempt. |
