# Modify_Authentication_Process:_Network_Device_Authentication - T1556004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access, Defense Evasion, Persistence |
| MITRE TTP | T1556.004 |
| MITRE Sub-TTP | T1556.004 |
| Name | Modify Authentication Process: Network Device Authentication |
| Log Sources to Investigate | Review network device logs, specifically focusing on any logs related to system image updates or changes. Examine logs from network management systems that track firmware or software changes on network devices. Analyze access logs that detail successful and failed login attempts to identify potential misuse of a hard-coded password. Consider monitoring telemetry from intrusion detection systems (IDS) for unusual access patterns or authentication attempts. |
| Key Indicators | Presence of unexpected system image updates or modifications. Sudden increase in successful logins from accounts that typically fail authentication. Detection of known or suspected adversarial passwords being used in authentication attempts. Unusual patterns in login behavior, such as access from atypical locations or at unusual times. |
| Questions for Analysis | Is there evidence of system image updates or modifications that were not authorized or expected? Are there login attempts using credentials that match the known hard-coded password? Are there patterns in the log data that indicate unusual access times or locations? Do network device logs show evidence of firmware alterations? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized modifications to system images are identified. Also, escalate if there are successful logins using the hard-coded password or unexplained successful authentications on multiple devices in a short timeframe. Unusual access patterns can also warrant escalation. |
| Additional Analysis Steps for L1 | Correlate reported authentication attempts with authorized updates or maintenance windows. Cross-reference login attempts with known IP address reputations or geolocations to spot suspicious connections. Verify if there have been any recent configuration changes logged on affected network devices. |
| T2 Analyst Actions | Conduct a deeper investigation into unauthorized system image modifications by comparing against known good images. Evaluate the scope of unauthorized access and identify if a specific password was used. Work with IT to determine if the firmware or software on devices matches expected versions or configurations. |
| Containment and Further Analysis | Isolate affected network devices to prevent further unauthorized access. Reverse any unauthorized image modifications by restoring from a known good backup. Change and strengthen all device passwords. Conduct a full security sweep to ensure there are no other altered systems. Recommend a review and update of device management and monitoring processes. |
