# Phishing_for_Information:_Spearphishing_Service - T1598001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1598.001 |
| MITRE Sub-TTP | T1598.001 |
| Name | Phishing for Information: Spearphishing Service |
| Log Sources to Investigate | Monitor logs from webmail services and social media platforms, focusing on outbound and inbound communications. Specifically, check for unexpected communication between employees and external accounts not typically associated with business interactions. Examples include Gmail, Yahoo, LinkedIn, and other social media platforms. Additionally, analyze logs related to any suspicious account creation events and access patterns in enterprise security systems that capture such data. |
| Key Indicators | Unusual messages originating from newly created or low-activity accounts, especially those posing as recruiters or business partners. Multiple urgent messages from the same source requesting sensitive information. Anomalous login attempts, especially if they follow the interaction on a third-party platform. The appearance of communication that mirrors private information disclosed elsewhere. |
| Questions for Analysis | 1. Is there an unexpected pattern of communication with external accounts from known personal or company profiles?<br>2. Do the sender's communication methods display known social engineering techniques (e.g., urgency, authority, scarcity)?<br>3. Has the sender attempted to obtain sensitive information, such as corporate policies, login credentials, or personal identifiers? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of repeated attempts to gather sensitive information, especially if combined with social engineering efforts that bypass normal channels. Also escalate if there is any indication of successful compromise or anomalous account activities post-interaction. |
| Additional Analysis Steps for L1 | 1. Correlate outgoing messages with enterprise activity logs to identify any compromised accounts.<br>2. Check if multiple employees have been contacted by the same third-party source.<br>3. Verify whether the sender’s profile or behavior matches known threat actor tactics. |
| T2 Analyst Actions | Conduct a deeper investigation into communication trails and corroborate them with reconnaissance data. Validate the potential reach and impact by reviewing past access logs to confirm unauthorized access. Check if the communication aligns with ongoing phishing campaigns or previously identified threat actor patterns. |
| Containment and Further Analysis | Implement email and social media account monitoring for the employee(s) affected. Advise the reset of credentials if anomalous access is detected. Share threat intelligence markers with other security teams. Review broader enterprise security posture, specifically the policies controlling third-party service interactions. |
