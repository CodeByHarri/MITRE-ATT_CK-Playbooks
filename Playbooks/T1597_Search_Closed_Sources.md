# Search_Closed_Sources - T1597

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1597 |
| MITRE Sub-TTP | T1597 |
| Name | Search Closed Sources |
| Log Sources to Investigate | Monitor access logs from data brokers, dark web monitoring tools, threat intelligence platforms, and payment transactions for instances of data purchase or access. Network logs, SIEM alerts, and financial transaction systems can also provide insights into suspicious activities involving closed source data access. |
| Key Indicators | Patterns of queries or information retrieval from closed data sources about specific entities or individuals, unusual access times, or access from previously unused IP addresses/countries. Financial transactions associated with purchasing data from private intelligence feeds, dark web marketplaces, or other unconventional sources. |
| Questions for Analysis | Is there evidence of recent access to closed-source databases? Are the access patterns consistent with normal business behavior? Have there been any financial transactions indicating data purchase from suspicious sources? Is there evidence of data extraction activities following access to closed sources? |
| Decision for Escalation | Escalate if access attempts are detected from unusual locations/IP addresses, if there's a mismatch between the user's role and the data accessed, or if transactions with known illicit data sources are identified. Escalation is critical when suspicious patterns imply intent to collect targeted information on specific entities. |
| Additional Analysis Steps for L1 | Verify the legitimacy of accessed sources and the role-based access permissions for involved accounts. Check for known indicators of compromise related to ill-reputed data sources and analyze historical access patterns for anomalies. |
| T2 Analyst Actions | Deep dive into transaction records and network traffic for confirmation of data purchase. Engage threat intelligence to verify the source credibility and assess the potential impact of information acquired. Correlate access logs against known threat actor behaviors or patterns. |
| Containment and Further Analysis | If unauthorized data collection is confirmed, isolate affected systems/accounts for further forensic examination. Initiate a review of access control policies and enhance monitoring for key assets. Engage legal and compliance teams if purchase from illicit sources is verified. |
