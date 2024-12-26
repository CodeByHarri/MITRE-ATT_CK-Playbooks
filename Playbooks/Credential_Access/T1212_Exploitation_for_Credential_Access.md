# Exploitation_for_Credential_Access - T1212

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1212 |
| MITRE Sub-TTP | T1212 |
| Name | Exploitation for Credential Access |
| Log Sources to Investigate | Monitor authentication logs from Kerberos, as well as network traffic logs focusing on any unusual replayed packets. Investigate cloud service logs, particularly those involving authentication token generation and renewal. Additionally, examine application logs for any anomalies in successive authentication attempts. For example, Microsoft Security Event logs, AWS CloudTrail, or Azure AD Sign-In logs can provide relevant information. |
| Key Indicators | Look for evidence of unusual or unauthorized attempts to create or manipulate Kerberos tickets. Network traffic patterns indicating replayed authentication packets are key indicators. Also, unexpected authentication token creation or renewal in cloud environments could signal exploit attempts. Indicators may include spikes in failed authentication attempts or the presence of packets with identical sequence numbers. |
| Questions for Analysis | 1. Are there any signs of unusual Kerberos ticket activities or errors suggesting tampering?<br>2. Is there evidence of identical packet data being sent multiple times, indicating a replay attack?<br>3. Are cloud service logs showing inappropriate or unexpected token activity? 4. Is there an abnormal increase in failed login attempts across the network or specific accounts? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed or strongly suspected evidence of Kerberos ticket exploitation, repeated packet anomalies indicative of replay attacks, or confirmed unauthorized token activity. Evidences of successful use of known exploits like MS14-068 should also be escalated. |
| Additional Analysis Steps for L1 | Review the context around suspicious network traffic patterns, noting destination and source IP addresses. Verify the legitimacy of the Kerberos errors or anomalies identified. Validate whether any cloud authentication tokens were issued in unusual contexts or to inappropriate parties. |
| T2 Analyst Actions | Conduct deeper forensic analysis on affected systems to determine the extent of any credential compromise. Investigate the specific vulnerabilities that were targeted or exploited. Analyze full packet captures if available to confirm replay attacks. Review privilege levels associated with any affected accounts. |
| Containment and Further Analysis | Immediately revoke any suspicious authentication tokens. Disable affected accounts temporarily while further investigation is conducted. Patch systems vulnerable to known exploits such as MS14-068. Implement network filters to block known bad IP addresses involved in recon or attack. Consider use of additional monitoring tools to enhance visibility into credential-based activities. |
