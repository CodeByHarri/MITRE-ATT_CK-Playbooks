# Exfiltration_Over_Alternative_Protocol:_Exfiltration_Over_Symmetric_Encrypted_Non-C2_Protocol - T1048001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Exfiltration |
| MITRE TTP | T1048.001 |
| MITRE Sub-TTP | T1048.001 |
| Name | Exfiltration Over Alternative Protocol: Exfiltration Over Symmetric Encrypted Non-C2 Protocol |
| Log Sources to Investigate | Network traffic logs, firewall logs, IDS/IPS logs, and proxy logs are essential for investigating this TTP. Examples include Wireshark packet captures, netflow records, and logs from network monitoring tools that can highlight unusual data exfiltration patterns over encrypted non-C2 channels. |
| Key Indicators | Unusual or unauthorized network traffic to external IPs, especially on ports not typically used for encrypted traffic. Detection of symmetric encryption algorithms in network traffic (e.g., unusual protocol use of RC4 or AES outside normal HTTPS traffic). Sudden spikes in outgoing data volumes could also be key indicators. |
| Questions for Analysis | Is there evidence of large or unexpected data transfers to unknown or unauthorized IP addresses? Are there signs of non-standard or unusual encryption protocols being used compared to baseline traffic? Is there any correlation with existing threat intelligence indicators related to known exfiltration techniques? |
| Decision for Escalation | Escalate if there is validation that data is being sent to unauthorized or suspicious external locations, particularly if the volume of data is significant. Escalate if analysis confirms the use of unapproved symmetric encryption protocols or if this activity matches any threat intelligence about ongoing campaigns. |
| Additional Analysis Steps for L1 | Conduct a thorough review of identified network traffic to confirm encryption used and destination legitimacy. Cross-reference identified activity with internals like asset owners and departments to verify legitimate data transfers. Verify consistency with patterns from threat intelligence. |
| T2 Analyst Actions | Perform deep packet inspection focused on suspicious traffic for any overlooked details. Use decryption techniques if possible to analyze the actual content and intent of the transferred data. Conduct historical data analysis to identify if similar patterns occurred in the past. |
| Containment and Further Analysis | Implement network segmentation or isolation for systems showing suspicious traffic. Increase monitoring on identified destinations for any outgoing connections. Engage in forensic analysis to determine the scope of data exposure. Coordinate with legal and compliance teams if data breach is verified. Continuously update incident response plan based on findings. |
