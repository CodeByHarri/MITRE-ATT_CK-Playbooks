# Data_from_Removable_Media - T1025

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1025 |
| MITRE Sub-TTP | T1025 |
| Name | Data from Removable Media |
| Log Sources to Investigate | Monitor logs related to USB and removable media connections, such as Windows Event Logs (specifically event IDs 200 and 201 for device connection and disconnection), filesystem access logs, and any anti-virus or endpoint detection and response (EDR) solutions that track removable media activity. Also focus on command line logging, looking for anomalous use of 'cmd' processes accessing removable media directories. |
| Key Indicators | Unusual or unauthorized connections of removable media devices, frequent read/write operations on these devices, unexpected command line processes accessing removable media paths, known scripts or executables running from a removable media directory, and anomalous file access patterns immediately prior to known exfiltration techniques. |
| Questions for Analysis | Is the use of removable media expected or approved in this environment? What types of files were accessed or copied from the removable media? Are there patterns in the files accessed that align with sensitive or critical data? Were there any anomalies in the user's typical behavior? Did the user recently report any lost or stolen devices? |
| Decision for Escalation | Escalate to Tier 2 if the removable media activity is uncharacteristic for the user or device, involves sensitive data, or correlates with known stages of an attack lifecycle (like exfiltration). Escalation is also required if there are signs of Automated Collection techniques noted, or if the source of the process is a known compromised device. |
| Additional Analysis Steps for L1 | Verify user activity against known baselines for removable media usage. Confirm the legitimacy of the device connected by checking device IDs against authorized lists. Examine command line history for any scripts or commands interacting with the media and cross-reference with whitelist rules. Identify any other systems the suspected removable media has been connected to recently. |
| T2 Analyst Actions | Conduct a more in-depth investigation on the removable media's contents. Use forensic tools to check for hidden partitions or unusual executable files. Analyze network traffic patterns for potential signs of data exfiltration. Correlate findings with threat intelligence to identify if this is linked to known group behaviors. |
| Containment and Further Analysis | Physically secure and unplug the removable media if it's still connected. Conduct a full system scan using EDR solutions to check for malware or unauthorized processes. Isolate the compromised system if necessary to prevent further unauthorized access. Engage with data loss prevention (DLP) solutions to monitor if any sensitive data was exfiltrated. Towards future prevention, consider implementing stricter controls and monitoring around the use of removable media. |