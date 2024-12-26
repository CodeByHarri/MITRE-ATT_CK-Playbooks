# Exfiltration_Over_Web_Service:_Exfiltration_Over_Webhook - T1567004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Exfiltration |
| MITRE TTP | T1567.004 |
| MITRE Sub-TTP | T1567.004 |
| Name | Exfiltration Over Web Service: Exfiltration Over Webhook |
| Log Sources to Investigate | Investigate web server logs to trace HTTP/S requests to known webhook endpoints. Network traffic logs should also be analyzed to identify unusual traffic patterns to domains associated with webhooks or SaaS services like Discord, Slack, etc. If applicable, SaaS platform logs such as Trello or Jira activity logs can also provide insights into what data is being accessed and potentially exfiltrated. Lastly, review any logs from DLP (Data Loss Prevention) systems that may identify potential data exfiltration events. |
| Key Indicators | Look for sudden increases in HTTP POST requests to known webhook URLs, especially from non-standard or suspicious user agents. Monitoring traffic to domains used by popular webhook services such as webhook.site, api.slack.com, etc., can be telling. Additionally, examine if there are repeated data transfer patterns to these webhook endpoints or any deviation from typical user activity metrics. |
| Questions for Analysis | Is this webhook communication consistent with known, legitimate webhook configurations or is it new/unknown? Is there a notable pattern of increased data size being transmitted? Do the endpoints being contacted suggest unauthorized use, such as endpoints not previously authorized under current business operations? |
| Decision for Escalation | Escalate to Tier 2 if the webhook traffic is directed to unknown or unverified endpoints, or if there is significant deviation from baseline network behavior patterns, especially if it involves sensitive or large datasets potentially containing sensitive information. |
| Additional Analysis Steps for L1 | Confirm whether the detected webhook endpoint traffic is aligned with authorized services or application uses. Document any anomalies or indicators linked to potential adversarial use. Verify whether this traffic deviates from established user behaviors or business processes. |
| T2 Analyst Actions | Conduct a deeper analysis of the network traffic to verify if any known malicious indicators are present in the payload. Use threat intelligence to verify if the destination IP or URL is linked to any suspicious activities. Assess the possibility of lateral movement and other compromised points within the network. |
| Containment and Further Analysis | If adversarial use is confirmed, disable offending user accounts and webhook configurations while alerting impacted services. Block the malicious IPs and URLs from accessing the network. Begin a thorough forensic investigation to determine the extent of the breach and root cause. Consider implementing additional network segmentation or applying stricter DLP policies to prevent similar activities in the future. |
