# Search_Open_Websites_Domains:_Social_Media - T1593001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1593.001 |
| MITRE Sub-TTP | T1593.001 |
| Name | Search Open Websites/Domains: Social Media |
| Log Sources to Investigate | Monitor social media platforms for unusual activity related to organizational profiles or employees. Logs from security monitoring tools that track mentions of the organization on social media or employee personal accounts that may contain sensitive information. Monitor data aggregation services like Data Loss Prevention (DLP) tools, social media monitoring tools (e.g., Brand24, Mention), and Open Source Intelligence (OSINT) platforms for anomalous activity or mentions. |
| Key Indicators | Detection of fake social media profiles mimicking employee accounts; High volume of posts or messages mentioning organizational-specific information; Unusual account activities or sudden surges in engagement on employee social media profiles; Discovery of fake or unauthorized groups or pages claiming association with the organization. |
| Questions for Analysis | Is the social media profile found associated with company legitimate? Are there posts or interactions from this account seeking sensitive information or impersonating employees; Is there a history of similar activities from this user or group? Are employees reporting any suspicious contacts or activities on social media? |
| Decision for Escalation | Escalate if there is confirmation of a fake profile leveraging company details; Report if multiple employee profiles are targeted or impersonated; Concern if sensitive or internal information is suspected to be disclosed or used improperly. |
| Additional Analysis Steps for L1 | Verify legitimacy of social media accounts with the involved employees; Cross-reference found profiles/groups against known company accounts; Review recent employee trainings and awareness regarding social media threats; Check whether data from these fake profiles matches any known data breaches or internal leaks. |
| T2 Analyst Actions | Perform detailed OSINT reconnaissance on the fake profiles/groups; Collaborate with platform providers to request takedown of malicious profiles/groups; Consult with the legal team if company branding is misused; Engage with threat intelligence teams to assess broader campaign implications or actor linkage. |
| Containment and Further Analysis | Notify and educate employees about the specific threat and advise on corrective actions (e.g., enhancing privacy settings); Conduct internal phishing awareness sessions if social media compromise could lead to spearphishing; Schedule regular monitoring of social media channels for emerging threats and continuously update detection capabilities. |
