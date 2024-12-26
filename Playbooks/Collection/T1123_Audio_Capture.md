# Audio_Capture - T1123

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection |
| MITRE TTP | T1123 |
| MITRE Sub-TTP | T1123 |
| Name | Audio Capture |
| Log Sources to Investigate | Monitor operating system APIs related to audio devices for suspicious access. Investigate logs from audio recording applications for unexpected usage. Check file access logs for the creation and modification of audio files. Investigate process execution logs for unusual processes interacting with microphone hardware. Examples include Windows Event Logs, Application logs for specific audio applications, and Endpoint Detection and Response (EDR) telemetry. |
| Key Indicators | Unusual access to microphone APIs or settings changes in the audio configuration. Creation or modification of audio files in protected or unusual directories. Unexpected data transmission from an endpoint, potentially indicating exfiltration of recorded audio files. Process trees showing unexpected applications accessing or controlling microphone devices. |
| Questions for Analysis | Is there legitimate software installed that normally accesses the microphone? Has the microphone access occurred during off-hours or from an unexpected user account? Are there signs of exfiltration, such as encrypted traffic leaving the network or unexpected data uploads? |
| Decision for Escalation | Escalate if unusual microphone access coincides with other suspicious activity, such as network anomalies or the presence of known malware signatures. Escalate if there is evidence of attempted or successful exfiltration of audio files. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the process accessing the microphone by checking installed software and user intent. Correlate audio access events with user login events to identify unauthorized access. Perform a basic check for known malware signatures on the system. |
| T2 Analyst Actions | Conduct a deeper investigation into file system changes, focusing on the locations of suspicious audio files. Analyze network traffic for potential exfiltration attempts, particularly monitoring outgoing encrypted traffic. Conduct a detailed process analysis to identify any unauthorized scripts or malware potentially facilitating audio capture. |
| Containment and Further Analysis | Isolate the affected system to prevent further data leakage. Disable unnecessary microphone access through policy or permission settings. Conduct a full malware scan and consider using forensic tools to identify altered files or processes. Review and update network-level data loss prevention (DLP) measures to detect future unauthorized audio exfiltration. Provide recommendations for increasing awareness and training on protecting sensitive conversations. |
