# Supply_Chain_Compromise:_Compromise_Hardware_Supply_Chain - T1195003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Initial Access |
| MITRE TTP | T1195.003 |
| MITRE Sub-TTP | T1195.003 |
| Name | Supply Chain Compromise: Compromise Hardware Supply Chain |
| Log Sources to Investigate | 1. Hardware Audit Logs: Review logs detailing hardware component changes or updates.<br>2. Firmware Logs: Check for unusual firmware updates or modifications.<br>3. Network Traffic Logs: Monitor for any unexpected outbound connections, especially after new hardware is installed. 4. System Logs: Look for system performance degradation or unusual behavior post-hardware installation. Examples include syslog, Windows event logs, or specific appliance logs. |
| Key Indicators | 1. Unexpected firmware versions not matching manufacturer releases.<br>2. Unapproved hardware component changes detected in asset management systems.<br>3. Anomalous network traffic from recently acquired hardware. 4. Unexplained performance issues or new device functionality. |
| Questions for Analysis | 1. Has the hardware recently been installed or updated?<br>2. Are the firmware versions verified with the manufacturer's specifications?<br>3. Is there any anomalous activity associated with the new hardware? 4. Was the hardware acquired from a trusted supplier? |
| Decision for Escalation | Escalate if there is confirmed deviation from expected firmware, evidence of unapproved hardware modifications, or any confirmed suspicious outbound network activities originating from the hardware. |
| Additional Analysis Steps for L1 | 1. Verify the hardware purchase records and compare hardware/firmware specifications with vendor information.<br>2. Examine network logs for any unusual traffic patterns post hardware deployment.<br>3. Check system performance logs for anomalies occurring after the installation. |
| T2 Analyst Actions | 1. Conduct a detailed forensic investigation of the hardware using tools capable of analyzing firmware integrity.<br>2. Coordinate with vendors to verify hardware authenticity and identify potential tampering.<br>3. Monitor affected systems for signs of secondary compromise and validate indicator matches with threat intelligence. |
| Containment and Further Analysis | 1. Isolate any compromised hardware from the network immediately.<br>2. Replace or revert the firmware to a known good state if possible.<br>3. Analyze historical logs to determine the extent of the compromise. 4. Engage with hardware vendors and threat intelligence feeds to inform broader detection and prevention strategies. |
