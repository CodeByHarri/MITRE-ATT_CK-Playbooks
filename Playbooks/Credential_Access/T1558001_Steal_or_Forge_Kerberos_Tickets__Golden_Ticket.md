# Steal_or_Forge_Kerberos_Tickets:_Golden_Ticket - T1558001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1558.001 |
| MITRE Sub-TTP | T1558.001 |
| Name | Steal or Forge Kerberos Tickets: Golden Ticket |
| Log Sources to Investigate | Investigate Windows Security Event Logs, specifically looking for Event ID 4769 (A Kerberos service ticket was requested) and Event ID 4768 (A Kerberos authentication ticket was requested). Look for anomalous ticket-granting ticket (TGT) requests or service ticket (TGS) requests. Additionally, examine Domain Controller logs and network traffic involving the Key Distribution Center (KDC). Log sources like SIEM logs, Windows Sysmon for detailed process and network events, and Active Directory audit logs should be reviewed. |
| Key Indicators | Unusual TGT creation with a long ticket lifetime, service tickets (TGS) created for privileged accounts without usual precursors, access requests from processes or systems that typically do not make such requests, and the presence of Kerberos tickets with unusual or rarely used encryption types. Monitor for anomalous patterns in the use of the KRBTGT account hash and unexpected outbound network connections to the KDC from unusual accounts. |
| Questions for Analysis | Are there any recent changes to accounts associated with critical Kerberos functions? Are there any accounts with excessive privileges suddenly requesting access to multiple resources? Have there been any anomalous login times or locations for the involved accounts? Are there any patterns of access from IP addresses or devices that aren't associated with typical business operations? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of unauthorized TGT or TGS requests, especially if involving sensitive or administrative accounts. Escalate if any KRBTGT password hash-related alerts appear, or if suspicious patterns such as unusual access requests or creation of large numbers of Kerberos tickets are detected. |
| Additional Analysis Steps for L1 | Correlate the suspected event with other authentication logs to identify the possible source and timeline of suspicious activity. Validate the involved accounts for recent password resets or privilege escalations. Check for Windows Event Logs around the specific times of the suspicious events. |
| T2 Analyst Actions | Conduct a deep dive into network traffic records associated with the detected anomalies. Analyze account usage patterns over time to identify abnormalities. Leverage threat intelligence and hunt for similar patterns highlighted in previous threats attributed to golden ticket attacks. Review patch levels and security configurations related to Kerberos and Active Directory for potential exploitation vectors. |
| Containment and Further Analysis | Initiate a password reset for the KRBTGT account and monitor for any propagated golden ticket traces. Temporarily disable affected accounts and block IPs associated with suspicious activity while further investigation is conducted. Coordinate with IT to isolate impacted systems to prevent lateral movement. Implement additional logging and monitoring to catch any recurrence or further abnormal behavior. |