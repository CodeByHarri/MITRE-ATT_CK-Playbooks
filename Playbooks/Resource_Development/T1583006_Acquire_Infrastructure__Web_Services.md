# Acquire_Infrastructure:_Web_Services - T1583006

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1583.006 |
| MITRE Sub-TTP | T1583.006 |
| Name | Acquire Infrastructure: Web Services |
| Log Sources to Investigate | Monitor and analyze logs from web service providers such as AWS, Google Cloud, or Azure for account creation and access patterns. Review network traffic logs for anomalies and analyze DNS logs to correlate with known web service endpoints. Also, track user-agent strings associated with these services, as well as firewall and proxy logs for unusual outbound connections to common web service IPs. |
| Key Indicators | High volume of account creation in a short period for web services. Unusual access to web services not typically used within the organization. Connections to known web service IP ranges at odd hours or from unauthorized endpoints. Presence of user-agent strings associated with scripts or automated tools. |
| Questions for Analysis | Are there any known legitimate needs for new web service accounts being created by the monitored identities? Do the access patterns of these accounts deviate from normal operational behavior? Do the network connections match with expected usage, both in terms of frequency and timing? |
| Decision for Escalation | Escalate to Tier 2 if there is no clear business justification for the creation and use of new web service accounts, or if there is evidence of account activities aligning with known attack patterns or techniques. Escalate if the investigation uncovers credentials that are being reused or abused. |
| Additional Analysis Steps for L1 | Verify existing logged events for correlations between account creation and usage anomalies. Cross-reference with threat intelligence feeds to identify known malicious IPs or domains associated with the web services. Investigate any alerts triggered by abnormal data exfiltration patterns or use of rare protocols. |
| T2 Analyst Actions | Conduct deeper investigation into the registration and usage timeline of the suspicious web service accounts. Check historical logs for similar patterns of behavior. Utilize threat intelligence to further investigate the identified suspicious connections. Engage with web service providers for additional context or logs if necessary. |
| Containment and Further Analysis | If malicious activity is confirmed, disable suspicious accounts and block associated IP addresses at the firewall. Work with the IT team to roll out patches to address potential vulnerabilities. Consider implementing network segmentation to isolate sensitive data and control access to critical systems. Forensically image affected systems for detailed investigation. |
